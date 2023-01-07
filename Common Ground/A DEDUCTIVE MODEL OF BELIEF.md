A robot planning system, such as STRIPS, must represent knowledge about the world in order to plan actions that affect the world. Of course it is not possible to represent all the complexity of the real world, so the planning system uses some abstraction of real-world properties that are important for its task, e.g., it might assume that there are objects that can be stacked on each other in simple ways (the blocks-world domain). It is helpful to view the representation and deduction of facts about the world as a separate subsystem within the planning system; we call it the belief subsystem. In its simplest, most abstract form, the belief subsystem comprises a list of sentences about a situation, together with a deductive process for deriving consequences of these sentences. It is integrated with other processes in the planning system, especially the plan derivation process that searches for sequences of actions to achieve a given goal.

![[Pasted image 20221205204448.png]]

In a highly schematic form, Figure 1 sketches the belief subsystem and its interaction modes with other processes of the planning system. The belief system is composed of the base sentences, together with the belief deductive process. Belief deduction itself can be decomposed into a set of deduction rules, and a control strategy that determines how the deduction rules are to be applied and where their outputs will go when requests are made to the belief subsystem.

There are two types of requests that result in some action in the belief subsystem.

**Belief Update Rule:** **A process may request the subsystem to add or delete sentences in its base set**; this happens, for example, when the plan derivation process decides what sentences hold in a new situation. Although this process of belief updating and revision is a complicated research problem in its own right, we do not address it here (see Doyle l | for related research).

**The second type of request is a query as to whether a sentence is a belief or not.** This query causes the control strategy to tr y to prove t hat the sentence is a consequence of the base set, using the deduction rules. It is this process of belief querying that we model in this paper.

We list here some further assumptions about belief subsystems. The internal language of a belief subsystem is a formal language, which must include a (modal) belief operator, e.g., a propositional or first-order modal language would be appropriate. It is assumed that there is a Tarskian semantics for the language, that is, sentences of the language are either true or false of the real world. The belief subsystem doesn't inherently support the notion of uncertain beliefs, **although this idea could be introduced if the internal language contained statements about uncertainty, e.g., statements of the form P is true with probability 1/2.**

**Tarskian Semantics: Tarskian Semantics, or No Notation Without Denotation!** http://www.cs.nott.ac.uk/~pszbsl/G52HPA/articles/McDermott:78a.pdf
related to **A denotational semantics for the symmetric interaction combinators**



<mark style="background: #BBFABBA6;">The deduction rules of a belief subsystem are assumed to be sound (with respect to the semantics of the internal language), effectively computable, and to have bounded input. In particular, this forces deduction rules to be monotonic. **It is our view that nonmonotonic or default reasoning should occur in the belief updating and revision process, rather than in querying beliefs.</mark>

Note that deductive consistency does not entail satisfiability, because the deductive process may not be complete. That is, a set of beliefs may be unsatisfiable and thus logically inconsistent, but, because of resource limitations, it may be impossible for an agent to derive a contradiction. Deductive consistency is the appropriate concept for belief subsystems. The assertion that rational agents are consistent is compatible with, but not required by, the model. It gives rise to a slightly different axiomatization (see Section 3).

The results of this paper depend only on the most general features of a belief subsystem as depicted in Figure 1: namely, that there is a formal internal language in which statements about the world are encoded; that there is a finite set of base beliefs in this language; and that there is some process of belief deduction that applies sound and effectively computable deduction rules to the base sentences at appropriate times, in response to requests by other processes in the planning system. A belief subsystem with these properties (along with the amplifications and restrictions given above) is a model of belief for planning agents, which we call Deductive Belief.

2.2 Resource Limitations and Deductive Cloture 
<mark style="background: #BBFABBA6;">One of the key properties of belief deduction that we wish to include is the effect of resource limitations. If an agent cannot deduce all the logical consequences of his beliefs, then we say that his deductive process is incomplete.</mark>

Logical incompleteness arises from two sources: an agent's deduction rules may be too weak, or his control strategy may perform only a subset of the derivations possible with the deduction rules.

<mark style="background: #FF5582A6;">CLOSURE PROPERTY. The sentences derived in a belief subsystem are closed under its deduction rules.</mark>

One advantage of requiring that beliefs be closed under deduction is conceptual clarity and predictability.

If beliefs are not closed, then there is some control strategy that guides the deductive process, making decisions to perform or not to perform deductions. If this control strategy uses a global effort bound, then behavior of such a subsystem is hard to predict.

Theoretically there may be a derivation of a sentence, but the control strategy in a particular case decides not to derive it, because it tried other derivations first. Closed systems, on the other hand, behave more dependably. They are guaranteed to arrive at all derivations possible with the given deduction rules.

The concept of "belief" is also complicated by the introduction of control strategy issues. **For example, it makes a difference to the control strategy as to whether a sentence is a member of the base set, or obtained at some point in a derivation.** One cannot simply say, "Agent S believes P* because such a statement doesn't give enough information about P to be useful. If P is derived at the very limit of deduction resources, then nothing will follow from it; if it is a base sentence, then it might have significant consequences.

