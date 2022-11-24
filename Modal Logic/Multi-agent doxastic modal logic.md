The syntax of a multi-[[agent]] doxastic modal logic consists of:

- a set Σ of [[propositional symbols]] (usually p, q, r, etc), which represent basic facts about the environment;
- the standard [[propositional connectives]] (¬, ∨, ∧, and →);
- and a set of modal operators Bi for each [[agent]] i, which describes the beliefs that the particular [[agent]] i has. **[[Compound propositions]]** (usually denoted ϕ or ψ) can be built from this [[language]].

As an example, consider the proposition Ba(level(propellant, low) → warn(op, level(propellant, low))), which states that [[agent]] a believes that if the level of the propellant is low, then the operator op should be warned of this. Here, the modality Ba represents agents a’s beliefs about its world.

Modalities can be nested, thus expressing such statements as BaBopvalve_open → Bavalve_open, which specifies that if [[agent]] a believes that the operator op believes that the valve is open, then [[agent]] a also believes this.

With this [[language]], one can describe the basic axioms of doxastic mental attitudes and, using [[logical inference]], derive the properties that follow from those axioms.

We require a corresponding semantics to give meaning to the sentences of the [[language]]. In fact, it is the semantics that enables logical reasoning on the syntactical level at all. The semantics of modal logics are usually based on Kripke semantics (Kripke, 1963). A Kripke model consists of a non-empty set W of possible worlds (usually denoted u, v, w), a belief accessibility relation for each [[agent]] defined over these possible worlds (usually Ri ⊆ W × W), and a valuation [[function]] that determines which [[propositional symbols]] are true in each world (usually V : W → 2 Σ).

Figure 1 shows a clarifying example Kripke model. There are four possible worlds, marked wi . The valuation V (wi) of each world wi denotes whether p is true in that world or not. For example, V (w1) = {}, V (w2) = {p}. That is, p is true in w2 but not in w1. The accessibility relations Ri for each [[agent]] (in this case there are two) are denoted by arrows. A label Bi on an arrow from world u to v denotes that (u, v) ∈ Ri .

![[Pasted image 20221123173202.png]]
Figure 1. An example of a Kripke model for a doxastic modal logic. On this figure, a label Bi on an arrow from world u to v denotes (u, v) ∈ Ri.

Informally, if we are in a world u, then the set {v | Ri(u, v)} denotes the worlds that [[agent]] i considers possible descriptions of the world. In the figure, [[agent]] 1 considers the worlds w2 and w3 possible in w1. Because p is true in both w2 and w3, [[agent]] 1 believes that p does hold, i.e. B1p in world w1. The reason is that the [[agent]] does not consider any other world possible that contradicts with this. Note that we cannot say this about [[agent]] 2 in world w1, because w3 and w4 are possible for [[agent]] 2 and p is true in w3 but not in w4. Note that B1p holds also in w2 and w3. Because these are the only two worlds [[agent]] 1 considers possible in world w1, we also have B1B1p, i.e. in world w1 [[agent]] 1 believes that it believes p.

Depending on additional constraints put on the accessibility relations, particular properties of belief follow. **From these constraints, we can prove axioms on the syntactic side, which can be used for further logical reasoning as indicated above.** When we describe the common ground logic in the next section, we omit the full description of the semantics. However, we believe that it is valuable for the reader to get an idea about the type of semantics we rely on.

