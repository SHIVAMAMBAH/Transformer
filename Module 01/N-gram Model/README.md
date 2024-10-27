The N-gram model is a statistical language model used to predict the next item in a sequence (such as the next word in a sentence) based on the previous N-1 items. It is widely used in NLP tasks, such as text generation, speech recognition, and machine translation.
### Definition
An N-gram is a contiguous sequence of N items (words, characters, etc.) from a given sample of text or speech. The model is defined as follows : 
- **Unigram (1-gram)** : Consider individual words.
- **Bigram (2-gram)** : Consider pairs of consecutive words.
- **Trigram (3-gram)** : Consider triplets of conosecutive words.
- **N-grams** : Generalized to any N.

### Mathemtical representation
The probability of a sequence of words W = w<sub>1</sub>, w<sub>2</sub>, ..., w<sub>T</sub> can be expressed using the chain rule in probability :  
*P(W)* = *P(w<sub>1</sub>)* . *P(w<sub>2</sub>|w<sub>1</sub>)* . *P(w<sub>3</sub>|w<sub>2</sub>,w<sub>1</sub>)* ... *P(w<sub>T</sub>|w<sub>1</sub>, w<sub>2</sub>,..., w<sub>T-1</sub>)*
In an N-gram model, we approximate the conditional probabilities by assuming that the probability of a word depends only on the previous *N-1* words :  
*P(w<sub>t</sub> | w<sub>t-N+1, ..., w<sub>t-1</sub>)* = *P(w<sub>t</sub> | w<sub>t-1</sub>, ..., w<sub>t-N+1</sub>)*  
This leads to the approximation :  
*P(w<sub>t</sub> | w<sub>t-1</sub>, ..., w<sub>t-N+1</sub>)* = [*C(w<sub>t-N+1, ..., w<sub>t-1</sub>, w<sub>t</sub>)*] / [*C(w<sub>t-N+1, ..., w<sub>t-1</sub>)*]  
where :  
- *C(w<sub>t-N+1, ..., w<sub>t-1</sub>, w<sub>t</sub>)* is the count of the N-gram in the training corpus.
- *C(w<sub>t-N+1, ..., w<sub>t-1</sub>)* is the count of the N-1 gram.

### Example
Consider the sentence : "I love natural language processing".
1. **Unigrams**:
- "I", "love", "natural", "language", "processing"
- probability of "love" : *P(love)* = *C(love)* / *N*
2. **Bigrams** :
- "I love", "love natural", "natural language", "language precessing"
- Probability of "natural" given "love" : *P(natural|love)* = *C(love, natural)* / *C(love)*
3. **Trigrams** :
  - "I love natural", "love natural language", "natural language processing"
  - Probability of "language" given "love" and "natural" : *P(language|love, natural)* = *C(love, natural, language)* / *C(love, natural)*

### Limitations
1. **Data Sparsity** :  As N increases, the number of possible N-grams grows exponentially, leading to many unseen N-grams in the training data.
2. **Context Limitation** : The model only considers a limited context (the previous N-1 words), which may not capture long-range dependencies in language.

### Smoothing Techniques
To address the limitations of N-gram model, especially data sparsity, various smoothing techniques are used, such as :  
- **Laplace Smoothing** : Adds one to the count of each N-gram to ensure no probability is zero.
  *P(w<sub>t</sub> | w<sub>t-1</sub>, ..., w<sub>t-N+1</sub>)* = [*C(w<sub>t-N+1, ..., w<sub>t-1</sub>, w<sub>t</sub>) + 1*] / [*C(w<sub>t-N+1, ..., w<sub>t-1</sub>) + V*]
  where V is the vocabulary size
- **Kneser-Ney Smoothing** : A more sophisticates method that adjusted probabilities based on the frequency of N-grams and their continuation probabilities.
