Humans, Agents, and Robots find themselves operating complex systems and technical equipment in highly dynamic and unknown environments requires faces many challenges. 

Yet with incresing system complexity, the burden on operators will only rise. This is especially the case if these systems are equipped with more autonomy, while not considering how this autonomy affects the human operators.

As software systems increasingly contribute to decision-making, the reduction in cognitive load made possible by the software system is sometimes counter-acted by added confusion of operators seeking to unserstand how the system's decisions came about.

Mantaining common ground between **decision-support** and **decision-making** systems and their **human partners** will make the relationship more effective.

Likewise softwae agents must be able to infer the common ground they have with human actors to react appropriately to input from their partners. Interdependence and therfore common ground is also crucial in the interaction between robotic systems and theiroperators. In some cases robots can be considered as extended sensor systems for operators, and therefore they should contribute to the adjustment of their common ground as sensor information and input from the operator is coming in.


# Common Ground
**Common ground is context-dependent collective acceptance.**
There is a collective acceptance of a proposition ϕ in a context c if and only if everyone involved in that context:
a) accepts ϕ in the context and
b) commonly believes that everyone accepts ϕ in the context.

A **context** can be either:
a) a joint activity (for activity-specific common ground)
b) or a group (personal and communal common ground).

It is the notions of activity-specific, personal, and communal common ground that demonstrate the importance of acceptance as part of common ground. 

A definition of common ground as common belief does not permit such notions, because it is not reasonable to assume that one can hold conflicting beliefs at the same time as part of two different contexts. However, it is quite natural to model conflicting acceptances as part of different contexts. A further observation that we will only touch on in this paper is that the participants in a joint activity draw on some combination of different common grounds: their activity-specific common ground as well as their personal and communal common ground.

We can define generic requirements for an agent's communication system.
1) Reduce the number and size of data transmissions.
2) Enable agents to engage actively and purposefully in the mantainence of shared situational awareness.
3) Enable agents to interact with different stakeholders simultaneously while coping with potentially conflicting stakeholder interests.
4) Enable agents to model communication with sufficient fidelity
5) Interpret and forecast agent-intentions

At the core of this architecture is a module that allows the probe to represent information about its environment. In artificial intelligence, this module is typically called **belief base**, denoting the set of beliefs a software agent has about the state of the environment. Part of this belief base is the probe’s representation of common ground of various contexts. Representing common ground in the same way as the rest of the belief base allows a neat integration. Using the language introduced in the previous section, the representations held in the common ground module of a probe P are of the type BP CAcϕ, i.e. they represent the probe’s beliefs about the common ground held in different contexts. Logical reasoning over the belief base, in line with the inference rules described in Section III, needs to be supported by suitable inference algorithms.

A communication module takes care of communicating with operators. One of the main responsibilities of this module is to maintain the representation of common ground. Clark (1996) calls the process of establishing and maintaining common ground during a joint activity the **grounding process**, which is necessary for the successful execution of joint activities. At the same time, the communication module draws on the representation of common ground to determine the information to be transmitted. We will see an example of this below.

The communication module itself is controlled and invoked by the internal planning processes of the probe whenever communication is required. These planning processes also determine the behavior of the probe in the context of the joint activities with the operators. The planning processes themselves draw on the content of the belief base, potentially including the representation of common ground. 

**Reduce the number and size of data transmissions**
Based on the assumption that what is represented as common ground is information that is actually shared, the communication system can make informed decisions about which information can be omitted from transmission. This can lead to a reduction in data transmission. Assume as a simple example that the probe P has encoded the following about its common ground with a particular operator O that is part of its team: CA{P,O}ϕ → ψ. Now, if the probe learns that ϕ, it is sufficient from the probe’s perspective to establish CA{P,O}ϕ since CA{P,O}ψ follows through modus ponens. The probe no longer needs to query the operator to ask if ψ holds

**Maintain shared situational awareness**
Common ground plays a key role in the shared situational awareness (Saner et al., 2009) between the probe and its operators. By treating common ground as a first-class citizen of the probe’s representation of the environment, maintaining shared situational awareness becomes an inherent feature of the probe’s activities. Moreover, maintaining common ground is a direct effect of communication, and communication is a natural by-product of the probe’s planning activities. If common ground is represented symbolically as we assume here, the probe can improve shared situational awareness by presenting its assumptions about common ground to the operators, based on the symbolic form it is represented in internally. A key issue in human-robot interaction is the difficulty for operators to understand the robots’ reasoning (Stubbs et al., 2007), which can be avoided by making the robot more transparent. To detect and mitigate mis-communication, the probe can represent the operators’ perception of common ground on top of its own perception (that is, what it believes is the operator’s belief of common ground), using the same representational system. This can help the probe to disentangle the discrepancies between actual common ground and perceived common ground.

