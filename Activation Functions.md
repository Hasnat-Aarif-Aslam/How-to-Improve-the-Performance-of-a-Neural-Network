Below are some of the details about the Activation Functions. Choosing the suitable Activation Function can improve the neural network performance.

![image](https://github.com/user-attachments/assets/c8c6cdf0-76b1-4a68-bc12-6e68ed4b3afd)


Sigmoid Activation Function
Advantages:

* Non-linear: It can capture the non-linearity in the data easily.

* Probability Output: Outputs values between 0 and 1, suitable for binary classification as probabilities.

* Smooth Gradient: The function is smooth and differentiable, aiding gradient-based optimization.

* Historical Use: Mimics the firing rate of neurons, making it a traditional choice in neural networks.

Disadvantages:
* Saturating Function: For very high or very low inputs, the gradient becomes very small, causing Vanishing Gradient Problem.

* Not Zero-Centered: Outputs are always positive, leading to inefficient gradient updates and slower convergence.

* Computational Cost: Involves exponential calculations, making it more computationally expensive than ReLU.

![image](https://github.com/user-attachments/assets/cc296c0e-fd3e-430a-b8a7-46dfed7b1c5b)

Tanh (Hyperbolic Tangent) Activation Function
Advantages:

* Non-linear: It can also capture the non-linearity in the data easily.

* Zero-Centered Output: Outputs range from -1 to 1, aiding in centering data and potentially faster convergence.

* Smooth Gradient: The gradient is larger for inputs close to zero compared to sigmoid, reducing the vanishing gradient problem.

Disadvantages:
* Saturating Function: For very high or very low inputs, the gradient still becomes small causing vanishing gradient problem, though less severely than sigmoid.

* Computational Cost: Similar to sigmoid, it involves exponential calculations, making it computationally expensive.

![image](https://github.com/user-attachments/assets/b4335f04-deb0-4558-9abd-4ada249c071a)

ReLU (Rectified Linear Unit) Activation Function
Advantages:

* Efficient Computation: Simple thresholding at zero makes it computationally efficient.

* Non-Saturating Gradients: Does not saturate for positive inputs, maintaining large gradients and efficient learning. Negative inputs, however, lead to zero gradients (dying ReLU problem) which can cause vanishing gradient problem.

* Sparse Activation: Produces sparse outputs (many neurons output zero), improving model efficiency and generalization.

Disadvantages:

* Non Zero-Centered: Similar to Sigmoid, ReLU outputs are not zero-centered, which can cause issues in gradient updates (It can be resolved using batch normalization).

* Dying ReLU Problem: Neurons can "die" if they get stuck outputting zero for all inputs, leading to no learning.

* Unbounded Output: Outputs can grow very large, potentially requiring careful weight initialization and regularization techniques.
