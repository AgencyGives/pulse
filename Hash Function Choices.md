**Hash array mapped trie**
A **hash array mapped trie**[[1]] (**HAMT**) is an implementation of an [associative array](https://en.wikipedia.org/wiki/Associative_array "Associative array") that combines the characteristics of a [hash table](https://en.wikipedia.org/wiki/Hash_table "Hash table") and an array mapped [trie](https://en.wikipedia.org/wiki/Trie "Trie").[[1]] It is a refined version of the more general notion of a [hash tree](https://en.wikipedia.org/wiki/Hash_tree_(persistent_data_structure) "Hash tree (persistent data structure)").

https://en.wikipedia.org/wiki/Hash_array_mapped_trie
**Javascript Hash Array Mapped Trie**
https://github.com/mondano/hamt

**Conccurrent Hash Trie**
The concurrent lock-free version of the hash trie called [Ctrie](https://en.wikipedia.org/wiki/Ctrie "Ctrie") is a mutable thread-safe implementation which ensures progress. The data-structure has been proven to be correct - Ctrie operations have been shown to have the [atomicity](https://en.wikipedia.org/wiki/Atomicity_(programming) "Atomicity (programming)"), [linearizability](https://en.wikipedia.org/wiki/Linearizability "Linearizability") and [lock-freedom](https://en.wikipedia.org/wiki/Lock_free "Lock free") properties.

https://www.researchgate.net/publication/221643801_Concurrent_Tries_with_Efficient_Non-Blocking_Snapshots
https://en.wikipedia.org/wiki/Ctrie

**Cache-Aware Lock-Free Concurrent Hash Tries**
http://infoscience.epfl.ch/record/166908/files/ctries-techreport.pdf


## Distributed Hash Table
Prefix Hash Tree An Indexing Data Structure over Distributed Hash Tables
https://people.eecs.berkeley.edu/~sylvia/papers/pht.pdf

## P Grid
https://www.manfredhauswirth.org/research/talks/P-Grid-Sbg.pdf

![[Pasted image 20221127204054.png]]
P-Grid abstracts a [trie](https://en.wikipedia.org/wiki/Trie "Trie") and resolves queries based on prefix matching. The actual topology has no hierarchy. Queries are resolved by matching prefixes. This also determines the choice of routing table entries. Each peer, for each level of the trie, maintains autonomously routing entries chosen randomly from the complementary sub-trees.[[2]](https://en.wikipedia.org/wiki/P-Grid#cite_note-Ray-2) In fact, multiple entries are maintained for each level at each peer to provide fault-tolerance (as well as potentially for query-load management). For diverse reasons including fault-tolerance and load-balancing, multiple peers are responsible for each leaf node in the P-Grid tree. These are called replicas. The replica peers maintain an independent replica sub-network and uses gossip based communication to keep the replica group up-to-date.[[3]](https://en.wikipedia.org/wiki/P-Grid#cite_note-Jepsen-3) The redundancy in both the replication of key-space partitions as well as the routing network together is called structural replication. The figure above shows how a query is resolved by forwarding it based on prefix matching.[_[citation needed](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed "Wikipedia:Citation needed")_]


## Koorde
In [peer-to-peer](https://en.wikipedia.org/wiki/Peer-to-peer "Peer-to-peer") networks, **Koorde** is a [distributed hash table](https://en.wikipedia.org/wiki/Distributed_hash_table "Distributed hash table") (DHT) system based on the [Chord DHT](https://en.wikipedia.org/wiki/Chord_(DHT) "Chord (DHT)") and the [De Bruijn graph](https://en.wikipedia.org/wiki/De_Bruijn_graph "De Bruijn graph") ([De Bruijn sequence](https://en.wikipedia.org/wiki/De_Bruijn_sequence "De Bruijn sequence")). Inheriting the simplicity of Chord, Koorde meets [_O_](https://en.wikipedia.org/wiki/Big_O_notation "Big O notation")(log _n_) hops per [node](https://en.wikipedia.org/wiki/Node_(networking) "Node (networking)") (where n is the number of nodes in the DHT), and {\displaystyle O\left({\frac {\log n}{\log(\log n)}}\right)}![{\displaystyle O\left({\frac {\log n}{\log(\log n)}}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/abe53f2911ec858f9b369f55c30e264999ed24eb) hops per lookup request with _O_(log _n_) neighbors per node.

The Chord concept is based on a wide range of [identifiers](https://en.wikipedia.org/wiki/Network_address "Network address") (e.g. 2160) in a structure of a [ring](https://en.wikipedia.org/wiki/Ring_network "Ring network") where an identifier can stand for both node and data. Node-successor is responsible for the whole range of IDs between itself and its predecessor.