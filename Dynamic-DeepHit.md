```latex
@article{Lee2020DynamicDeepHitAD, title={Dynamic-DeepHit: A Deep Learning Approach for Dynamic Survival Analysis With Competing Risks Based on Longitudinal Data}, author={Changhee Lee and Jinsung Yoon and Mihaela van der Schaar}, journal={IEEE Transactions on Biomedical Engineering}, year={2020}, volume={67}, pages={122-133} }
```

# Dynamic DeepHit
Lee, Yoon, and van der Schaar apply self-attention to a temporal sequence of learned embeddings to estimate the probability of competing risks in patients with Cystic Fibrosis.
#attention #risk

# Summary

## Methods
![[Pasted image 20220708230758.png]]

The combination of a 1. learned embedding of sequential measurements, here via RNN, and 2. token mixing via temporal attention over a sequence of learned embeddings, is reminiscent of a transformer architecture. Given that transformers appeared a year earlier it is surprising they chose to _roll their own_ version, though the Vision Transformer was still a couple years away when the first Dynamic-DeepHit paper was released in 2018.

An MLP head with softmax activation provides a categorical joint distribution over competing risks.

## Results
They outperform traditional statistical models that treat each risk as independent, like the Cox proportional hazard model, by 5-15%.

# Connections

# Key References