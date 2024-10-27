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
