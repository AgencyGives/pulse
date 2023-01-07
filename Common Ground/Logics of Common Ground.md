According to Clark’s seminal work on common ground and grounding, participants collaborating in a joint activity rely on their shared information, known as common ground, to perform that activity successfully, and continually align and augment this information during their collaboration.

Indeed, without appropriate information being shared, using agent autonomy to reduce the workload on humans may actually increase workload as the humans seek to understand why the agents are behaving as they are.

Common ground is an important part of human interaction, and establishing common ground can lead to more efficient interactions; e.g. in conversations (Lee, 2001) and in teamwork.

**Grounding** is the term used for the process by which people establish a mutual understanding through their collaborative efforts to make their meanings intelligible to each other.

The grounding process can be understood as accumulating the participants’ common ground: that is, the participants gain and incrementally accumulate representations of the information that they share and believe that they share.

**Salient common ground (Section 5):** The final logic defines a new notion of common ground, which we call salient common ground. Salient common ground determines the common ground of a context, but considers that individuals partaking in a joint activity will base their interaction on activity-specific common ground as well as on the common ground that existed before the activity commences — that is, their personal or communal common ground. Our notion of salient common ground brings these together. For example, the personal preferences of the operator shared through personal common ground might be adjusted in a particular context and therefore become part of activity-specific common ground, which is reflected in salient common ground. Our logic for salient common ground builds on our logic for context-dependent common ground.

The composition of different sources of common ground is not a simple conjunction of the common ground from groups and activities, because this conjunction may be inconsistent. **Activity-specific information that contradicts generalised common ground may be required to successfully complete a joint activity, so it is natural that activity-specific common ground is given priority over personal and communal common ground in joint activities.** 

**Accordingly, we define salient common ground so that activity-specific common ground overrides any generalised common ground that is inconsistent with the activity-specific common ground.**

For example, the two pilots may have personal common ground that operating procedures (communal common ground) are not efficient, so they draw on their personal common ground when operating as a pair, giving their personal common ground a higher precedence.

## Section 3

**Definition 3 (Acceptance).** Hakli (2006) defines acceptance of a proposition ϕ as: “a kind of mental act, a decision to treat ϕ as true in one’s utterances and actions, or an act of adopting a policy to use ϕ as a premise in one’s theoretical and practical reasoning. This is usually taken to include assuming ϕ for the sake of some practical purpose, pretending that ϕ is true or acting as if ϕ were true, because it is usually allowed that one can simultaneously accept that ϕ and believe that not ϕ” (p. 288).

Acceptance and belief represent similar mental attitudes, but they need not be consistent with each other. Importantly, one can accept a proposition without believing it. This is generally done to achieve some goal. Gilbert (2002) defines the canonical example of acceptance as being: “a case of assuming something ‘for the sake of the argument’, or ‘for present purposes’ ” (p. 38), while Engel (1998) asserts that “Acceptance aims not at truth, but at utility or success. In this sense it is a pragmatic notion, not a cognitive or theoretical one.”; and further, that acceptance is “voluntary or intentional, unlike belief ” (p. 148)

#### Awareness
Definition 4 (Awareness). We define awareness of one’s acceptances (and non-acceptances) as the property of holding a belief about one’s acceptances; that is, if an agent accepts (does not accept) a proposition, then that agent believes that it accepts (does not accept) that proposition: Aiϕ → BiAiϕ and ¬Aiϕ → Bi¬Aiϕ.

**As noted by several philosophers (e.g. see the work of Engel, 1998; Gilbert, 2002), accepting a proposition is a conscious act; a decision that is taken.** Therefore, it is reasonable to model that if an agent consciously decides to accept ϕ, the agent is aware that this act has occurred, and as a result, it should believe that it accepts ϕ. This definition of awareness should not be confused with Fagi

### Collective Acceptance
We define collective acceptance (common ground) as: “There is a collective acceptance of a proposition ϕ in a group if and only if there is common belief that all members of that group accept that ϕ.” Thus, our definition does not explicitly require that everybody accepts ϕ, but it implies this (see Theorem 5).

The definition of collective acceptance is quite different to that of common belief. First, collective acceptance is not an infinitary conjunction of everybody accepting something, and everyone accepting and everyone accepting, etc. Instead, it is defined as being common belief that everyone accepts something. Thus, the notion of common belief plays an important role in the definition, and further, is the part of the definition that captures the infinitary nature of collective acceptance.

Second, collective acceptance is a non-summative type of group belief as it does not imply corresponding individual beliefs, even though collective acceptance can be reduced to individual mental attitudes.

Like common belief, collective acceptance has an infinite regress property: collective acceptance, shared belief in collective acceptance, and common belief in collective acceptance, are all equivalent.

## Semantics
Semantically, common belief and collective acceptance are defined through the union of possible worlds that are reachable by context-independent accessibility relations for belief and acceptance of the individual members of the group.