**Interact with different stakeholders simultaneously** 
The model of common ground introduced in the previous section can represent different and possibly conflicting common ground associated with different contexts, i.e. CAc1 ϕ ∧ CAc2 ¬ϕ. The key to this capability, which is not found in other models of common ground, is the reliance on the notion of acceptance. While interacting with different parties, the probe can accept conflicting information until eventually there is a necessity to resolve the conflict. For example, the probe could establish common ground with scientists to point an instrument at a particular attitude while also establishing with engineers to go into maintenance mode at the same time. Obviously, this conflict requires resolution through communication but this could deliberately be deferred to a later point.

**Model communication with sufficient fidelity**
Common ground and the grounding process play a key role in human-human communication. Therefore, agents in this system also need a sufficiently accurate model of grounding and common ground for their interactions with human team members.

First, we discussed earlier that common ground comes in different types; and the common ground assumed in a particular joint activity consists not only of the common ground created immediately in that activity (activity-specific common ground) but also of the common ground that is held because of the previous common experiences (personal common ground) and common group memberships of the participants (communal common ground).

The agent would draw on the personal common ground created during previous interactions with its communication partners. A requirement for the representation of communal common ground is a representation of group memberships to be included in the belief base. Also, a suitable model needs to be created for the “merging” of activity-specific, personal, and communal common ground.

Second, one purpose of the grounding process is to align perceived and actual common ground. For agents to track discrepancies between their actual common ground and the common ground that they each assume to hold they need to be able to represent what they believe about the perception of common ground of other agents. We mentioned this in the context of the previous scenario. Only a model of common ground as differentiated as the one we build on here can support this requirement.

Overall, representing and using common ground improves the interdependence between probes and their operators: probes adjust their communication to the current situation and the information assumed to be shared to reduce data transmission, while still maintaining sufficient shared situational awareness.

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

Figure 1 shows a clarifying example Kripke model. There are four possible worlds, marked wi . The valuation V (wi) of each world wi denotes whether p is true in that world or not. For example, V (w<sub>1</sub>) = {}, V (w<sub>2</sub>) = {p}. That is, p is true in w2 but not in w1. The accessibility relations Ri for each [[Agent]] (in this case there are two) are denoted by arrows. A label Bi on an arrow from world u to v denotes that (u, v) ∈ R<sub>i </sub>.

![[Pasted image 20221123173202.png]]
Figure 1. An example of a Kripke model for a doxastic modal logic. On this figure, a label Bi on an arrow from world u to v denotes (u, v) ∈ R<sub>i</sub>.

Informally, if we are in a world u, then the set {v | R<sub>i</sub>(u, v)} denotes the worlds that [[Agent]] i considers possible descriptions of the world. In the figure, [[Agent]] 1 considers the worlds w<sub>2</sub> and w<sub>3</sub> possible in w<sub>1.</sub> Because p is true in both w<sub>2</sub> and w<sub>3</sub>, [[Agent]] 1 believes that p does hold, i.e. B<sub>1</sub>p in world w<sub>1</sub>. The reason is that the [[Agent]] does not consider any other world possible that contradicts with this. Note that we cannot say this about [[Agent]] 2 in world w1, because w<sub>3</sub> and w<sub>4</sub> are possible for [[Agent]] 2 and p is true in w<sub>3</sub> but not in w4. Note that B<sub>1</sub>p holds also in w<sub>2</sub> and w<sub>3</sub>. Because these are the only two worlds [[Agent]] 1 considers possible in world w1, we also have B<sub>1</sub>B<sub>1</sub>p, i.e. in world w1 [[Agent]] 1 believes that it believes p.

Depending on additional constraints put on the accessibility relations, particular properties of belief follow. **From these constraints, we can prove axioms on the syntactic side, which can be used for further logical reasoning as indicated above.** When we describe the common ground logic in the next section, we omit the full description of the semantics. However, we believe that it is valuable for the reader to get an idea about the type of semantics we rely on.

# **Syntax**

Let **Σ** be a set of propositional symbols, and ***Ag*** be a finite and non-empty set of agents.

**We define the common ground modal language L<sub>CG</sub> to be the smallest set that is determined by the following Backus Naur Form:**

ϕ ::= p | ¬ϕ | ϕ ∧ ϕ | B<sub>i</sub>ϕ | EB<sub>G</sub>ϕ | CB<sub>G</sub>ϕ | A<sub>c</sub> iϕ | EA<sub>c</sub>ϕ | CA<sub>c</sub>ϕ

