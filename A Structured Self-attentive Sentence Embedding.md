```latex
@article{Lin2017ASS, title={A Structured Self-attentive Sentence Embedding}, author={Zhouhan Lin and Minwei Feng and C{\'i}cero Nogueira dos Santos and Mo Yu and Bing Xiang and Bowen Zhou and Yoshua Bengio}, journal={ArXiv}, year={2017}, volume={abs/1703.03130} }
```

# A Structured Self-attentive Sentence Embedding
To produce a fixed length encoding of a variable length sentence Lin, et al. introduce self-attention to produce new fixed length embeddings that are each a linear combination of the input embeddings.
#attention #NLP

# Summary
Practically, this looks like the broad strokes of the #transformers architecture;
1. sequence of tokens (words) -> sequence of embeddings
2. sequence of embeddings -> multi-head self-attention (they refer to this as 'multiple hops' of attention)
3. multi-head self-attention -> sequence of embeddings (in this case of fixed length)
4. sequence of embeddings -> MLP head for downstream tasks (classification)

## Methods
The key difference between this and transformer self-attention is that for each head we compute attention weights over all input sequences. Thus for each head we get a single vector of attention to which we similarly apply softmax to get a categorical distribution. 

We take the product of the input and this attention to produce 1 new vector that is simply a linear combination of the inputs, in this case the inputs are a sequence of word embeddings $H$ produced by a bi-directional LSTM.

We repeat this process $m$ times, or more practically perform the $m$-many applications in a vectorized way with an appropriately shaped weight matrix, to produce $m$-many attention vectors in attention matrix $A$. The sentence embedding $M$ is thus produced by:

$$M = AH$$

## Results
Aside from introducing multi-head self-attention and some SOTA results on NLP tasks of the day, because their output embeddings are linear combinations over the embeddings of the input tokens, they can visualize their outputs as a heatmap over the input tokens to remarkable effect.

![[Pasted image 20220710230413.png]]

# Connections
The linear combination of the input embeddings is very close to our own [[Compositionality|Embedding Space Transformer]].

# Key References
* [[Skip-Thought Vectors]]