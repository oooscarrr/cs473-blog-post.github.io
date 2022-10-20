# Oscar Xue Blog Post for Lecture 12 Intro to Gradients

## Bird's eye view of optimization

### Example: How much water to give your plant?
Let $\theta$ be the amount of water per day, $f(\theta)$ be the leaf loss per day.
1. Brute-force search
    - iterate through all points $\theta$ and record the lowest $f(\theta)$.
2. No analytical model
    - Select three data points and find their minimum $\hat{\theta}$;
    - Select three new points near $\hat{\theta}$, then recurse the first step;
    - Gradually increase resolution around the lowest points.
3. Analytical model available
    - Compute first and second derivative(gradient);
    - Local extremum when $f'(\theta)=0$
        - $f''(\theta)>0 \Rightarrow$ minimum;
        - $f''(\theta)<0 \Rightarrow$ maximum.
4. Model available, but difficult to directly minimize
    - **Gradient descent**

---
## Gradient descent
Start at $\theta_0$ and iteratively update $\theta$ by
$$\theta_{t+1} = \theta_t - \alpha f'(\theta_t)$$
where $\alpha$ is the learning rate that determines how far away is the next itertion.

### Newton's method to find local extremum
A special case of gradient descent with $\alpha= 1/f''(\theta)$, such that
$$\theta_{t+1} = \theta_t - \frac{f'(\theta_t)}{f''(\theta_t)}$$
