```latex
@inproceedings{Rostami2021LifelongDA, title={Lifelong Domain Adaptation via Consolidated Internal Distribution}, author={Mohammad Rostami}, booktitle={NeurIPS}, year={2021} }
```

# Lifelong Domain Adaptation via Consolidated Internal Distribution
Mohammad Rostami proposes a method of 1. identifying key examples and their labels in an unsupervised domain adaptation continuous learning scenario under domain distribution shift, 2. constraining the learned internal distributions from moving too far away from those learned on the original domain distribution, and 3. regularizing with the previously identified key examples to overcome _catastrophic forgetting_.
#catastrophic-forgetting #lifelong-learning #distribution-shift

# Summary
Given different data sets (that clearly exhibit domain shift) for the same task (e.g. digit recognition) the goal is to train on successive datasets while maintaining performance on all previous data sets. Only the labels from the first dataset are visible during training, all subsequent datasets are trained on without any labels.

## Methods
1. Train an encoder $\phi$ on dataset $X$ with labels $Y$ and $j$-many classes.
2. Fit a GMM $p_J(z)$ to the embedding space $Z$ of the encoder.
    1. Each of the $j$ modes in this GMM corresponds to one of the input classes.
3. Select from the dataset $X$ _ideal_ representative samples, as determined by their distance to each of the $j$ cluster centers, and save these in a replay buffer $\mathcal{D}_b$.
4. For each subsequent dataset we first generate a _pseudo_ dataset $Z_P$ by sampling from each of the GMM clusters and assigning each the label $Y_P$  of their respective cluster.
5. We update our entire pipeline to
    1. minimize the classification loss between samples $z$ and their cluster labels $y$ of our pseudo dataset $Z_P$
    2. minimize the classification loss between samples $x$ from our replay buffer $\mathcal{D}_b$ and their cluster labels $y$
    3. minimize the distance $D$ between our encoded source data distribution $\phi(p_t(X))$ and our GMM _pseudo_ data distribution $p_J(Z_P)$
    4. minimize the distance $D$ between our encoded replay buffer data distribution $\phi(p_t(X_b))$ and our GMM _pseudo_ data distribution $p_J(Z_P)$

![[Pasted image 20220711185413.png|400]]

## Results
The results look pretty good, strong performance is achieved on subsequent tasks without labels and without catastrophic forgetting, though there is a degradation of performance on the original task.

![[Pasted image 20220711185340.png]]

# Connections

# Key References
- A crowdsourcing triage algorithm for geopolitical event forecasting.