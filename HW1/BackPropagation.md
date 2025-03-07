# Carlos Rodriguez
# CSC 59866
# Proofs of Backpropagation Formulas

## Proof of BP3: $\frac{\partial C}{\partial b_j^l} = \delta_j^l$

We need to prove:

$$
\frac{\partial C}{\partial b_j^l} = \delta_j^l
$$

### Step 1: Understanding the Terms

The weighted input to neuron $j$ in layer $l$ is:

$$
 z_j^l = \sum_k w_{jk}^{l} a_k^{l-1} + b_j^l
$$

where:

- $w_{jk}^{l}$ is the weight from neuron $k$ in layer $l-1$ to neuron $j$ in layer $l$,
- $a_k^{l-1}$ is the activation of neuron $k$ in layer $l-1$,
- $b_j^l$ is the bias of neuron $j$ in layer $l$.

$C$ is the loss function, $\frac{\partial C}{\partial b_j^l}$ is the partial derivative of the loss function with respect to the bias. This tells us how much a change in the bias will affect the error. Finally, we have $\delta_j^l$, which is the error.

### Step 2: Applying the Chain Rule

We want to compute:

$$
\frac{\partial C}{\partial b_j^l}
$$

Using the chain rule:

$$
\frac{\partial C}{\partial b_j^l} = \frac{\partial C}{\partial z_j^l} \cdot \frac{\partial z_j^l}{\partial b_j^l}
$$

### Step 3: Compute $\frac{\partial z_j^l}{\partial b_j^l}$

From the equation of $z_j^l$:

$$
 z_j^l = \sum_k w_{jk}^{l} a_k^{l-1} + b_j^l
$$

Differentiating with respect to $b_j^l$:

$$
\frac{\partial z_j^l}{\partial b_j^l} = 1
$$

### Step 4: Using the Definition of $\delta_j^l$

By the backpropagation equations:

$$
\delta_j^l = \frac{\partial C}{\partial z_j^l}
$$

Thus, substituting into our chain rule equation:

$$
\frac{\partial C}{\partial b_j^l} = \delta_j^l \cdot 1 = \delta_j^l
$$

This confirms that:

$$
\frac{\partial C}{\partial b_j^l} = \delta_j^l
$$

---

## Proof of BP4: $\frac{\partial C}{\partial w_{jk}^l} = a_k^{l-1} \delta_j^l$

We need to prove:

$$
\frac{\partial C}{\partial w_{jk}^l} = a_k^{l-1} \delta_j^l
$$

### Step 1: Understanding $z_j^l$

The weighted input $z_j^l$ to neuron $j$ in layer $l$ is:

$$
 z_j^l = \sum_k w_{jk}^{l} a_k^{l-1} + b_j^l
$$

### Step 2: Applying the Chain Rule

We want to compute:

$$
\frac{\partial C}{\partial w_{jk}^l}
$$

Using the chain rule:

$$
\frac{\partial C}{\partial w_{jk}^l} = \frac{\partial C}{\partial z_j^l} \cdot \frac{\partial z_j^l}{\partial w_{jk}^l}
$$

From the backpropagation equations:

$$
\delta_j^l = \frac{\partial C}{\partial z_j^l}
$$

Thus, we rewrite the equation as:

$$
\frac{\partial C}{\partial w_{jk}^l} = \delta_j^l \cdot \frac{\partial z_j^l}{\partial w_{jk}^l}
$$

### Step 3: Compute $\frac{\partial z_j^l}{\partial w_{jk}^l}$

From the equation of $z_j^l$:

$$
 z_j^l = \sum_k w_{jk}^{l} a_k^{l-1} + b_j^l
$$

Taking the derivative with respect to $w_{jk}^l$:

$$
\frac{\partial z_j^l}{\partial w_{jk}^l} = a_k^{l-1}
$$

### Step 4: Substituting

Substituting this result back:

$$
\frac{\partial C}{\partial w_{jk}^l} = \delta_j^l \cdot a_k^{l-1}
$$

which simplifies to:

$$
\frac{\partial C}{\partial w_{jk}^l} = a_k^{l-1} \delta_j^l
$$

This proves the formula asked of us for backpropagation.

