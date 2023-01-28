https://www.infoq.com/presentations/HyperGraphDB/

## HypergraphDB Model & Terminology
- V (nodes) + E(Edges) = A(atoms)
- Atom = **target set** + "payload", that is a tuple of 0 for (**nodes**) or more (for **links**) atoms + a typed value
- **Incidence set(x)** = {y | x is in y's target set},
- **Arity(x)** = cardinality of its target set
- **Type(x)** = An atom conforming to a special interface
- **Value(x)** = Arbitrary data managed by Type(x)

### Why n-ary relationships
- Because sometimes more then 2 things stand in a relationship together!

## Why higher-order relation?
- Because a relation is an abstract entity in a model, i.e. an **entity**...
- Examples:
	- Causal links between events
	- Contextualization (betweeness depends on transportation means)
	- Instead of sparse foreign keys
	- Standard tree-like structures
	- Rule representation: link premises and conclusion

## Atoms and References
- Node atoms: any Javascript Object
- Link atoms: implements HGLink
	- possible to decouple this interface at a small cost
- Universal reference: HGHandle
	- HGLiveHandle points to the Javascript Ref and the
	- HPPersistentHandle which is the DB id
	- Valid in a distributed environment
	- Several varieties interacting with caching etc.
- Because of Universal Validity, can't use disk offsets as atom identifiers, key lookup required
- In RAM, HGHandle derferencing is member dereferencing at best or hash lookup at worst.

## Incidence Sets
- Given atoms:
	- L->[A,B,C] and A->[C,D,E]
	- The incidence set of C is IS(C)={L,A}
		- To find adjacent atoms, exmamine all targets of all links in an atom's incidence set
	- ...so A is both an adjacent atom and an incident link to C
	- All incidence sets are stored in the cache

### Caching
- Constant lookup of handle by atom and vice-versa
- Constant traversals within RAM working set
- Holding the incidence set of an atom in the cache allows for doing traversals without holding information about the full graph.

### Storage Architecture
- Two layers - primitive and model layer
- Primitive Layer - a low-level graph of identities and raw data
- Model Layer - a layout for representing typed hypergraph atoms

### Primitive Layer
- A graph of identities and raw, byte[] data
- LinkStore
	- ID -> [ID,...,ID] stores ID's mapped to tuples of ID's
- DataStore
	- ID -> byte[]
- Current IDs are type 4 UUID

### Model Layer
- Formalizes layout of primitives:
	- AtomID -> [TypeID, ValueID, TargetId, ... TargetID] (Value can be something structured, to represent nested structures)
		TypeID := AtomID
		TargetID := AtomID
	 ValueID -> [ID, ... ID] | byte[]
- A set of predefined indices:
	- IncidenceIndex: AtomID -> SortedSet(AtomID)
		TypeIndex: TypeID -> SortedSet(AtomID)
		ValueIndex: ValueID -> SortedSet(AtomID)

## Typing
- Data Interpretation
	- Integrity and consistency
	- Customized storage model
	- Dynamic databse schema
- Types as atoms
	- **Reflectivity: domain model part of the data!**
	- **Type constructors** (types of types) covers any types: allows us to map different programming paradigms and type systems in the db.
	- Bootstrapped by a set of predefined types
		- Frozen in cache, configurable

## The HGAtomType Interface
Create and return the runtime of an atom or some nested value

Objectmake(**HGPersistentHandle** handle, HGHandle[], targetSet, Set(HGHandle) incidenceSet)
- **HGPersistentHandle** is the storage ValueID
- **HGhandle[]** is empty for nodes or nested values
- IncidenceSet: the runtime instance of an atom can depend on its graph connections! -> the runtime presentation of an atom can depend on how it is networked with other atoms in the graph

Call storage layer to serialize instance and return a new or existing ValueID HGPersistentHandle store(Object Instance)

Remove a value from storage layer given it's ValueID void release(HGPersistentHandle handle)

Used mainly as a sub-typing predicate in type constructors boolean subsumes(Object general, Object specific)

### Java Typing
Java Type Factories allows for converting any Java classes or HypergraphDB predefined types and type constructors into language agnostic HypegraphDB types.

**Q:** **What about type hierarchies?**
**A:** Represented with a predefined HGSubsumes link - remember, types are just atoms.

## Indexing
**- Associate indexes with atom types - then indexing is automatic**
- HGIndexer: given an atom, produce a key.
- Out-of-box implementations:
	- object property -> atom
	- target -> atom
	- target -> another target
	- target tuple -> atom
	- multi-key: compose any of the above

## Querying
- Traversals - API for standard graph traversals. Hyper-traversals by jumping levels of type-abstraction.
- Constrained atom sets (SQL style), API based, lazy evaluation
- (Vaporware) Graph patterns - a new API + comprehensive query language

## Transactions
- MVCC in memory and on disk
- ACI(D), nested, thread-bound
- Read-only transactions
	- never conlict
	- very long queries or traversals remain isolated at no additional memory cost!
- Conflicts resolved through retries
	- Be careful of side-effects within your own code!

## Distribution
- Builld on ACL (Agent Communication Language)
- Pluggable presence and communication layer
- Nested workflows framework for agent
- Primitive conversations such as subgraph transfer
- Eventually consistent replication at model layer level.