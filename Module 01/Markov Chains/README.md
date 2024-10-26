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


> Transition probability means the likelihood of moving from state to another in a stochastic process. It is defined as the probability of transitioning from the state S<sub>i</sub> to S<sub>j</sub> in one time step.

> A stochastic process is a mathematical model used to describe a system that evolves over time in a way that involves randomness. In other words, a stochastic process is a collection of random variables, each representing the state of a system at different points in time.<br>
> Key characteristics of Stochastic processes :
> - **Randomness** : The future of the state of the process has some degree of uncertainty, often influenced by probabilistic factors.
> - **Time Dependence** : The process evolves over timem so it has different states at different times.
> - **State Space** : The set of all possible states that the process can be in. This can be discrete or continues.
> - **Indexing by Time** : The process can be indexed by time *t*, which may be continuous or discrete.

P<sub>ij</sub>  = number of tranitions from state S<sub>i</sub> to state S<sub>j</sub> / total number of transition from the state S<sub>i</sub>


### Problem Statement
Imagine we want to predict the weather for a given day, knowing that : 
- If it's sunny on a given day, there's a 70% chance that it will be sunny the next day and a 30% chance it will be rainy.
- If it's rainy on a given day, then there's an 80% chnace that iw will continues to be rainy the next day and a 20% chance that it will be sunny.

Given the Current whether is sunny, what is the probability that it will be sunny or rainy on each of the next two days?
### Solution
#### Define the States
In this problem, we have two states
- Sunny (S)
- Raint (R)
These states represent the type of weather for each day.
#### Define the Transition probabilities
- If the current day is Sunny (S)
  - Probability it will be Sunny (S) the next day  = 0.7
  - Probabilit it will be Rainy (R) the next day = 0.3
- If the current day is Rainy (R)
   - Probability it will be Rainy(R) on the next day = 0.8
   - Probability it will be Sunny(S) on the next day = 0.2
We can represent this as a transition matrix (P) :<br>
        P = | 0.7 0.3 |<br>
            | 0.2 0.8 |<br>
Each row of this matrix represents the transition probabilities from the current state to the next state.

#### Define the Intial State vector
Let's us assume the current weather is Sunny. We can represnt this as an intial state vector V<sub>0</sub>.<br>
V<sub>0</sub> = | 1 |<br>
                | 0 |
