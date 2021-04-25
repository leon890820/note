# 11/2 Related Work
###### tags: `robot` `MRL` `report`
Yu-Yang Chen
Department of Mathematics
National Central University
2020.11.2

<img src='https://codimd.mcl.math.ncu.edu.tw/uploads/upload_1ea0f460ad50d670af23b43798251732.png'  width=250px>


---

### Hardware

https://github.com/miguelasd688/4-legged-robot-model

https://hackaday.io/project/171456-diy-hobby-servos-quadruped-robot

https://www.thingiverse.com/thing:3445283

https://github.com/mike4192/spotMicro

---

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_b34782f30bf2d394d24def426dbc38d0.png)


---
### Foot design for a hexapod walking robot
Krzysztof Walas
Institute of Control and Information Engineering, Poznan University of Technology

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_d34d3d6653034026b79d3125909391a7.png)


---

### Playing Atari with Deep Reinforcement Learning
Volodymyr Mnih Koray Kavukcuoglu David Silver Alex Graves Ioannis Antonoglou
Daan Wierstra Martin Riedmiller
DeepMind Technologies

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_e8a333b4f03efdf66d5c3c7bc82761c6.png)

----

#### method:
convolutional neural network, trained with a variant of Q-learning, whose input is raw pixels and whose output is a value function estimating future rewards.


---

### Learning to Walk via Deep Reinforcement Learning
Tuomas Haarnoja;1;2, Sehoon Ha;1, Aurick Zhou2, Jie Tan1, George Tucker1 and Sergey Levine1;2
1Google Brain 2Berkeley Artificial Intelligence Research, University of California, Berkeley

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_59427921fec3826e0199a8e24aa16449.png)


----

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_b628f4f537ae953add243d5ae01d6d4d.png)

#### method : 
deep RL algorithm based on maximum entropy RL
#### problem:
poor sample complexity and sensitivity to hyperparameters.
#### web : 
https://sites.google.com/view/minitaur-locomotion/

---

### The Crawler, A Class Room Demonstrator for Reinforcement Learning.
Michel Tokic and Wolfgang Ertel and Joachim Fessler
ZAFH Servicerobotik

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_17813b9bf8cece370dfff556d591d6d2.png)

----

#### method : 
reinforcement learning

#### result : 
learns to move forward within about 15 seconds in real time.
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_84b050f3a11bfb5af5714464d3efacdc.png)

----

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_201b9844349302c0b39ba2e89d3faaee.png)


---

### Learning Agile and Dynamic Motor Skills for Legged Robots
JEMIN HWANGBO1*, JOONHO LEE1, ALEXEY DOSOVITSKIY2, DARIO BELLICOSO1, JOONHO LEE1,
Compiled January 28, 2019

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_80da46b349df4b1488f4602379a89c03.png)



----

#### method : 
training a neural network policy in simulation and transferring it to a state-of-the-art legged system(ANYmal robot, a sophisticated medium-dog-sized quadrupedal system.)

#### result : 
leverage fast, automated, and cost-effective data generation schemes

----

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_825554a711c7856bf44384bcf640c3ff.png)


----

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_23443fc087698e1761ea31a3f59ad338.png)

---
### ANYmal - A Highly Mobile and Dynamic Quadrupedal Robot*
2016 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)
Daejeon Convention Center
October 9-14, 2016, Daejeon, Korea



![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_e009c2f22e47fd7a51eeff8e1ac97de0.png)


---

### Dynamic Locomotion in the MIT Cheetah 3 Through Convex Model-Predictive Control
Jared Di Carlo1, Patrick M. Wensing2, Benjamin Katz3, Gerardo Bledt1,3, and Sangbae Kim3
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_be75917a4bebc53beaa8f184b76e8ceb.png)


----

method : model predictive control (MPC)

result: The robot achieved forward speeds of up to 3 m/s, lateral speeds up to 1 m/s, and angular speeds up to 180 deg/sec.

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_b201c1926ef1ab36ba3598f4c1cbf671.png)


---


### Inverse Kinematic Analysis Of A Quadruped Robot
Muhammed Arif Sen, Veli Bakircioglu, Mete Kalyoncu
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_71e250c15853ceb6c7136aff06c0f424.png)

