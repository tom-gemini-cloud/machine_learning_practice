# Supervised Learning Classification

## Discriminant Analysis

Discriminant Analysis is a family of supervised classification methods that model each class's distribution and then use Bayes' rule to assign the most likely class.

### Core idea

Assume each data point is a feature vector:

- $\mathbf{x} \in \mathbb{R}^d$ (a vector of $d$ real-valued features)

Assume the features come from a **class-conditional density**:

- $p(\mathbf{x} \mid y = k)$ (the probability density of seeing $\mathbf{x}$ if the class is $k$)

and each class has a **prior probability**:

- $\pi_k = P(y = k)$ (how common class $k$ is overall)

### Prediction rule

Predict the class $\hat{y}$ by choosing the class $k$ that maximises:

$$
\hat{y} = \arg\max_k \left[ \log p(\mathbf{x} \mid y = k) + \log \pi_k \right]
$$

### Common modelling choice

Most commonly, $p(\mathbf{x} \mid y = k)$ is modelled as a **multivariate Gaussian**.
