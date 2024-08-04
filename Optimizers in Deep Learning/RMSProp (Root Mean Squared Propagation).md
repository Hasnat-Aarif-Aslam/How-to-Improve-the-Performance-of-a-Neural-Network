# **Adagrad (Adaptive Gradient Algorithm)**
Key Idea:

* Adapt Learning Rate: Adapts the learning rate for each parameter individually.
  
* Cumulative Sum: Uses the sum of the squares of all previous gradients to scale the learning rate.

**How It Works:**

* As training progresses, Adagrad accumulates the squared gradients for each parameter
  
* Parameters with larger cumulative gradients get smaller updates, while parameters with smaller cumulative gradients get larger updates.
  
* This helps with sparse data by giving more learning power to infrequent features.
  
**Pros:**

* Good for Sparse Data: Works well with sparse features because it increases the learning rate for rarely updated parameters.

* No Manual Learning Rate Tuning: Automatically adjusts the learning rate during training.

**Cons:**

* Learning Rate Decreases Too Much: The cumulative sum can become very large, leading to the learning rate becoming extremely small, which can stop learning prematurely.

  
# **RMSprop (Root Mean Square Propagation)**
Key Idea:

* Adapt Learning Rate: Also adapts the learning rate for each parameter, but in a more controlled way.
* Exponential Moving Average: Uses an exponentially decaying average of past squared gradients to scale the learning rate.
  
**How It Works:**

* Instead of summing all past squared gradients like Adagrad, RMSprop keeps a moving average of the squared gradients.
* This moving average helps to keep the learning rate more balanced and prevents it from becoming too small.
  
**Pros:**

* Controlled Learning Rate: Avoids the issue of the learning rate shrinking too much, ensuring continuous learning.
* Effective for Non-Stationary Problems: Works well with non-stationary problems (where the distribution of data changes over time).
  
**Cons:**

* Hyperparameter Tuning: Requires setting a decay rate (usually around 0.9), which might need some tuning.

# **Disadvantages:**
* No as such dis-advatages, it was the best optimizer before ADAM

* in some case if ADAM does'nt works best, we can use RMSProp
