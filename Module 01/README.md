## <div align="center">Introduction to Transformer and Sequence Models</div>
## History of Sequence Models
The history of the sequence models in machine learning and natural language processing (NLP) is a fascinating journey, evolving from early statistica methods to advanced deep learning architecture like Transformers. Here is a detailed look at this progression : 
### Statistical Methods for Sequence Modelling
- **[Markov Chains (1950s)](https://github.com/SHIVAMAMBAH/Transformer/blob/main/Module%2001/Markov%20Chains/README.md)** :
  - The early foundations of sequence modelling relied on probablistic approach like Markov Chains.
  - Markov Chains assume that the probability of the each item in a sequence depends only on the previous item.
  - Despite its simplicity, the Markov assumption helped develop many early NLP applications including simple text generation and part-of-speech tagging.
- **[Hidden Markov Models (HMMs) (1960s-1970s)](https://github.com/SHIVAMAMBAH/Transformer/blob/main/Module%2001/Hidden%20Markov%20Model/README.md)**:
  - HMMs introduced a way to model hidden or unsolved states influencing observed data, marking an improvement over simple Markov chains.
  - Widely applied in <mar>speech recognition and bioinformatics</mark>, HMMs allowed models to handle sequences with unobserved (latent) variables, making them more expressive.
  - HMMs were used for tasks like speech recognition, where phonemes (sound units) needed to be infered from a sequence of audio signals, and named entiry recognition (NER).
- **[N-gram Model (1980s)](https://github.com/SHIVAMAMBAH/Transformer/blob/main/Module%2001/N-gram%20Model/README.md)** :
  - N-gram involve splitting sequences into fixed-size subsequences, or "grams" allowing model to estimate probabilities by counting occurance.
  - N-gram Provide more context than single words (as in markov Chains) but are still limites by the fixed sized window size.
  - They were widely used in machine translation, text prediction, and speech recognition, forming the basis of many NLP tasks before deep learning.

### Neural Network-Based Sequence Models
- **[Recurrent Neural Networks (RNNs) (1980s-1990s)](https://github.com/SHIVAMAMBAH/RNN/tree/main)**:
  - RNNs introduced the concept of using neural networks to handle sequential data by maintaining a hidden state across time steps, allowing models to learn dependencies within the sequence.
  - This architectire enables more complex language modelling, text generation, and time-series prediction than previous statistical methods.
  - However, RNNs struggled with long-term dependencies due to issues like vanishing gradients, where gradients shrink or explode as they are backpropagated over time.

- **Long Short-Term Memory (LSTM) Networks (1997)**:
  - LSTM networks were developed by Hochreiter and Schmidhuber to address the limitations of standard RNNs.
  - LSTMs use a gating mechanism (input, forget, and output gates) to regulate information flow, allowing them to capture longer dependencies and reduce the vanishing gradient problem.
  - They became popular for language modelling, speech recognition, and machine translation, among other tasks.
- **Gated Recurrent Units (GRUs) (2014)** :
  - GRUs introduced as a simlified version of LSTMs, use fewer gates (update and reset) to capture dependencies within sequence.
  - GRUs provided similar performance to LSTMs while reducing computational complexity, making them popular for tasks where model efficiency was essential.

### Attention Mechanism (2014)
- **Introduction to Attention in RNNs** :
  -  The attention mechanism was first proposed in the context of neural machine translation (NMT) to allow the model to focus on relevant parts of an input sequence while decoding.
  -  It enabled the network to assign different weights to different input tokens, improving the handling of long sentences and complex relationships within sequences.
  -  Attention mechanism became widely used in sequence-to sequence models, enhancig the ability of RNNs, LSTMs and GRUs for tasks like translation, summarization, and question answering.

### The Transformer Model (2017)
- **Attention is all you need (Vaswani et al., 2017)** :
  - Transformer departs from RNN-based architectures, relying solely on attention mechanisms and discarding recurrence although.
  - They introduced self-attention, where each element in the sequence can attend to every other element, allowing for better parallelization during training and more effective long-range dependency handlling.
  - Transformers quickly outperformed previous models across NLP tasks, revolutionizing language modelling, machine translation, and many other domains.

- **Encoder-Decoder Structure in Transformers** :
  - The encoder processes the input sequence, while the deocder generates the output sequence.
  - Self-attention within the encoder captures relationships words in the input sequence between the input and output sequences.

### Transformer-Based Architecture (2018-Present)
- **BERT (Bidirectional Encoder Representations from Transformers) (2018)** :
  - BERT introduced bidirectional training of Transformers, meaning it could look at both the left and right context of each word, improving performance on NLP tasks that require a nuanced understanding of context.
  - It's success inspired other bi-directional models like RoBERTa and ALBERT, leading to significant advancements in tasks like question answering and sentimental analysis.



