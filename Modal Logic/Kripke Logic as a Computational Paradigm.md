# Doxatic Modal Logics

The syntax of a multi-[[Agent]] doxastic modal logic consists of:

- a set Σ of [[propositional symbols]] (usually p, q, r, etc), which represent basic facts about the environment;
- the standard [[propositional connectives]] (¬, ∨, ∧, and →);
- and a set of modal operators Bi for each [[Agent]] i, which describes the beliefs that the particular [[Agent]] i has.
**[[Compound propositions]]** (usually denoted ϕ or ψ) can be built from this [[Language]].

As an example, consider the proposition Ba(level(propellant, low) → warn(op, level(propellant, low))), which states that [[Agent]] a believes that if the level of the propellant is low, then the operator op should be warned of this. Here, the modality Ba represents agents a’s beliefs about its world.

Modalities can be nested, thus expressing such statements as BaBopvalve_open → Bavalve_open, which specifies that if [[Agent]] a believes that the operator op believes that the valve is open, then [[Agent]] a also believes this.

With this [[Language]], one can describe the basic axioms of doxastic mental attitudes and, using [[logical inference]], derive the properties that follow from those axioms.

We require a corresponding semantics to give meaning to the sentences of the [[Language]]. In fact, it is the semantics that enables logical reasoning on the syntactical level at all. The semantics of modal logics are usually based on Kripke semantics (Kripke, 1963). A Kripke model consists of a non-empty set W of possible worlds (usually denoted u, v, w), a belief accessibility relation for each [[Agent]] defined over these possible worlds (usually Ri ⊆ W × W), and a valuation [[function]] that determines which [[propositional symbols]] are true in each world (usually V : W → 2 Σ).

Figure 1 shows a clarifying example Kripke model. There are four possible worlds, marked wi . The valuation V (wi) of each world wi denotes whether p is true in that world or not. For example, V (w1) = {}, V (w2) = {p}. That is, p is true in w2 but not in w1. The accessibility relations Ri for each [[Agent]] (in this case there are two) are denoted by arrows. A label Bi on an arrow from world u to v denotes that (u, v) ∈ Ri .

![[Pasted image 20221123173202.png]]
Figure 1. An example of a Kripke model for a doxastic modal logic. On this figure, a label Bi on an arrow from world u to v denotes (u, v) ∈ Ri.

Informally, if we are in a world u, then the set {v | Ri(u, v)} denotes the worlds that [[Agent]] i considers possible descriptions of the world. In the figure, [[Agent]] 1 considers the worlds w2 and w3 possible in w1. Because p is true in both w2 and w3, [[Agent]] 1 believes that p does hold, i.e. B1p in world w1. The reason is that the [[Agent]] does not consider any other world possible that contradicts with this. Note that we cannot say this about [[Agent]] 2 in world w1, because w3 and w4 are possible for [[Agent]] 2 and p is true in w3 but not in w4. Note that B1p holds also in w2 and w3. Because these are the only two worlds [[Agent]] 1 considers possible in world w1, we also have B1B1p, i.e. in world w1 [[Agent]] 1 believes that it believes p.

Depending on additional constraints put on the accessibility relations, particular properties of belief follow. **From these constraints, we can prove axioms on the syntactic side, which can be used for further logical reasoning as indicated above.** When we describe the common ground logic in the next section, we omit the full description of the semantics. However, we believe that it is valuable for the reader to get an idea about the type of semantics we rely on.

# **Syntax**

Let **Σ** be a set of propositional symbols, and ***Ag*** be a finite and non-empty set of agents.

We define the common ground modal language L<sub>CG</sub> to be the smallest set that is determined by the following Backus Naur Form:

ϕ ::= p | ¬ϕ | ϕ ∧ ϕ | B<sub>i</sub>ϕ | EB<sub>G</sub>ϕ | CBGϕ | A<sub>c</sub> iϕ | EA<sub>c</sub>ϕ | CA<sub>c</sub>ϕ

where:
- **p** is any propositional symbol in **Σ**
- **i** is any agent in Ag
- **G** is a group of agents such that **G ⊆ Ag**
- and **c** is a **context**.

A context is either an **activity** (denoted by **α**) or a **group** (denoted by **G**).

Informally, Biϕ specifies that agent i believes ϕ, EBGϕ specifies that ϕ is believed by every agent in the group G, and CBGϕ specifies that ϕ is common belief for the group of agents in G.

Negation is represented using the symbol ¬, and conjunction with ∧.

*This syntax follows existing modal logics of belief and common belief (Fagin et al., 1995).*

The proposition **A<sub>i</sub><sup>c</sup>ϕ** specifies that agent **i** accepts **ϕ** in context **c**, representing the notions of individual acceptance in joint activity contexts, personal groups, and communal groups. 

Informally, **EA<sub>c</sub>ϕ** specifies that every agent involved in context **c** accepts **ϕ** in that context, and CAcϕ specifies that it is collectively accepted by every agent in context c that ϕ holds in that context.

*Standard propositional connectives such as ∨, →, and ↔ can be defined in terms of ¬ and ∧; e.g. p ∨ q is the same as ¬(¬p ∧ ¬q).*

Recall that context-dependent collective acceptance as denoted by CAcϕ reflects activity-specific, personal, and communal common ground, depending on the type of context c (joint action or group). The concepts of personal common ground and communal common ground are treated the same, and it is the identification of the group as personal or communal that determines which type of common ground it is. Consistent with our discussion in the previous section, individual beliefs are not indexed by a context: beliefs are independent of context (although they can result from context-dependent activities).

**Charecter Stream**

**Scanner**

**Token Stream**


**Parser**

**Parse Tree**
- Interaction Net - Hypergraph

**Semantic Analysis and Intermediary Code Generation**

**Abstract Syntax Tree or other Intermediate Form**

**Object-Hypergraph Interaction Net of Functions and Remappings, with corresponding streams between objects for Beleif Modal Operators**


#### Modal Logic Solver: Framework for modelling Kripke structures and solving modal logic formulas
https://github.com/mondano/mlsolver/tree/master/mlsolver

[[Multi-agent doxastic modal logic]]


