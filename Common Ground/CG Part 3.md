## Salient Common Ground

> Salience is a form of conflict resolution

The context-dependent common ground presented in the previous section allows us to reason about individual and collective acceptance in particular contexts, **however, it does not allow us to reason about the acceptances of individuals or groups over multiple contexts together, considering the specific social constellation of the context.** That is, a group partaking in a joint activity may rely on the activity-specific common ground of that activity, but also on their existing communal and personal common ground.

#### Salient:  mutually recognised to be shared

Our analysis builds on the observation that in any human social interaction, a number of shared group memberships will be salient, i.e. mutually recognised to be shared.

**The salience of group memberships determines the groups whose communal common ground is considered by the individuals in the interaction.** For example, two Anglo-Australians could interact with their English group membership or their Australian group membership being salient, or both for that matter. This is in line with the broader ideas of social identity theory (Tajfel & Turner, 1979) and self-categorisation theory (Turner, 1982), according to which different social identities are salient during any social interaction. Indeed, there is evidence that the effect of perceived group membership on conversation might very well be mediated by social identities (Shintel & Keysar, 2009).

In this section, we define the notion of salient common ground by extending our logic LAC to a new logic LCG. **This is done by introducing and formalising the concept of salient acceptance — those individual acceptances that are important in a given activity.**

**Salient common ground is then defined as the collective acceptance of these salient acceptances.**

**It is important to note that salient acceptance, and as a result salient common ground, are not simple conjunctions of the acceptances of multiple contexts, because these acceptances may conflict with each other. As such, salient acceptance is a satisfiable collation of the acceptances from the different contexts, in which the acceptances specific to the current activity receive priority over the acceptances from personal and communal common ground. Further, we introduce the notion of precedence among group contexts, so that if the acceptances from two groups conflict, the higher-precedence group’s acceptances are adopted, while the others are removed from the scope of the salient common ground.**

## 5.1 
We define salient common ground in a similar spirit, including the information relevant to the current activity (activity-specific common ground), mutual information between participants (personal common ground), and broader common ground (communal common ground). Salient common ground is defined relative to an activity, similar to activityspecific common ground. That activity takes precedence over all other contexts, in cases where there is conflicting information. We also consider precedences between all contexts in personal and communal common ground.

**We define a context as salient to an activity if it is mutually recognised that the common ground from that context forms part of the background information used as part of that activity**.

Further, a context is **more salient** than another if the common ground in that context is considered to be more relevant or important to the particular activity. For example, treaties of international law would likely be considered more salient in most contexts than procedures for handover to a new controller, as the former would take precedence over the other.

## Set of salient contexts and the precedence relation between contexts
**Thus, the set of salient contexts and the precedence relation between contexts are both themselves part of the common ground, although for simplicity, we do not model them as such (see the discussion on limitations in Section 6).**

## salient common ground informal definition
The salient common ground of a joint activity is: (i) the activity-specific common ground of that activity, conjoined with (ii) the common ground of all the groups whose membership is salient in that activity that does not conflict with (i) or with the common ground of any higher precedence salient group in that activity.

That is, the salient common ground is the activity-specific common ground for that activity, and the generalised common ground (personal and communal) that the group bring to that activity from their group contexts, provided that this generalised common ground does not result in conflicting information. If there is conflicting information, then the group that is “more salient”, as defined by some relation among groups, takes precedence.

This definition implies that the common ground in the current context (the activity) has a higher precedence than the generalised common ground. **As a result, the composition operator through which salient common ground arises is not conjunction.** The conjunction of activity-specific, personal, and communal common ground might be inconsistent, and **in our definition, the common ground of an activity overrides personal or communal common ground.**

**This design choice is due to empirical observations about how people derive their common ground.**

Activity-specific common ground is generally **shorter-term** and more recent than generalised common ground, as observed by Kashima et al. (2007).

### So common ground has a temporal qualty... the tme of the actvty... ongong or stopped

As a result, generalised common ground is “in place” when an activity starts, and anything that is accepted during the activity must take precedence, **otherwise it would not have been added.**

For ¬ϕ to become activity-specific common ground, the participants in the joint activity must mutually recognise their acceptance of ¬ϕ for the purpose of progressing this interaction. If the common ground of ϕ from generalised common ground is more important than the activity-specific common ground, then the participants would not accept ¬ϕ as part of the interaction. **Of course, there may be possible misunderstandings, meaning that individual acceptances deviate from what has been shared, but in these cases, common ground is not agreed upon: the perceived common ground is not consistent with the actual common ground.**

While it may be possible to find exceptions to this, we assert that giving activity-specific common ground a higher precedence than personal or communal common ground is a well justified model of how the different types of common ground relate. Further, in our logic, this assumption is straightforward to relax.

*We acknowledge that there are approaches to communication where achieving, for example, plausible deniability rather than common ground is the objective, e.g. see the work of Pinker, Nowak, and Lee (2008) — and in such circumstances different relationships may apply between the forms of common ground, but such analysis is out of scope here.*

To illustrate the types of settings where our assumptions are appropriate, we return to the example from Section 4.8 of a child born in a country to foreign parents. If a child is born in Australia to British parents, they may interact with their family using their common ground of being British, and with their school friends using their common ground of being Australian. However, if such a child interacts with another child of Anglo-Australian heritage, their interaction may use the combination of these two common grounds. As an example, in their family group, they may accept that imperial measures are used for measurement, while at school with their Australian friends, they would accept that metric is used. If two Anglo-Australians come together, their common ground may instead be that both can be used, or that it does not matter. If they then partake in a joint activity of measuring distance as part of a school project, they would be required to use the metric system, and this would be part of activity-specific common ground. However, after using it together over several activities, it may become part of their personal common ground that metric should be used.

Our robotic example from Section 4.8 offers an apt illustration as well. The communal common ground of an autonomous aerial vehicle and its operator may consist of knowledge such as operating procedures, and rules for undertaking certain tasks. In addition, they may share personal common ground from previous missions; for example, the vehicle may have learnt about certain preferences of the operator. Then, in the context of a search and rescue activity, new common ground about that activity is derived, such as the area to be searched. The salient common ground then brings together the relevant, non-conflicting factors. Information about operating procedures and the area to be searched may in fact interact, as the area to be searched may be influenced by operating procedures. Therefore, deriving the salient common ground in this activity is useful.

**Y (α) is the set of nonempty groups that are salient in that activity**

**Distribution for the common ground operator:**
CGα(ϕ → ψ) → (CGαϕ → CGαψ)

## 5.2
We extend the syntax of the logic LAC to include an operator for individual acceptance pooled over multiple contexts, individual salient acceptance, shared salient acceptance, and an operator for salient common ground. The use of precedence in contexts is important in these definitions. To represent precedence, **we introduce precedence relations over contexts**. The set O is the set of all strict total orders, (D, ), such that D ⊆ C is a non-empty subset of the set of all contexts. The term c  d specifies that context c has a higher precedence than context d. If O ∈ O, then O  c denotes a new ordering that extends O to include c as the lowest precedence context.


SAO i ϕ specifies that ϕ is saliently accepted by agent i by combining all contexts in O, except those those contexts that conflict with some higher-precedence context.

P AO i ϕ specifies that agent i accepts ϕ over a pooled set of contexts D, where O = (D, ). In essence, it is the same as SAO i , except that it ignores the precedence relation and pools together contexts irrelevant of whether they conflict or not.

CGαϕ specifies that ϕ is salient common ground for the activity α.

As a shorthand, we use ESAαϕ to specify that everybody saliently accepts ϕ in activity α (shared salient acceptance).