where:
- **p** is any propositional symbol in **Σ**
- **i** is any agent in Ag
- **G** is a group of agents such that **G ⊆ A<sub>g</sub>
- and **c** is a **context**.

A context is either an **activity** (denoted by **α**) or a **group** (denoted by **G**).

Informally, B<sub>i</sub>ϕ specifies that agent i believes ϕ, EBGϕ specifies that ϕ is believed by every agent in the group G, and CBGϕ specifies that ϕ is common belief for the group of agents in G.

Negation is represented using the symbol ¬, and conjunction with ∧.

*This syntax follows existing modal logics of belief and common belief (Fagin et al., 1995).*

The proposition **A<sub>i</sub><sup>c</sup>ϕ** specifies that agent **i** accepts **ϕ** in context **c**, representing the notions of individual acceptance in joint activity contexts, personal groups, and communal groups. 

Informally, **EA<sub>c</sub>ϕ** specifies that every agent involved in context **c** accepts **ϕ** in that context, and CAcϕ specifies that it is collectively accepted by every agent in context c that ϕ holds in that context.

*Standard propositional connectives such as ∨, →, and ↔ can be defined in terms of ¬ and ∧; e.g. p ∨ q is the same as ¬(¬p ∧ ¬q).*

Recall that context-dependent collective acceptance as denoted by CAcϕ reflects activity-specific, personal, and communal common ground, depending on the type of context c (joint action or group). The concepts of personal common ground and communal common ground are treated the same, and it is the identification of the group as personal or communal that determines which type of common ground it is.

**Consistent with our discussion in the previous section, individual beliefs are not indexed by a context: beliefs are independent of context (although they can result from context-dependent activities).**

# Axiomatics
We describe an axiom schema for the LCG logic in this section. While doing so, we omit the detailed semantics and instead build on the intuitive meanings of sentences. The full detail of the logic is reported elsewhere (Pfau et al., 2014). However, we note that the logic’s semantics rely on accessibility relations for the belief and acceptance modalities for each agent and context.

The axioms and inference rules listed in the following subsections comprise a Hilbert-style deductive proof system for LCG.

*In a Hilbert-style deduction system, a **formal deduction** is a finite sequence of formulas in which each formula is either an axiom or is obtained from previous formulas by a rule of inference. These formal deductions are meant to mirror natural-language proofs, although they are far more detailed.*

![[Deduction_architecture.png]]

For the sake of clarity, we describe the axiom schema in two separate sections. The first section describes axioms and inference rules related to belief. The second section describes axioms and inference rules related to acceptance.

## Individual and Common Belief
![[Pasted image 20221128134401.png]]
In addition, we account for the following inference rules.
![[Pasted image 20221128134422.png]]

The axioms for propositional logic (Prop), inference rules modus ponens (MP) and necessitation (NecB), and the distribution axiom (KB) define a normal modal logic. 

Axiom KB entails that if an agent believes an implication, then when the agent believes the antecedent of the implication, it also believes the consequent. Axioms DB, 4B, and 5B further define a standard KD45 logic (Fagin et al., 1995). DB ensures the consistency of beliefs (an agent cannot believe something and its negation), and 4B and 5B represent positive introspection and negative introspection for beliefs respectively. That is, if an agent believes (does not believe) something, it believes that it believes (does not believe) it. 

Axiom EB defines how shared belief is derived from individual belief, and axiom CB is the so-called fixed-point axiom for common belief, which demonstrates the infinite nature of common belief. 

The inference rule MP defines the rule of modus ponens. Together with the distribution axiom KB, this implies that an agent believes all the logical consequences of its beliefs. The rule NecB specifies that if something is a tautology, the agent believes it. These last two assumptions are known as logical omniscience and are commonly accepted to be too strong for resource-bounded agents. The final rule, IndCB, describes how common belief is inferred from shared belief.

## Individual and Collective Acceptance
![[Pasted image 20221128134811.png]]

Axioms KA, DA, 4A, and 5A together form a standard KD45 modal logic, and therefore the notion of acceptance is equivalent to the notion of belief, but defined over a different accessibility relation. Axioms 4AB and 5AB specify that an agent has positive and negative awareness about their acceptances. That is, if an agent accepts (does not accept) a proposition, then they believe that they accept (do not accept) that proposition. Axiom EA is the counterpart to axiom EB and defines how shared acceptance is derived from individual acceptances. Axiom CA defines how collective acceptance is derived from shared acceptance and the common belief of shared acceptance. Note that this formalization of collective acceptance reflects the informal description from Definition 4. In Section V.B, we present a model of this defined in an agent programming language called AgentSpeak. This model uses the axioms above to infer new statements about the beliefs and acceptances of agents and groups of agents.





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

