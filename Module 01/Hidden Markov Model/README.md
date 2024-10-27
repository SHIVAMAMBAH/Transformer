Hidden Markov Models are statistical models that are used to represent systems that are assumed to be a Markov process with unobserved (hidden) states. HMMs are particularily useful in various fields such as speech recognition, bioinformatics and finance, where the system being modeled is not directly observable.

### Components of the HMMs
1. **States** : A set of hidden states *S*  = {s<sub>1</sub> , s<sub>2</sub> , ...., s<sub>N</sub>}.
2. **Observation** : A set of observable sybmols *O* = {o<sub>1</sub>, o<sub>2</sub>, ...., o<sub>M</sub>}
3. **Initial State Distribution** : A probability distribution over the states, denoted as &pi; = {&pi;<sub>i</sub>}, where &pi;<sub>i</sub> = *P*(q<sub>1</sub> = s<sub>i</sub>).
4. **State Transition probabilies** : A matrix A = {a<sub>ij</sub>} where a<sub>ij</sub> = P(q<sub>t+1</sub> = s<sub>j</sub> | q<sub>t</sub> = s<sub>i</sub>) represents the probability of transitioning from state s<sub>i</sub> to state s<sub>j</sub>.
5. **Emission probabilities** : A matrix *B* = {b<sub>ij</sub>} where b<sub>ij</sub> = P(o<sub>t</sub> = o<sub>j</sub> | q<sub>t</sub> = s<sub>i</sub>) represents the probability of observing o<sub>j</sub> given that the system is in the state s<sub>i</sub>.

### Example
Consider a simple weather model where the hidden states are "Sunny" and "Rainy" and the observations are "Walk", "Shop", and "Clean".
1. **States** : *S* = {Sunny, Rainy}
2. **Observations** : *O* = {Walk, Shop, Clean}
3. **Initial State Distribution** : &pi; = ColumnVector(0.8 0.2) (80% chance of starting in Sunny, 20% in rainy0
4. **State Transition Probabities** : *A* = Matrix([0.7 0.3], [0.4 0.6]) (70% chance of staying Sunny, 30% of transitioning to rainy, 40% chance of transitioning to Sunny from rainy and 60% of staying rainy)
5. **Emissin probabilities** : *B*  = Matrix([0.6 0.3 0.1], [0.1 0.4 0.5]) (given Sunny, 60% chance of walk, 30% chance of shop, 10% of clean, given rainy, 10% chance of Walk, 40% of shop, 50% of Clean)
