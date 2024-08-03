# **Difference betwenn SGD with momentum & NAG**

* In SGD Momentum, we calculate both the Momentum (History of velocity) & Gradient at the point to take the next step

* In NAG, we firstly calculate Momentum at take the step (LOOK AHEAD), then we calculate the Gradient at the new point and take another step  THAT'S IT!
  
![image](https://github.com/user-attachments/assets/b65e494d-bd28-446a-acdb-debb5738220e)

![image](https://github.com/user-attachments/assets/3cadfc2a-dbfd-48b9-bca7-cdd64483dd15)


# **Disadvantage:**

* due to damped oscillations, we can stuck in local minima

![image](https://github.com/user-attachments/assets/54485bd0-b83c-42e6-9036-55b10888e3c9)

# **Keras Code**
![image](https://github.com/user-attachments/assets/5cbb85bb-5fa1-42bb-b1b0-3d59afcd2954)


