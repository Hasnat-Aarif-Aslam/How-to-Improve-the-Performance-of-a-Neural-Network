# **Dont's:**

1. Why We Can't Initialize Weights with Zero
Problem:

* Identical Outputs: All neurons in a layer will produce the same output because they start with the same weights and biases.
* Identical Gradients: Gradients will be the same for all neurons during backpropagation, leading to identical weight updates.
* Symmetry Breaking: The network will fail to break symmetry and learn diverse features, essentially behaving as if it has only one neuron per layer.

2. Why We Can't Initialize Weights with a Non-Zero Constant
Problem:

* Identical Outputs: All neurons will output the same value during the forward pass, as they have the same weights.
* Identical Gradients: Gradients will be identical for all neurons, resulting in identical weight updates during backpropagation.
* Learning Diversity: The network will fail to learn different aspects of the input data, as all neurons will learn the same features, behaving as a single neuron.

3. Why We Can't Initialize Weights with Random Small Numbers
Problem:

* Vanishing Gradients (especially for Sigmoid/Tanh): If weights are too small, the activations in deep networks can become very small, leading to very small gradients during backpropagation. This makes the weights update very slowly, hindering learning.
* Loss of Signal: In deep networks, small weights can cause the signal (activations) to diminish as it propagates through layers, making it difficult for the network to learn effectively.

4. Why We Can't Initialize Weights with Random Large Numbers
Problem:

* Exploding Gradients: If weights are too large, the activations can become very large, leading to very large gradients during backpropagation. This can cause the weights to update too drastically, destabilizing the learning process.
* Loss of Gradient Information: Large activations can cause saturation in activation functions like Sigmoid and Tanh, where the gradient is near zero for very high or very low values. This leads to the vanishing gradient problem despite the large initial weights.
* Instability: Large initial weights can cause instability in the training process, with the loss function oscillating wildly or diverging.


# **Do's:**
* Xavier/Glorot: Works best for tanh and sigmoid (not for relu)
* Xavier/Glorot (Normal):
* ![image](https://github.com/user-attachments/assets/cade93ce-5266-4058-8929-9402106557ad)


* He: Works best for Relu
* He (Normal):
* ![image](https://github.com/user-attachments/assets/be6a0546-474c-4a04-bb00-8d338a2bc114)


* Xavier/Glorot (Uniform):
* ![image](https://github.com/user-attachments/assets/3f659ee8-ce46-44d2-9e92-b3e41a65437e)


* He (Uniform):
* ![image](https://github.com/user-attachments/assets/d782c236-1e84-43f7-b756-91c46216c6ce)


# Xavier/Glorot Normal & Uniform Code Implementation:


kernel_initializer = 'he_normal'

kernel_initializer = 'he_uniform'

kernel_initializer = 'glorot_normal'

kernel_initializer = 'glorot_uniform'

* Default kernal_initializer is 'glorot_uniform'

# OR:

import tensorflow as tf

'Xavier Normal Initialization'

xavier_normal = tf.keras.initializers.GlorotNormal()

'Xavier Uniform Initialization'

xavier_uniform = tf.keras.initializers.GlorotUniform()

model = tf.keras.models.Sequential([
tf.keras.layers.Dense(units=hidden_size, input_shape=(input_size,), kernel_initializer=xavier_normal),
tf.keras.layers.Dense(units=output_size, kernel_initializer=xavier_uniform)
])



# He Normal & Uniform Code Implementation:

import tensorflow as tf

'He Normal Initialization'

he_normal = tf.keras.initializers.HeNormal()

'He Uniform Initialization'

he_uniform = tf.keras.initializers.HeUniform()

model = tf.keras.models.Sequential([
tf.keras.layers.Dense(units=hidden_size, input_shape=(input_size,), kernel_initializer=he_normal),
tf.keras.layers.Dense(units=output_size, kernel_initializer=he_uniform)
])



