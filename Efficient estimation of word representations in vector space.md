```latex
@inproceedings{Mikolov2013EfficientEO, title={Efficient Estimation of Word Representations in Vector Space}, author={Tomas Mikolov and Kai Chen and Gregory S. Corrado and Jeffrey Dean}, booktitle={ICLR}, year={2013} }
```
# Efficient Estimation of Word Representations in Vector Space
Mikolov, Chen, Corrado, and Dean introduce new techniques for word vector learning and analyze the learned vectors along multiple degrees of similarity.
#NLP #word-vectors 
# Summary
## Methods
Two model architectures are introduced.
1. CBOW; predicts a word, given a window of words before it and after it.
2. Skip-gram; given a word, predicts a window of words before it and after it.
## Results
The best results are achieved with **high dimensional word vectors** $\mathbb{R}^{640}$, and a **large amount of data** 783M training words.

Vector similarity is measured by vector addition and cosine distance eg. $X = vector(biggest) - vector(big) + vector(small)$, then finding the word closest to $X$ measured by cosine distance.

![[Pasted image 20220703154256.png]]
# Connections
The finding that word vector dimension and training data set size need to grow together recalls [[The Bitter Lesson]] and is a premonition of the #LLM and #transformers revolution to come.
# Key References
* Linguistic Regularities in Continuous Space Word Representations
* A neural probabilistic langage model