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
V<sub>0</sub> = [ 1 0 ]<br>
This vector indicates that there's a 100% probability that the current whether is Sunny and therefore a 0% probability it is Rainy.
#### Calculate the State Vector for the Next Day (Day1)
To find the weather probability for the next day, we multiply the initial state vector by the transition matrix : <br>
<div align = "center">V<sub>1</sub> = V<sub>0</sub>.<i>P</i></div>
After multiplying we will get V<sub>1</sub> as [0.7 0.3]<br>
So, on the first day<br>
(1) Probability of it being Sunny (S) = 0.7<br>
(2) Probability of it being Rainy (R)  = 0.3<br>

#### Calculate the State Vector for the Day next After (Day 2)
Now we calculate the state vector for the following day<br>
<div align = "center">V<sub>2</sub> = V<sub>1</sub>.<i>P</i></div>
After multiplying we will get V<sub>2</sub> as [0.55 0.45]<br>
So, on the first day<br>
(1) Probability of it being Sunny (S) = 0.55<br>
(2) Probability of it being Rainy (R)  = 0.45<br>

### Application of Markov Chains
**1. Machine Learning and Artificial Intelligence**
- Natural Language Processing (NLP): Markov chains are foundational in language models for tasks like text prediction, language generation, and spell-checking. While deep learning has advanced NLP, Markov-based models (e.g., Hidden Markov Models) are still used for simpler tasks or when interpretability and lower computational cost are needed.
- Reinforcement Learning: Markov Decision Processes (MDPs), a generalization of Markov chains, are fundamental in reinforcement learning, helping train agents to make decisions in games, robotics, and self-driving cars.
Speech Recognition and Generation: Applications like virtual assistants, voice recognition, and chatbot speech generation still use Markov models, especially Hidden Markov Models (HMMs), for probabilistic state transitions.<br>

**2. Financial Modeling and Economics**
- Stock Market and Option Pricing: In finance, Markov chains help in modeling stock prices, credit ratings, and economic state transitions (e.g., from boom to recession). Their ability to predict changes in financial states and risk over time makes them invaluable for risk management and investment strategies.
- Algorithmic Trading: Many trading algorithms use Markov chains to predict short-term price trends, enabling high-frequency and quantitative trading strategies.<br>

**3. Recommendation Systems**
- Content Recommendations: Websites like YouTube, Netflix, and Amazon use variations of Markov models to recommend content by predicting the next probable item a user might engage with, based on previous interactions.
- Product Recommendations: In e-commerce, Markov chains analyze user browsing and purchasing history to suggest products that users are likely to buy next.<br>

**4. Healthcare and Genomics**
- Patient Health Modeling: Markov chains model patient health transitions, helping predict disease progression and treatment outcomes (e.g., in chronic diseases or cancer stages).
- DNA and Protein Sequencing: In bioinformatics, Markov models analyze DNA sequences, protein structures, and evolutionary patterns, providing insights into genetics and heredity.<br>

**5. Internet and Social Media Analysis**
- Search Engine Algorithms (e.g., Google PageRank): Google's PageRank uses a Markov process to rank websites based on their importance and link structure. It’s a key component in how search results are prioritized.
- Social Media Behavior Modeling: Platforms analyze user interactions and transitions (e.g., likes, shares, follows) using Markov chains to predict user behavior and recommend content.<br>

**6. Robotics and Autonomous Systems**
- Navigation and Path Planning: In robotics, Markov chains help map environments and determine the best paths, factoring in probable transitions from one state or location to another.
- Robot Decision-Making: For instance, cleaning robots may use Markov chains to decide the next area to clean based on current location and probable dirt accumulation.<br>

**7. Computer Networks and Cybersecurity**
- Network Traffic Prediction: Markov chains model network traffic patterns, helping optimize data transmission, reduce latency, and manage bandwidth.
- Anomaly Detection in Security: Markov models identify unusual patterns in user activity that might indicate a security breach or cyber attack.<br>

**8. Operations and Supply Chain Management**
- Inventory Control: Markov chains model inventory levels and demand patterns to optimize stock levels, reducing shortages and overstock situations.
- Logistics and Transportation: They’re used to predict vehicle or shipment locations in logistics, optimizing delivery times and routes based on state transitions.<br>

**9. Entertainment and Gaming**
- Game Development: Markov chains model character behavior and scene progression, helping make NPC (non-player character) actions realistic and unpredictable.
- Procedural Content Generation: In games, Markov chains generate levels, music, and character dialogues in ways that are dynamically influenced by player actions.<br>

**10. Weather Forecasting and Climate Modeling**
- Weather Prediction: Markov chains can predict short-term weather patterns based on current atmospheric conditions, used in meteorology to forecast day-to-day changes.
- Climate Modeling: They help simulate climate changes over time, analyzing transitions between different climatic states (e.g., El Niño and La Niña).
