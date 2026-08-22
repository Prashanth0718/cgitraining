# The Illustrated Transformer – Research Paper Summary

**Author:** Jay Alammar
**Topic:** Transformer Architecture and Self-Attention

*The Illustrated Transformer* is a visual explanation of the Transformer architecture introduced in the 2017 research paper *Attention Is All You Need* by Vaswani et al. The fundamental goal of the Transformer is to process sequences, particularly for natural language tasks such as machine translation, without relying on recurrent neural networks (RNNs). One of its major advantages is that it can process many parts of a sequence in parallel, making training more efficient.

The Transformer uses an **encoder-decoder architecture**. The encoder reads the input sentence and converts it into meaningful representations. The decoder then uses these representations to generate the output sentence. Unlike recurrent neural networks, which process words sequentially, the Transformer can process the input sequence in parallel.

The key component that enables this is **self-attention**. Self-attention allows each word in a sentence to consider other words that are important for understanding its meaning and context. For example, in the sentence, “The animal didn't cross the street because it was tired,” attention helps the model understand which word the pronoun “it” refers to. The self-attention mechanism uses three representations called **Query, Key, and Value (Q, K, V)** to determine how much attention one word should give to other words.

The Transformer also uses **multi-head attention**, which applies multiple attention mechanisms in parallel. Each attention head can learn different relationships between words and capture different types of information. The Transformer also uses **positional encoding** to provide information about the position of each word because the model processes the sequence in parallel and does not inherently know word order.

Each encoder layer contains a **multi-head self-attention mechanism** followed by a **feed-forward neural network**. These components use residual connections and layer normalization. The decoder contains three main components: masked multi-head self-attention, encoder-decoder attention, and a feed-forward neural network. Masking prevents the decoder from using future words when generating the output.

The Transformer replaced traditional sequence-to-sequence approaches that relied heavily on recurrent or convolutional networks with an architecture based primarily on attention. Its ideas became the foundation for many modern Natural Language Processing and Generative AI systems.

**Conclusion:** The main principle of the Transformer is that a model can understand relationships between words more effectively by allowing each position in a sequence to attend to other positions. Through self-attention, multi-head attention, positional encoding, and the encoder-decoder architecture, the Transformer can process information in parallel and capture relationships between words efficiently. *The Illustrated Transformer* makes these complex concepts easier to understand through visual explanations.