----

method : Inverse Kinematic Analysis

---

### Sim-to-Real: Learning Agile Locomotion For Quadruped Robots
Jie Tan1, Tingnan Zhang1, Erwin Coumans1, Atil Iscen1,
Yunfei Bai2, Danijar Hafner1, Steven Bohez3, and Vincent Vanhoucke1
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_1e6fc1bb1b4a667b0eb50cd5c5ee2457.png)


----

method: deep reinforcement learning

result:After learning in simulation, a quadruped robot can successfully perform both gaits in the real world.


---

### Asynchronous Methods for Deep Reinforcement Learning
Volodymyr Mnih1 VMNIH@GOOGLE.COM
Adrià Puigdomènech Badia1 ADRIAP@GOOGLE.COM
Mehdi Mirza1;2 MIRZAMOM@IRO.UMONTREAL.CA
Alex Graves1 GRAVESA@GOOGLE.COM
Tim Harley1 THARLEY@GOOGLE.COM
Timothy P. Lillicrap1 COUNTZERO@GOOGLE.COM
David Silver1 DAVIDSILVER@GOOGLE.COM
Koray Kavukcuoglu 1 KORAYK@GOOGLE.COM
1 Google DeepMind
2 Montreal Institute for Learning Algorithms (MILA), University of Montreal

---


### Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_53374698441520b042df94e020a5ddcd.png)

---

### A. Iscen, K. Caluwaerts, J. Tan, T. Zhang, E. Coumans,V. Sindhwani, and V. Vanhoucke. Policies modulating trajectory generators. In Conference on Robot Learning (CoRL). PMLR.

----

#### method :
Policies Modulate Trajectory Generators (PMTG)

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_23fe56a92993842ce9313a8adc948944.png)

---

### G. Berseth, C. Xie, P. Cernek, and M. Van de Panne.Progressive reinforcement learning with distillation for multi-skilled motion control. International Conference on Learning Representations (ICLR), 2018.


----

#### method: 
progressive learning and integration via distillation (PLAID)

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_87aa498378cc5bf3bd08a38c04bd9f30.png)



---

### N. Heess, S. Sriram, J. Lemmon, J. Merel, G. Wayne, Y. Tassa, T. Erez, Z. Wang, A. Eslami, M. Riedmiller, et al. Emergence of locomotion behaviours in rich environments. arXiv preprint arXiv:1707.02286, 2017.

https://www.youtube.com/watch?v=hx_bgoTF7bs&feature=youtu.be

----

method: 

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_d81491b2c2797a1f750b706c001f598a.png)


---

### X. B. Peng, G. Berseth, and M. Van de Panne. Terrainadaptive locomotion skills using deep reinforcement learning. ACM Transactions on Graphics (TOG), 35 (4):81, 2016.


----

#### method: 
deep reinforcement learning (DeepRL)、 mixture of actor-critic experts (MACE)

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_f9d64c8656fd653917b00d9f1bdfcf2c.png)

----


#### contribute

MACE learns more quickly than a single actorcritic approach and results in actor-critic experts that exhibit specialization.

#### code

https://www.cs.ubc.ca/~van/papers/2016-TOG-deepRL/index.html


---

### Z. Xie, G. Berseth, P. Clary, J. Hurst, and M. van de Panne. Feedback control for cassie with deep reinforcement learning. arXiv preprint arXiv:1803.05580, 2018.
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_19b44c01dca7e57576d21d24f876f1be.png)

----


### method:

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_7bd028c41eae885f11672264c876b914.png)

---

## QAQ


---

1. Which paper is your benchmark from reference papers.
2. This paper has github code or not? You can implement it?.
3. What's the gap in this field? Your research topic is in this gap?

---

### feedback:

1. Reference format.
2. The input information (sensors?) of the benchmark. For example, we don't have "Torque" information for cheap servo motors. Hence, check the black box (system).

3. Need to compare each paper.
---

Mo: 找論文要幹嘛:
A: 主要是找paper的演算法之間的差別，再決定使用哪一種方法

yee: 目標
A: 要可以讓機器狗走路

好: sim to real 有跟上學期做的一樣嗎
A: 沒有

hsin: 硬體加裝要怎麼辦
A: 挖洞





---