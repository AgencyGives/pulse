http://davidjaz.com/Talks/DJM_Dyn2020.pdf

Give a formal defintion of dynamical system doctrine, and define their 2-category.

Define a dynamical system in a given doctrine, and describe ways to compose them by plugging variables into parameters, and describe maps between them.

Prove that the trajectories, steady states, and periodic orbits of coupled dynamical systems compose via matrix arithmetic, generalizing Spivak, *The steady states of coupled dynamical systems compose according to matrix arithmetic.* 
- From the way the systems are coupled, you find a matrix. 
- Multiplying the vector of steady states of the constituent systems by this matrix gives the vector of steady states of the whole system. 
- We do this with representable indexed double functors.

In a determinisitic automaton (discrete, continuous, measurable), where the dynamics is given by specifying the next state as a function of the current state.
- The next state may depend on an **input** **symbol** — a parameter.
- Each state may expose an **output** **symbol** – a variable of the state

In full, a deterministic automaton consists of an **input alphabet I**, **an output alphabet O**, a set (or space) of states S, and two functions:
- An update function u : S × I → S, and A readout function r : S → O.
- These are continuous, smooth, or measureable, according to taste.