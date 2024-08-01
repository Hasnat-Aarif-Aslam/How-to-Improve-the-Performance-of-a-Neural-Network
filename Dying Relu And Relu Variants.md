![image](https://github.com/user-attachments/assets/276e3786-ac7d-4e99-9f3b-3f041f4a582c)The dying ReLU problem occurs when neurons receive too many negative inputs, resulting in their outputs being zero.

* Consider a neural network layer where the majority of inputs to neurons are negative. With the ReLU activation function, these neurons will output zero. Over time, if these neurons do not receive positive inputs that could activate them, they will remain zero, contributing nothing to the learning process.

* **If the dying relu contributes to the de-activation of more than 50% of neurons, the model becomes useless and can no longer identify patterns in the data.**


![image](https://github.com/user-attachments/assets/653448ce-28c1-4d69-a26e-cbad9d489906)


![image](https://github.com/user-attachments/assets/8af292a3-a8cc-4a2b-a8c4-02047815f191)


* When the output of Relu becomes 0:
![image](https://github.com/user-attachments/assets/dcbc19be-2df5-4b34-8e81-ce6bbe8b30ec)

* What are the solutions:
* Setting value of 0.01 for bias is proven for a good start, as it is large enough to prevent Dying Relu problem.
![image](https://github.com/user-attachments/assets/9e8aabe0-e4b9-4328-8d15-16b156f0b37c)


Variants:

Linear Category (actually referring to piecewise linear functions like ReLU variants):

* Leaky ReLU: A variant of ReLU that allows a small, non-zero gradient for negative inputs, preventing neurons from "dying".
* Parametric ReLU (PReLU): Similar to Leaky ReLU, but with a learnable parameter for the slope of the negative part.
* Both Leaky ReLU and PReLU are piecewise linear functions because they are composed of linear segments but introduce non-linearity by having different behaviors for positive and negative inputs.

Non-Linear Category:

* ELU (Exponential Linear Unit): Uses an exponential function for negative inputs, providing smoother and more robust learning.
* SELU (Scaled Exponential Linear Unit): A variant of ELU that scales the output, helping to normalize the network.
* ELU and SELU are inherently non-linear and provide more complex transformations than piecewise linear functions like ReLU variants.
![image](https://github.com/user-attachments/assets/3450c494-3a47-416c-99ea-0723b1a3e474)


* Leaky Relu:
0.01 * z means, outputs a small -ive value for values <0
![image](https://github.com/user-attachments/assets/f134a8b7-d1c3-4cef-97eb-e9637798aca4)
* Advantages:
![image](https://github.com/user-attachments/assets/797068e3-b7ee-4ea1-9f28-cc966d582d71)

* Example Usage:
  
![image](https://github.com/user-attachments/assets/f9fcfea4-deca-487c-badc-5951b526b9f5)


* Parametric Relu:

The slope for negative inputs is not fixed; it is optimized during training, allowing the model to learn the best value for this parameter.

More flexible, potentially leading to better performance, but slightly more complex due to the additional learnable parameter.

![image](https://github.com/user-attachments/assets/c68ef394-8a9d-4086-a4bc-b14558c0faa9)


* Example Usage:
  
![image](https://github.com/user-attachments/assets/4bd80af0-488e-4bf2-971b-368eebc4a430)


* ELU (Exponential Linear Unit):
* Alpha is constant and its values ranges from 0.1 to 0.3
  ![image](https://github.com/user-attachments/assets/55605bf8-60ea-4788-8db2-3ff4bcd306bf)
* Disadvantage is: cost of exponential operations
  ![image](https://github.com/user-attachments/assets/6d88757a-bc45-42dd-9d52-af6835424b2f)


* SELU (Scaled Exponential Linear Unit):
![image](https://github.com/user-attachments/assets/26d57899-db3a-4f8c-a56c-423b2f162f36)

* Derivative Plot and Advantages:
![image](https://github.com/user-attachments/assets/a8d03610-8944-4d72-a1b5-55e7c5422537)


Summary:
* ReLU: Default choice, fast and simple.
* Leaky ReLU: When ReLU neurons die and you need a simple fix.
* PReLU: When you need flexibility to learn the negative slope.
* ELU: When faster and more accurate learning is needed.
* SELU: For very deep networks where self-normalization helps.