In terms of formalizing the model of Deductive Belief, the assumption of closure is technically extremely useful.

**Consider the task of formalizing a belief subsystem that has a complex global control strategy guiding the deductive process.**

To do this correctly, one must write *axioms that describe the agendas*, **proof trees**, **and other data structures used by the control strategy**, and *how the control process guides deduction rules operating on these structures.*

Reasoning about the deductive process involves making inferences using these axioms to simulate the deductive process, a highly inefficient procedure.

By contrast, the assumption of closure leads to a simple formalization of belief subsystems that incorporates the belief deductive process in a direct way (the Deductive Belief logic, B, is presented in the next section)


Having argued that control strategies that use a global effort bound are undesirable, **we now show that weak (but closed) deduction can have the same effect as control strategies with a local effort bound.** 

**We define a local bound as a restriction on the type of derivations allowed, without regard to other derivations in progress, i.e., all derivations of a certain sort are produced.** An example of this sort of control strategy is **level-saturation** in resolution systems. Here we give a simpler example.

**Suppose an agent uses modus ponens as his only deduction rule, and has a control strategy in which only derivations using fewer than k applications of this rule are computed; this is a local effort bound.**

<mark style="background: #ADCCFFA6;">
To model this situation with a closed belief subsystem, consider transforming the base set so that each sentence has an extra conjunct tacked onto it, the predicate DD(0) (DD stands for "derivation depth"). Instead of modus ponens, the belief subsystem has the following modified deduction rule:</mark>

![[Pasted image 20221205210142.png]]

MP2 is sound and effectively computable, so it is a valid deduction rule for a belief subsystem. The closure of the base set of sentences of the belief subsystem under MP2 will be the same (modulo the DD predicate) as the set of sentences deduced by the nonclosed control strategy of the agent. The Closure Property, together with the assumption of totality for the belief derivation process, imply that the deduction rules are decidable for all base sets of sentences. 

The Closure Property, together with the **assumption of totality** for the belief derivation process, imply that the deduction rules are decidable for all base sets of sentences.

> The process of belief derivation is assumed to be total. This means that the answer to a query will be returned in a finite amount of time; i.e., the belief subsystem cannot simply sit and continue to perform deductions without returning an answer.

## Views
Up to this point, we have specifically assumed that agents don't have any deduction rules dealing with the beliefs of other agents. Now, however, we form the constructive part of the Deductive Belief model: adding to the belief subsystem model so that an agent can reason about its own and other belief subsystems. **We can arrive at deduction rules that apply to beliefs by noting that the obvious candidate for the intended interpretation of the belief operator is another belief subsystem.**

**That is, the modal sentence [S]α is intended to mean "the sentence a is derivable in agent S's belief subsystem."**

> This is important for the DHT, and showing someone where to go to find sound Derivations.

The new deduction rules that apply to belief operators will be judged sound if they respect this intended interpretation. For example, suppose a deduction rule states that, from the premise sentences [S]p and [S](p>q), the sentence [S]q can be concluded. This is a sound rule if modus ponens is believed to be a deduction rule of S's belief subsystem, since the presence of p and pz>q in a belief subsystem with modus ponens means that q will be derived.

We summarize by postulating the following property of Deductive Belief:

<mark style="background: #BBFABBA6;">RECURSION PROPERTY . The intended model of the belief operator in tbe internal language of a belief subsystem is another belief subsystem. The intended model for an agent's own beliefs is his own belief subsystem.</mark>

The Recursion Property of belief subsystems leaves a large amount of flexibility in representing nested beliefs. Each agent might have his own representational peculiariaties for other agents' beliefs. An agent John might believe that Sue has a set of deduction rules R1, whereas he believes that Kim's rules are R2. In addition, John might believe that Sue believes that Kim's rules are R3.

**We call a belief subsystem as perceived through a chain of agents a view, and use the Greek letter v to symbolize it.**

For example, John's perception of Sue's perception of Kim's belief subsystem is the view v = John, Sue, Kim.

Having slated the Recursion Property, we now ask if there is a way to implement it within the confines of belief subsystems. At first glance it would seem so: suppose the agent S wishes to know whether he believes some statement p, i.e., whether [S]p is one of his own beliefs. If we assume he can query his belief subsystem, he simply submits p to it; if it answers "yes," he believes {S]p, and if ''no," then he believes -[S]p. Similarly, if he wishes to know whether another agent S' believes p, he simply queries a subsystem supplied with **(his version of) S' deduction rules**, and uses the answer to conclude either [S]p or -[S']p.

The problem with this strategy is that we haven't shown that S will receive an answer from the subsystems he queries. In the case of querying his own subsystem, there may be another occurrence of the modal operator [S] that wil l cause a recursive call to his belief subsystem, and so on in an unbounded manner. Although we assumed that the initial subsystem without the Recursion Property was decidable, we have not shown that this is also true for the expanded subsystem.

