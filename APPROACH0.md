# APPROACH
###### tags: `robot` `MRL` `paper`


## The proposed method

I will use [1] to be my benchmark since its approach is most adopt my project. In benchmarch, they use Proximal Policy Optimization(PPO) [2] because it is a stable on-policy methon and can be easily paralleized [3]. In this paper, they propsed some problem: reality gap. A robot is trained in simulator well, not also be trained well as real world. However, if you train on real-bot, it may falldown when it is training which will damage the robot. To overcome the gap, must to solve two challenge: learning controllable locomotion policies and transferring the policies to the physical system. There have three approach to increase learining controller: dynamics randomization, perturbation forces and compact design of observation space.

In this paper, there robot have only two actuators for each leg. Instead my robot which have three mortor for each leg. But it also can be through a Pulse Width Modulation (PWM) singnal. The Minitaur is equipped with motor encoders that measure the motor angles and an IMU that measures the orientation and the angular velocity of its base. Since the microcontroller can't run neural network, they install an Nvidia Jetson TX2 on robot. Before run the robot in reality, they build a phisics simulation using PyBullet [4].  

They solve the model by using policy gradien method. the observation include the roll, pitch, yaw, the angular velocity, and the mortor angles. Action space include legs in leg space and motor space [5] [6] . They don't include all observation space since it may be noise. For example, they exclude the yaw of the base because the measurement drift quickly. They design the reward function to encourage faster forward running speed and penalize high energy consumption. 

1. What’s the problem you try to solve? What’s the gap?
Training the robot on simulation and transfer it to reality.
2. What’s the algorithm of the benchmark?
Proximal Policy Optimization(PPO).
3. What’s the algorithm of the proposed approach?
Same as the benchmark.
4. What does the benchmark demonstrate?
They show that deep RL can be applied to learn agile locomotion automatically for robots.
5. What will your approach demonstrate?
I'll make the robot stand-up and trot.






[1] Tan, J., Zhang, T., Coumans, E., Iscen, A., Bai, Y., Hafner, D., Bohez, S., and Vanhoucke, V. Sim-to-real: Learning agile locomotion for quadruped robots. In Robotics: Science and Systems (RSS),
2018.

[2] John Schulman, Filip Wolski, Prafulla Dhariwal, Alec Radford, and Oleg Klimov. Proximal policy optimization algorithms. CoRR, abs/1707.06347, 2017.

[3] Danijar Hafner, James Davidson, and Vincent Vanhoucke. TensorFlow agents: Efficient batched reinforcement learning in TensorFlow. arXiv preprint arXiv:1709.02878, 2017.

[4] Erwin Coumans and Yunfei Bai. Pybullet, a python module for physics simulation in robotics, games and machine learning. http://pybullet.org, 2016–2017.

[5] Gavin Kenneally, Avik De, and Daniel E Koditschek. Design principles for a family of direct-drive legged robots. IEEE Robotics and Automation Letters, 1(2):900–907, 2016.

[6] Krzysztof Choromanski, Atil Iscen, Vikas Sindhwani, Jie Tan, and Erwin Coumans. Optimizing simulations with noise-tolerant structured exploration. In Robotics and Automation (ICRA), 2018 IEEE International Conference on. IEEE, 2018.






