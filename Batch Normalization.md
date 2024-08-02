What is Batch Normalization?
Batch normalization is a technique used in training neural networks to make the learning process more stable and faster. It does this by standardizing (Mean = 0, Standardization = 1)
the inputs to a layer for each mini-batch, meaning it adjusts and scales the activations.


Why Use Batch Normalization?
* Stabilizes Learning: By keeping the input to each layer normalized, batch normalization helps the network learn more efficiently.
* Speeds Up Training: It allows for higher learning rates, which means the model can converge (find the optimal solution) faster.
* Reduces Sensitivity to Initialization: It makes the training less dependent on the initial starting weights of the network.
* Acts as a Regularizer: It can reduce the need for other regularization techniques like dropout, helping to prevent overfitting.

**Covariate Shift:**
Covariate shift occurs when the statistical distribution of the input data changes between the training phase and the testing (or deployment) phase. This can lead to poor performance on new, unseen data because the model was trained on data with different properties.

Real-World Example:

Imagine you're developing a model to predict house prices based on various features like the size of the house, the number of bedrooms, and the neighborhood.

Training Data: You collect data from a city where house prices are generally high because it's a desirable location.

Testing Data: You then apply your model in a different city where house prices are lower due to different economic conditions and less demand.

Problem: The model may not perform well in the new city because it was trained on data from a city with different house price distributions. This change in the input data distribution is covariate shift.


* Lets say we have mistakenly trained our model with only red rose images and other flowers. On the right we can see the distribution of training, but when we tested our model we gave it roses of different colors due to which the distribution has changed which will lead to performance degradation

![image](https://github.com/user-attachments/assets/53012a88-7132-4fad-b0a4-51bf7ed7995a)


**Internal Covariate Shift:**
Internal covariate shift refers to the changes in the distribution of inputs to a layer within a neural network during training. As the network updates its weights, the distribution of inputs to each layer changes, which can slow down training and make it harder for the network to learn effectively.

Real-World Example:

Imagine you're teaching a child to solve math problems.

Early Lessons: You start with simple addition problems, and the child learns the basics.

Later Lessons: As you introduce more complex problems (like multiplication or division), you notice that the child struggles because the way you presented the problems keeps changing in unpredictable ways.

Problem: If the way you present the problems keeps changing, the child needs to constantly adapt, making learning harder. In a neural network, if the distribution of inputs to each layer keeps changing due to weight updates, each layer needs to continuously adapt, slowing down the learning process.


Things To Remember:
* Used only with Mini-Batch GD
* It can be applied to any or all the layers of the NN

Normalizing:
![image](https://github.com/user-attachments/assets/b2fa033c-29f3-41a9-9764-c87313b63244)

Shifting:
![image](https://github.com/user-attachments/assets/5e16c668-09a1-40d3-b5a2-83e59608645c)


* As we know when we train the model with batch normalization, gamma, beta, mean and std are calculated for each neuron based on the batch size.
  
* gamma and beta are learnable parameters (learned using GD during training
  
* mean and std are non-learnable parameters
  
* **But when we test the model, we only have 1 sample to test at a time, then how we can get mean and std???**

* As we know for each batch there is mean and std for it, so for all the batches we maintain (Exponentially Weighted Moving Average) for mean and std
  
* After all the batches, we then use the value of mean and std which are now (EWMA for mean & EWMA for std) for testing 
 
![image](https://github.com/user-attachments/assets/df883f96-e202-49b2-b9ee-5162222bf32b)


