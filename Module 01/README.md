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

- **GPT (Generative Pre-trained Transformer) Series (2018 - Present)** :
  - GPT models focus on generating text based on left-to-right context, making them effective for tasks like text completion, dialogue systems, and content creation.
  - The release of GPT-3 in 2020 showcased the potential of transformers to generate high-qualit , human-like text, pushing the boundries of language generation.

- **Specialized Transformer (T5, XLNet, Transformer-XL)** :
  - Various architecture have been developed to address specific tasks or challenges within sequence modelling, such as handling long-range dependencies, memory efficiency, and specific task adaptation.

- **Recent Innovations (2021-Present)** :
  - Transformers have continued to evolve with efficient transformer variants like BigBird and Reformer for handling long sequences, and multimodel transformers that process multiple data types (e.g. text, image).
  - Transformers have also expanded into fields beyond NLP, such as computer vision, reinforcement learning, and genomics, demonstrating their flexibility.

### The Current and Future Landscape
- **Transformers in Multimodal Applications** :
  - Multimodal transformers can process different data types (e.g. images, and text) in the same model, paving the way for advanced applications in fields like healthcare, robotics and social media.
- **Efficient Transformer Architectures** :
  - techniques like sparse attention, memory-efficient transformers, and adaptive transformers continue to push the boundries, allowing transformers to handle larger data and perfrom effieciently in real-time applications.

## RNNs and LSTMs : Limitations
### Limitations of RNNs
- **vanishing and Exploding Gradients**
     - **Description** :
       - RNNs rely on backpropogation through time (BPTT) to ypdate weights. During this process, gradients are propogated backward through many time steps.
       - If the gradients become very small (vanishing) or very large (exploding) the model's ability to learn the long-term dependencies is compremised.
     - **Impact** :
        - Vanishing gradients make it difficult for RNNs to learn long-range dependencies, as the model cannot effectively update weights for earlier time steps.
        - Exploding gradients cause instability during training, leading to divergence of the learning process.
- **Difficulty in capturing Long-Term Dependencies**
     - **Description** :
       - RNNs struggle to maintain information over long sequences due to the vanishing gradient problem.
       - They tend to proritize recent information over old context, leading to poor performance on tasks requiring long-term memory (e.g. language translation with distant dependencies).
     - **Impact** :
        - Tasks requiring the model to relate information for apart in the sequence, such as understanding the context of a novel or resolving long-range coreferences, suffer.
- **Sequential processing**
     - **Description** :
       - RNNs process input sequentially, step by step, which limits parallelization during training and inference.
    - **Impact** :
      - This sequential dependecy results in longer training times and makes RNNs computationally inefficient compared to models that can leverage parallel processing, such as Transformers.
- **Fixed Input and Output Lengths** :
     - **Descriptin** :
       - While RNNs can handle variable-length input sequences, they often require pre-determined lengths for input and output sequences in practice.
    - **Impact** :
        - This can be limiting for certain tasks where dynamic sequence lengths are crucial, like real-time streaming data analysis.
