We construct logical languages which allow one to represent a variety of possible types of changes affecting the information states of agents in a multi-agent setting. We formalize these changes by defining a notion of _epistemic program_. The languages are two-sorted sets that contain not only sentences but also actions or programs. This is as in dynamic logic, and indeed our languages are not significantly more complicated than dynamic logics. But the semantics is more complicated. In general, the semantics of an epistemic program is what we call a_program model_. This is a Kripke model of ‘actions’,representing the agents' _uncertainty about the current action_ in a similar way that Kripke models of ‘states’ are commonly used in epistemic logic to represent the agents' _uncertainty about the current state_ of the system. Program models induce changes affecting agents' information, which we represent as changes of the state model, called _epistemic updates_. Formally, an update consists of two operations: the first is called the update map, and it takes every state model to another state model, called the _updated model_; the second gives, for each input state model, a transition relation between the states of that model and the states of the updated model.

Each variety of epistemic actions, such as public announcements or completely private announcements to groups, gives what we call an _action signature_, and then each family of action signatures gives a logical language. The construction of these languages is the main topic of this paper. We also mention the systems that capture the valid sentences of our logics. But we defer to a separate paper the completeness proof.

The basic operation used in the semantics is called the _update product_. A version of this was introduced in Baltag et al. (1998), and the presentation here improves on the earlier one. The update product is used to obtain from any program model the corresponding epistemic update, thus allowing us to _compute_ changes of information or belief. This point is of interest independently of our logical languages. We illustrate the update product and our logical languages with many examples throughout the paper.