Markov Chains are mathematical systems that undergo transitions from one state to another state within a finite or countable number of possible states. They are characterized by the Markov property, which states that the future state of the process depends only on the current state and not on the sequence of events that preceded it. This property is often referred to as "memorylessness".

### Key components of the Markov Chains
**1. States** : The different conditions or positions that the process can be in.   
Let S = {s<sub>1</sub>,s<sub>2</sub>,s<sub>3</sub>, .... s<sub>n</sub>} be the set of states.  
**2. Transition Probabilities** : The probabilities of moving from one state to another.  
The transition probability from state s<sub>i</sub> to state s<sub>j</sub> is denoted by P<sub>ij</sub>,   
where: P<sub>ij</sub> = P(X<sub>n+1</sub> = s<sub>j</sub> | X<sub>n</sub> = s<sub>i</sub>), X<sub>n</sub> represent the state at any time n.  
**3. Transition Matrix** : The transition probablities can be organized into a matrix P, where the entry P<sub>ij</sub> represents the probability of transitioning from state s<sub>i</sub> to state s<sub>j</sub>. The matrix P must satisfy the following conditions:
- Each entry is non-negative : P<sub>ij</sub> >=0.
- The sum of probablities from any state must equal 1 : &Sigma;<sub>j</sub>P<sub>ij</sub> = 1 for all i.


> Transition probability means the likelihood of moving from state to another in a stochastic process. It is defined as the probability of transitioning from the state Si to Sj in one time step.
