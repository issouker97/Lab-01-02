# Lab 01 & 02: Robots planning to avoid collision and obstacles 

# Introduction:
The primary objective of the laboratory experiment is to develop a control strategy ensuring the safe navigation of robots, minimizing collisions, and ensuring smooth operation when encountering random obstacles while pursuing their designated flags. We will systematically evaluate different approaches, considering their advantages and disadvantages, and subsequently implement enhancements to address the specified requirements effectively.

In order to run this project, you should follow these steps: 

# STEP 01: Clone the Project repository: 

cd ~/catkin_ws/src && git clone https://github.com/KTBE/Mission_Coordination_project.git

cd ~/catkin_ws && catkin_make && source ~/catkin_ws/devel/setup.bash

# STEP 02:  You must make the agent.py file executable.
Copy and peast these commands on your window: 

cd /home/user/catkin_ws/src/Mission_Coordination_project/evry_project_strategy/nodes
chmod +x agent.py
cd ~

# STEP 03: Simulation time ! 

After excuting the agent.py file , now let's go toward the simulation by runing each command of these following in a separate window: 

To run the simulation, open a new terminal and run the following instruction:
roslaunch evry_project_description simu_robot.launch

This command will allow you to work with the three simulating robots at the same time:
roslaunch evry_project_strategy agent.launch

# STEP 04: simulating some tasks 

# First Simulation: Moving one robot safely to its corresponding flag and stop it at this position.

In order to visualize the behaviour of the 3 robots and make them stop in the corresponding flag, i  did design the code that you will find it under the name Q6.txt
please, copy and peast the code on the agent.py file then excute the file 
after excuting the file follow the commands on the step 03 as it was defined 

# Second Simulation: Designing a PID controlle

In this part, we are going to implement a PID controller in order to move the robot with high speed when it is further from the target flag and decrease the speed as it is approaching the appropriate flag 
I did create this code,which enable a robot control system using a PID controller to adjust the robot's velocity based on the distance to a target flag. The robot smoothly approaches the flag with a maximu speed is 2.0, then slowing down with a minimum speed 0.5 as it gets closer to it from a specific distance equal to 5.0 acccording to the setting code, and stops when it reaches the specified target distance

In ordert to visualize the behaviour of the 3 robots and make them stop in the corresponding flag, i  did design the code that you will find it under the name Q7.txt
please, copy and peast the code on the agent.py file then excute the file 
after excuting the file follow the commands on the step 03 as it was defined


# Third Simulation: Sequential Robot Activation ( time delay of robots) 

In this part, we are tasked to elaborate a technique that allows the three robots to safely reach their tracking flag without any collision with each other during their navigation to reach the appropriate flag.

In order to satisfy the requirement, I developped a code based on a delay among the three robots. In other words, each robot will start in a specific time different from others which will help us to avoid colliding and assure a safe navigation of robots.

In order to visualize the behaviour of the 3 robots and make them stop in the corresponding flag, i  did design the code that you will find it under the name Q8.txt
please, copy and peast the code on the agent.py file then excute the file 
after excuting the file follow the commands on the step 03 as it was defined

# Simulation number 04:  Fine-tunning angles for robots motion:

In order to deal with avoiding collision witnessed previously, I did fine-tune the robot's behavior through setting a control strategy as follow: 
The control strategy was implemented based on the distance to the flag. When the distance is greater than 30, the robot sets an angular velocity of 0.02, and when the distance is less than 30, it sets an angular velocity of -0.06. Additionally to this, the robot checks if it has reached the flag (distance <= 1.5) and stops if the condition is satisfied.
The values of angular velocities as well as the condition of distance threshold was set after several simulation attempts.

In order to visualize the behaviour of the 3 robots and make them stop in the corresponding flag, i  did design the code that you will find it under the name angles_tunning.txt
please, copy and peast the code on the agent.py file then excute the file after excuting the file follow the commands on the step 03 as it was defined

# Simulation number 05:

In order to guide each robot to its corresponding flag,I thought about another approach which is more robust and effective. This approach is based on disignning guidance under a 3rd-order polynomial time scaling to generate a trajectory for each robot

The strategy uses a polynomial-based approach to guide each robot smoothly towards its respective flag while dynamically adjusting the heading to avoid collisions. The trajectory tracking and collision avoidance are achieved through careful control of linear and angular velocities based on the polynomial coefficients and heading error calculations.

In order to visualize the behaviour of the 3 robots and make them stop in the corresponding flag, i  did design the code that you will find it under the name Scond_solution.txt
please, copy and peast the code on the agent.py file then excute the file after excuting the file follow the commands on the step 03 as it was defined

# Conclusion: 

Overall, the outcomes of our lab show and demonstrate that the 3rd Order Polynomial Time Scaling strategy, combined with the collision avoidance logic by adjusting robot angles, demonstrated robust and effective navigation. This approach allowed for dynamic trajectory planning, ensuring smooth paths and effective avoidance of collisions. In contrast, the sequential activation approach with a time delay among robots showed limitations in robustness. The delay mechanism, while helpful in preventing immediate collisions, might not adapt well to dynamic environments or unexpected changes. Therefore, the polynomial time scaling strategy stands out as a more adaptable and robust solution for navigating robots in complex scenarios.

# Further work/Enhancement: 

I would like to implement another method, which is called the attractive and repulsive potential fields, that I have tried before in the lab of flight planning and it worked perfectly to track a target with avoiding obtacles
The repulsive forces work alongside the attractive forces to guide the robot in approaching the target and going away from the obstacle
The combination of this method with the 3rd order polynomial time scaling will lead to outstanding results for robot path planning and obstacles avoidance, which deserves an attempt !

                               
                               
                                                            Enjoy guys ! 