When a subgroup is considered, the union of possible worlds is smaller and therefore the common beliefs and collective acceptances of the subgroup contain at least the same sentences as the common beliefs and collective acceptances of the supergroup. In the case of activity-specific, generalised, and salient common ground, considering a subgroup instead of a supergroup also changes the accessibility relations that need to be considered. **Hence, there is no logical relationship between the context-dependent or salient common ground of a group and its subgroups**

Using the logic of acceptance defined above, we can define this formally as:

CAGϕ ↔ CBGEAGϕ

Here, we see a divergence of the symmetry that existed between belief and acceptance so far. In the case of collective acceptance, it is not enough for everyone to accept that ϕ, and everyone accept that everyone accept that ϕ, ad infinitum. Instead, there must be a common belief that everyone accepts ϕ.

## Limitations
In our logics, we have chosen to model information such as group membership and salient groups of an activity as part of the model. That is, if an agent is in a group, it is commonly known that this is so; and the definition of Y (α) is also commonly known. Another approach would be to insist that, for example, a proposition ϕ is only communal common ground in a group G if it is activity-specific common ground between the participants of the joint activity that G is indeed salient. This could be modelled by introducing propositions such as salient(G, α) to indicate that group G is salient in α. While such a model is closer to reality, we opted to include this as part of the Kripke model; first, to be consistent with existing modal logic formalisms, and second, because the aim of the paper is to share formal definitions of common ground, and such detail may over-complicate the definitions for readers. If we include propositions like salient(G, α) in our possible worlds, then there is a further argument that we should also include all other parts of the model as propositions, such as the constraints on accessibility relations, the mapping of agents to accessibility relations, etc. However, such a definition would be over-complicated for its purpose.

### this opens the door for **computational representations of cultural transmission of information.**

The definition of common belief using an infinite formula, which we have done in this article, has raised fair objections from others, such as Allan (2013). This is discussed in detail in Section 2.7. Similarly, as with other epistemic logics, the problem of logical omniscience — an agent believes (accepts) all theorems and all deductive consequences of its beliefs (acceptances) — is a consequence of our definitions. **Clearly, such assumptions could be dropped to make the model more ‘realistic’,** however, in our opinion, these idealisations do not impair the value of the model as a tool for making distinctions explicit or as a starting point for more concrete instantiations.

## Insights
Our model suggests refinements of existing work. In related work, salient and contextdependent common ground were not clearly separated (Kashima et al., 2007). **We carefully distinguish between the different components of salient common ground**;

**for example, the source of any proposition in salient common ground (activity-specific, personal, or communal common ground).**

**Our model shows that this is necessary to make a distinction between what has been shared (in the sense of exchanged) in the current interaction (activity-specific common ground) and what is shared because of different common grounds (salient common ground), including activity-specific common ground.**

Further to this, with the assumption that agents believe that they accept their acceptances, we are able to provide a simplified definition of collective acceptance and prove its equivalence to Tuomela’s and Stalnaker’s definitions.

### On the link between actual and perceived common ground
Using our model, we define perceived common ground from an individual perspective as individual belief about common ground, and then prove that if a group all have the same perceived common ground, this will be actual common ground, **thus demonstrating a link between perceived and actual common ground.**

The presuppositions of an individual can be different from actual common ground, and such a case requires at least one member of the group to have a false belief. However, if a group of agents have equivalent presuppositions, then their perceived common ground is consistent with actual common ground.

### Meta-point
As a final discussion point, our definition of salient common ground proved useful as a tool for grounding within our group itself, with the formalism helping us to identify inconsistencies of our understandings. That is, we did not have a common ground on the definition of common ground, even though we perceived that we did. **The formalism allowed us to ground this definition correctly by identifying what was perceived and actual common ground.**

> Perceived vs actual common ground of formulas... We can have common ground about a function in a context...




### Addressing Resource Boundedness

**Theorem 2 (Infinite regression of common belief)**

This theorem comes from our definition of common belief using an infinite formula. Such definitions have been criticised in the past due to the fact that they require “infinite processing” (Allan, 2013). This criticism is valid, and we could opt for a definition that does not require an infinitely-long definition by, in effect, limiting the depth to which belief is followed before common ground is achieved, similar to the definition proposed by Allan. This could be done **by e.g. limiting 1 ≤ k ≤ 3 in the definition of CGG**. Such a definition would imply that the three properties of infinite regression in Theorem 2 hold only from right to left.

Co-present observations — that is, observations of some phenomena when a group is physically located in the same place — can lead to common knowledge/belief (Clark & Marshall, 2002). In such a situation, it is straightforward for an artificial agent to assert CBGφ as a sentence in its knowledge base without having to reason about the underlying infinite formula. Any query involving arbitrarily long nestings of belief could be answered using this sentence.

Similarly, it seems reasonable to assert that a human in a **co-present situation** would add common belief without reasoning about the underlying formula, whether this underlying formula is infinite or not. That is, for a human to add a belief that something is common ground, they would not explicitly reason about this up to some depth k, **but would merely accept the sentence itself.**

So, using the infinite definition provides a more expressive language, while still allow one to define a non-infinite version of “common” belief as simply e.g. EBGφ∧EB2 Gφ∧EB3 Gφ; although the definition of common ground according to Allan (2013) is more involved than this.

