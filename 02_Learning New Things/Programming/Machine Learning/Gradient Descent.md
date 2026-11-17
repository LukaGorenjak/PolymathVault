==is an iterative mathematical optimization algorithm used to find the minimum of a function.==

---
**How it works:**
- Imagine you are standing on a foggy mountain and want to reach the lowest valley:

- **Cost/Loss Function:** Measures how wrong your model's predictions are. Your position on the mountain represents the current error value. [[1](https://outcomeschool.com/blog/math-behind-gradient-descent), [2](https://machinelearningmastery.com/gradient-descentthe-engine-of-machine-learning-optimization/)]

- **Gradient:** Calculates the slope (derivative) of the error function at your exact spot. It points in the direction of the _steepest ascent_ (uphill). [[1](https://en.wikipedia.org/wiki/Gradient_descent), [2](https://machinelearningmastery.com/gradient-descentthe-engine-of-machine-learning-optimization/), [3](https://www.envisioning.com/vocab/gradient-descent)]

- **Step in the Opposite Direction:** You take a step in the _negative_ direction of the gradient to go downhill. [[1](https://machinelearningmastery.com/gradient-descentthe-engine-of-machine-learning-optimization/), [2](https://en.wikipedia.org/wiki/Gradient_descent), [3](https://outcomeschool.com/blog/math-behind-gradient-descent)]

- **Learning Rate (α):** A hyperparameter that controls the size of the steps you take.
    - If the step is **too big**, you might overshoot the bottom and bounce around.
    - If the step is **too small**, it will take a very long time to reach the bottom. [[1](https://builtin.com/data-science/gradient-descent), [2](https://outcomeschool.com/blog/math-behind-gradient-descent), [3](https://machinelearningmastery.com/gradient-descentthe-engine-of-machine-learning-optimization/)]

- **Convergence:** You repeat this loop until the slope is nearly flat (the error is minimized)