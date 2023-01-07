In previous work we presented a foundational calculus for spatially distributed computing based on intuitionistic modal logic. With the modalities □ and \Diamond\Diamond we were able to capture two key invariants: the mobility of portable code and the locality of fixed resources. This work investigates issues in distributed control flow through a similar propositions-as-types interpretation of classical modal logic. The resulting programming language is enhanced with the notion of a network-wide continuation, through which we can give computational interpretation of classical theorems (such as [] A º \lnot \Diamond \lnot A\Box A \equiv \lnot \Diamond \lnot A). Such continuations are also useful primitives for building higher-level constructs of distributed computing. The resulting system is elegant, logically faithful, and computationally reasonable.