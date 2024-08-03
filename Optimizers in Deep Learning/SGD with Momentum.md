* Can handle high curvature
* Can move faster even for saddle points
  
![image](https://github.com/user-attachments/assets/96451b04-099a-4b30-9498-751497c28287)


**Why use momentum?**
* it provides speed
  
* if our previous gradients tells us to move in the same direction, we will then move with more speed in that direction as we are confident now!

**To implement momentum, we use EWMA. The term (Beta * Vt-1) implements momentum while the rest of the term computes the gradient which is a common step**

![image](https://github.com/user-attachments/assets/3353bfef-e5c5-4e84-82f8-4d16d4f607d3)


**Effects if beta**
* if beta = 0, it will act simple SGD

* if beta = 1, there will be no decay and it will continuously move & will never stop (NO FRICTION)
![image](https://github.com/user-attachments/assets/12ed6da7-b141-4ed3-a937-b6d8168f6f2d)


**Disadvantage:**
* Disadvantage of momentum is, MOMENTUM

* Even at reaching the global minimum, it oscillates (to and fro) when wastes time, As EWMA uses previous values (WHICH ARE VELOCITIES IN THIS CASE) and gradually the weightage of velocities decreases & then it settles down
  
![image](https://github.com/user-attachments/assets/4684e0a7-5c76-4ad3-8a3f-155507bb0678)


# **Keras Code**
![image](https://github.com/user-attachments/assets/6548c8a5-cf46-4b90-b703-66dff6f1ab12)