In the case of querying S's subsystem, S doesn't have the complete subsystem in hand, since he has incomplete knowledge of the base set. So, in effect, 5 must tr y to prove that, in each of S"s base sets that are consistent with S's beliefs, p is derivable. But even if we assume that individual subsystems that faithfully implement the Recursion Property are decidable, we haven't shown that the theory of a set of such subsystems is decidable, which is what is needed for S to receive an answer to [S; ]p.

We now give a formal interpretation of these issues. Let 6 be a belief subsystem for agent S characterized by a set of deduction rules R, and let 6(B) be the set of sentences deduced by the belief subsystem from a base set B. We say that 6 is decidable if 6(B) is decidable for all B. An extension of 6 is a subsystem whose deduction rules are a superset of R. Now suppose 6 is decidable, and consider the following questions:

![[Pasted image 20221205220516.png]]

We have proven the following about these questions. In general, (1) must be answered negatively, as not all subsystems are extendable. There are specific types of subsystems for which extensions satisfying (1) exist, however (e.g., if the base set contains no instances of the self-belief operator).2 If an extension exists, it is decidable. But the theory of a decidable extension is not, in general, decidable; there exist counterexamples to (3).3

Even though a complete, decidable implementation of the Recursion Property does not exist in all cases, we can find incomplete approximations. The idea is that the undec id ability results from the unboundedness of belief recursion, that is, reasoning about an agent reasoning about an agent..., in an unbounded manner. Suppose, however, we place a bound on the depth of such reasoning: as the deductions involve higher embeddings of belief subsystems, the rules become weaker, and eventually the line of reasoning is cut off at some finite depth. Belief subsystems satisfying this property are said to have Bounded Recursion. **Bounded Recursion** subsystems are a nice example of resource limitations in belief deduction.

## A propositional Deductive Belief Logic
We assume a modal propositional internal language. The logic is capable of representing belief subsystems with or without the Bounded recursion property. It is sound and complete with respect to these models.

The general model of deduction that we assume is a **block tableau sequent system**
> This is as opposed to semantic tableau and hilbert style deduction.

Block Tableaux have much in common with PLANNER-type theorem-provers, and also have nice formal properties.

Let Si be a set of (names for) agents and let L be a modal propositonal language with unary modalitieis [Si] ([Si]a means agent Si believes a)

Let capital Greek letters stand for finite sets of sentences of L (lower greek Letters stand for single sentences)

A sequent is an ordered pair of sets written as A -> B, B follows from A.

![[Pasted image 20221205221312.png]]
![[Pasted image 20221205221431.png]]
![[Pasted image 20221205221608.png]]

agent's beliefs are also beliefs; a possible-worlds model cannot take into account resource limitations that might be present in an agent's belief system. The propositional modal logic that formalizes the possible-worlds model of belief is weak 55, that is, 55 without the condition that all beliefs are true. We have proven that B reduces to this system under the following conditions:
		1. The propositioned rules r(v)) for each view v are complete, and
		2. Belief recursion is unbounded. In addition, if a modified form of B5 is used in which an agent doesn't know everything he doesn't believe, then under the same conditions B reduces to weak 54. Thus, under the assumption of deductive completeness and an infinite resource bound, the B reduces to more familiar belief logics.

4 . Conclusio n We have introduced the concept of robot belief subsystems parameterized by a finite set of base sentences and a set of deduction rules. This Deductive Belief model is a viable alternative to possible-worlds models of belief and has the attractive property of taking resource limitations into account in deriving consequences of beliefs. We have formalized the Deductive Belief model for the propositional case with the logic B, which is sound and complete with respect to our model.


# KNOWING INTENSIONAL INDIVIDUALS, AND REASONING ABOUT KNOWING INTENSIONAL INDIVIDUALS
https://www.ijcai.org/Proceedings/83-1/Papers/090.pdf

For instance, when a person perceives a physical object such as a tree , he is reall y apprehending his representation of the tree. Hence, a knowledge representation that is meant to be a component of a "mind" should not contain denotations. A more elaborate statement of thi s positio n can be found in Maida and Shapiro (1982) and the system for representing knowledge, called Lambda Net, described in the remainder of thi s paper is described in Maida (1982). For our purposes, refrainin g from representing denotations achieves two goals: 1) the problem of substitutio n of equal terms for equal terms goes away because distinc t terms are never equal; and 2) we can represent iterate d propositional attitude s without invoking a hierarchy of types.

## Lambda Net
A. Intensional Individuals

There is a class of intensional individuals for which it can be said that they have a value as seen in assertions such as:

A. What has been Achieved? A system which can reason validly about knowledge must have at least the following three per - formance characteristics :
1) The system must be able to represent assertion s involvin g iterate d propositiona l attitude s and reaso n fro m thes e assertions ;
2) The system must reac t appropriatel y t o assertion s involvin g coreferenc e between distinct intensiona l individuals ; and ,
3) The system must felicitously represent that another cognitiv e agent can know the valu e of some intensiona l indi - vidua l withou t the system itsel f necessaril y knowi n g the value . Lambda Net has these characteris - tic s jus t a s Creary' s (1979) does . However, Lambda Net offers the advantage of not invoking a hierarchy of conceptual types in order to achieve these performance characteristics .
