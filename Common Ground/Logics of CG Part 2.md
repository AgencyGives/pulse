### 4. Context-Dependent Common Ground

**individuals** engaging in a joint activity will communicate information specific to the activity, generating **activity-specific common ground**

**groups** in which the individuals know each other for some extended time, and partake in joint activities over that period, they would extend (i.e. generalise) their activity-specific common ground to become what Clark (1996) calls **personal common ground** - the knowledge, belief, and acceptances that are mutually shared by the group, independent of any particular joint activity and not re-established each time they partake in an activity.

However, if a **group** share an understanding that they have reason to believe is shared by a larger group other than themselves, this understanding may be **communal common ground**.

In **communal common ground**, individuals treat information as common ground based on some common group membership, such as their nationality, affiliation to a particular organisation or political party, occupation, education, recreational activities, or ethnicity, despite not knowing each other and having no reason to believe that someone accepts a proposition except that they belong to that group.

In this section, we formalise the notions of personal and communal common ground according to Clark (1996), and the notion of activity-specific common ground according to Kashima et al. (2007). All three are defined as collective acceptance, similar to that in Section 3, **except that the acceptances of individuals are indexed relative to the particular context, in which a context is a (possibly joint) activity, or a group (for personal and communal common ground).** We refer to the collective of these three types of common ground as context-dependent common ground. This formalism is a logic, LAC, which is a modification of the logic LA from Section 3.

Using the above syntax, the concept of personal common ground and communal common ground (defined as collective acceptance) are treated the same, and it is the identification
of the group label as referring to a personal or communal group that determines which type of generalised common ground it is. **The reason for treating joint activity and group contexts equivalently is that we follow Kashima et al. (2007) in assuming that activity-specific, personal, and communal common ground are technically equivalent, apart from the different type of context they are associated with. Any further characterisation of the term “context”, however, is beyond the scope of this paper.**

It is important to note that group and joint activity contexts **are not** groups or joint activities, but are instead labels that individuals use to refer to the contexts. From the perspective of social category learning (Kashima, Woolcock, & Kashima, 2000), **context labels can be understood to play the role of cues to access and retrieve associated information stored in memory, e.g. context-specific acceptances**.

Kashima et al. (2007, pp. 34–36) describe how common ground is constructed with respect to a **collective identity** — the identity of a collective (not the identity of an individual as a member of this collective).
- In the case of activity-specific common ground, this collective identity might be indexically specified, denoting the individuals taking part in the activity.
- This collective identity might be generalised to an interpersonal relationship (giving rise to personal common ground)
- or to an imagined collective (giving rise to communal common ground), whereby an **imagined collective** is a collective of individuals that do not interact synchronously with each other, e.g. a social group.
We represent collective identity by a group or joint activity context label respectively.

Later in Section 5 we define salient common ground as the common ground that is obtained in a joint activity through a combination of activity-specific, personal, and communal common ground. **In that case, the collective identity is created from a multi-valued context label.**

**The interpretation of context as a label should be kept in mind by the reader although we interchangeably talk about contexts as labels and contexts as groups or joint activities**


### 4.6
However, it is important to note that the axioms for acceptance are indexed by both the individual and the context. For example, the axiom for positive introspection is:

### 4.7
From our assertion that the axiomatisation is a straightforward mapping from the logic LA, it follows that the properties of distribution, consistency, positive introspection, and negative introspection all hold for the context-dependent group acceptance operators. However, one property that does not hold is the property regarding subgroups.

Theorem 9 (Subgroup acceptance does not hold in LAC). 

This can be demonstrated by constructing two accessibility relations for two contexts in which there is a world such that an agent accepts ϕ in one context and ¬ϕ in the other context.

## 4.8 
Context-dependent common ground is not the same as simply modelling two different groups with different common ground, because individuals can accept conflicting propositions in different contexts. In fact, Theorem 9 shows that a group can have conflicting collective acceptances between an activity and a group context, even if the two groups involved are the same individuals. For example, for a group G partaking in a joint activity α, the following can hold:

CAαϕ ∧ CAG¬ϕ

even though X(α) = G, because each individual has different accessibility relations for the contexts α and G.

As an example of this, consider a person born in a country to foreign parents. If parents have a particular affinity to their home land, this will often be passed to their children. The children may accept that customs are done in a particular way when they are in a home context with their parents, and this could form the personal common ground within their family group. However, when they are in a different context, such as with their friends at school, their acceptances about those customs may change to fit in with their local community

A similar example can be made with respect to the joint activity of human teleoperators working with a semi-autonomous unmanned aerial vehicle to perform search and rescue. The vehicle may accept that a certain region of the search space is empty and may report on this, forming new common ground between the vehicle and the analysts reading the report. However, under command from the human operator, the vehicle may accept that the region is non-empty in order to enact a plan for exploring that region, thus forming common ground between itself and the operator that is different to the common ground of the reporting context. The two different contexts, reporting and exploring, have different individual acceptances so that the planner in the vehicle can derive plans consistent with what it believes is common ground (yet does not believe), but can also report information that conflicts with this in a different context.

The lack of subgroup acceptance as a theorem demonstrates the clear difference between context-dependent common ground, and more general definitions that do not consider context. Following Kashima et al. (2007), we consider context to function similarly to a label for a collective identity, which is either specifying the participants of a joint activity or a social group (refer to the discussion in Section 4.2). The relationship of context and common ground is important, as it allows an agent participating in more than one context to hold conflicting acceptances in those contexts, i.e. in different joint activity and social group contexts; and in participating in some activity, participants come into the activity with some prior common ground, **some of which is believed to be common ground by the participants, and some of which must be discovered to be common ground.**

While one could argue that the collective acceptance of a group must imply that of the subgroup, as is done in Lorini et al. definition of collective acceptance (Lorini et al., 2009), we assert that for common ground, this is not necessarily the case. As an example, consider again the family from above, with F = {mother, father, daughter, son}. For the purpose of a peaceful family life, they might have established the common ground CAF ϕ that travelling to the same holiday destination every year is great. At the same time, the subgroup K = {daughter, son} might have established the common ground that this is actually not that great after all: CAK¬ϕ. The contexts here are precisely the groups, not a joint activity, and yet this demonstrates a valid situation in which subgroup acceptance does not hold.

### While subgroup acceptance does not hold, we could analyse a related property, which follows from CA, EA, and CB:
CAGϕ → CBG'EAGϕ
Any subgroup G' of a group G commonly believes that the individuals in G individually accept ϕ.

As discussed in Section 4.2, when describing collective acceptance, we collapse the indices for group and context in the sense that the group index G of a collective acceptance CAGϕ fully determines the context index of the enabling individual acceptances AG i . This is consistent with ideas by Kashima et al. (2007), who note that common ground is indexed relative to a particular context, and common ground arising from a joint activity can be temporally extended to personal common ground if the group members interact repeatedly, or even grounded to communal common ground of an imagined collective, which is imagined to exist beyond the particular activity or personal group. In these cases, the common ground is the same, but what changes is the context, from activity-specific, to personal or communal common ground. Lorini et al. (2009), on the other hand, retain the distinction between group- and context-indices in collective acceptance, and therefore subgroup acceptance follows naturally from this.