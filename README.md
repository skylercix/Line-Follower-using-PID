# Line-Follower-using-PID
![image](https://github.com/user-attachments/assets/ed33cfd4-3c12-43b9-bb24-0b35105f86eb)

## Project Overview  

This project is a **PID-controlled line follower robot**, developed as part of an **Embedded Systems course**. The main goal was to understand how a **PID controller** influences system behavior and improves motion control.  

I will not go into a detailed presentation of the entire project. Instead, I will highlight only the key components necessary for understanding how the **PID controller** works. The complete project, from which I took inspiration, can be found at the following link:  

🔗 **[Original Project on Hackster.io](https://www.hackster.io/anova9347/line-follower-robot-with-pid-controller-cdedbd#toc-6--bluetooth-control-5)**  

By implementing this project, I explored how proportional, integral, and derivative terms affect motor speed adjustments, ensuring stable and efficient line tracking.

## Components
* [Arduino Pro Mini 328 - 5V/16MHz](https://www.sparkfun.com/products/11113)  

* [DRV8835 Dual Motor Driver Carrier](https://www.pololu.com/product/2135)

* [Step-Up/Step-Down Voltage Regulator 5V S7V7F5](https://www.pololu.com/product/2119)  

* [Li-Po Battery 7.4V 300mAh](https://hobbyking.com/en_us/turnigy-nano-tech-300mah-2s-45-90c-lipo-pack.html)

* [QTR-8RC Reflectance Sensor Array](https://www.pololu.com/product/961)   

* [Micro Metal Gearmotor HPCB 6V (10:1, 3000 RPM)](https://www.pololu.com/product/2363) 2x

* [Solarbotics RW2i Wheels](https://solarbotics.com/product/rw2i/) x2 

* [3/8" Ball Caster](https://www.pololu.com/product/956)  

* [6x6x6 mm Push Button](https://www.sparkfun.com/products/97)  x2

* [1k Ohm Resistor](https://www.digikey.com/product-detail/en/CF14JT1K00)  x4

## How It Works  
This project implements a **PID-controlled line follower robot** that adjusts motor speeds dynamically to stay on track. The system consists of a **sensor array**, an **Arduino microcontroller**, a **PID controller**, and a **motor driver** to regulate movement.  

![image](https://github.com/user-attachments/assets/6d8a043d-c09c-49d5-9b8c-8a1c3513ce3c)



### **Working Principle:**  

1. **Line Detection**  
   - The **sensor array** continuously reads the position of the line.  
   - This data is sent to the **Arduino** for processing.  

2. **PID Control Algorithm**  
   - The Arduino calculates a **PID correction value** based on the error (deviation from the desired path).  
   - This correction adjusts the speed of the motors to bring the robot back to the center of the line.  

3. **Motor Speed Adjustment**  
   - The PID value influences the **motor speed**, ensuring smooth and stable movement.  
   - The corrected speeds are sent to the **motor driver**, which controls **Motor A and Motor B**.  

4. **Continuous Correction**  
   - The system continuously reads new sensor data, recalculates the error, and updates motor speeds in real-time.  
   - This ensures efficient line tracking, even at high speeds or with curves in the path.  

### **Why Use a PID Controller?**  
Unlike basic line followers that use a simple on/off control (where the motors turn left or right based on a threshold), the **PID controller** provides a smoother, more stable response. It helps the robot:  
- Reduce oscillations  
- Improve accuracy on curves  
- Maintain speed without overshooting  

## Schematic
![image](https://github.com/user-attachments/assets/faf7a3ab-59dd-475c-b7c7-05e9dfde15fb)

## PID Control    

### **Breakdown of the PID Formula:**  

- **Proportional Term (P)**: `P = error`  
  - Corrects the current error between the desired position and the measured position.  

- **Integral Term (I)**: `I = I + error`  
  - Compensates for small but persistent errors that are not corrected by the proportional component alone.  

- **Derivative Term (D)**: `D = error - lastError`  
  - Responds to rapid changes in error, preventing overshoot and oscillations in control.  

The final motor speed is determined using the formula:  
`int motorspeed = Kp * P + Ki * I + Kd * D;`  
where **Kp, Ki, and Kd** are tuning parameters that adjust the influence of each term on the system.  

This approach ensures smooth and stable motion control, minimizing deviations from the intended path.

## Conclusion

Through this project, I deepened my understanding of PID control and successfully applied it to a real-world scenario, enabling the robot to follow a line efficiently. Additionally, I had the chance to enhance my skills in soldering electronic components onto PCB boards, which was crucial for assembling the hardware. This project was a great learning experience, allowing me to integrate both software and hardware in robotics, further strengthening my knowledge of control systems, electronics, and their practical applications.
