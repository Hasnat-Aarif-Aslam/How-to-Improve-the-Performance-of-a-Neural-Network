# **When to use AdaGrad:**

![image](https://github.com/user-attachments/assets/067a38b2-aca8-4823-97fe-5caf23aa5bd3)

* Let say we have two features, if one feature is sparse we will have less update for it as compared to the other feature which is normal

* It can be seen here that other optimizers are not taking the straight path to reach minima, firstly the update in normal feature which is "b" in our case is more significant than update of "m" but once it reaches to its optimum value then the change in weight in b is near to zero whereas m has not reached to its optimum value. So, it still tries to get its optimum value and continue to change even with small change in weight and thus take large time but still converge.

![image](https://github.com/user-attachments/assets/9622e3ab-b5d9-4354-862e-fdfe8e536049)

* So we set differnt learning rates, if the gradient is small we will increase the LR, if the gradient is large we will reduce the LR, inorder to have equal steps in all directions

![image](https://github.com/user-attachments/assets/f7eb9a72-e0b7-40cb-a789-c3efc2e5b001)


**AdaGrad in action**
* we can see it is taking optimized paths as compared to other optimizers
![image](https://github.com/user-attachments/assets/c21915eb-c32d-4896-bb96-807e424b489c)


**Disadvantages**
* we dont use it in NN, can be used in simple task like Linear Reg

* **it never reaches minima, as the LR decreases too much and it stops learning**

![image](https://github.com/user-attachments/assets/762608d4-d2d6-4959-a36d-f90ca40cbbd8)



