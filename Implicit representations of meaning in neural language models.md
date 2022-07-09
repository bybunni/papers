```latex
@inproceedings{Li2021ImplicitRO, title={Implicit Representations of Meaning in Neural Language Models}, author={Belinda Z. Li and Maxwell Nye and Jacob Andreas}, booktitle={ACL}, year={2021} }
```
# Implicit Representations of Meaning in Neural Language Models
Li, Nye and Andreas explore intermediate word embeddings in a language model with a _probe_ to see if logical propositions are encoded in the embeddings.
#LLM #NLP #word-vectors 
# Summary
## Methods
An information state $I$ is built up of logical propositions $\phi$ describing the state of various entities in a sequence of sentences $x$.

Given a chest, a key, and an apple, and $x_0:$ _The only thing in the chest is an old key._, $I_1:$
1. $\phi_{1,0}$ contains(chest, key) = T
2. $\phi_{1,1}$ contains(chest, apple) = F
3. $\phi_{1,2}$ eaten(apple) = ?

A _probe_ is used to explore if intermediate embeddings can be used to correctly classify logical propositions  as $T$, $F$, or $?$. The _probe_ is trained on a subset of labeled discourses and their propositions and tested on held-out discourses.

![[372D7DCA-DAB8-4AA0-8623-131F2EC67609_1_201_a.jpeg]] (Eq. 1)
## Results
1. The _probe_ correctly classifies the subject entity 96.9% of the time, ie. the proposition is considering the correct entities.
2. The _probe_ correctly classifies the proposition state ($T, F, ?$) 53.8% of the time, ie. the proposition is correct.
3. The state of an entity is roughly localized to tokens that refer to it.
# Connections
# Key References
* What Does BERT Look at? An Analysis of BERT’s Attention
* Does BERT Make Any Sense? Interpretable Word Sense Disambiguation with Contextualized Embeddings
* Revealing the Dark Secrets of BERT
* BERT Rediscovers the Classical NLP Pipeline