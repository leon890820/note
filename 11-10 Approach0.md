---

slideOptions:
  transition: convex
    
---

# 11/10 Approach
###### tags: `MRL` `robot` `report`
Yu-Yang Chen
Department of Mathematics
National Central University
2020.11.10

https://arxiv.org/pdf/1804.10332.pdf

---

## ABSTRACT

### problem: 
In robotics, policies trained in simulation often do not transfer to the real world.

### solution
By improving the physics simulator and learning robust policies.

---

## I.INTRODUCTION


Classical approaches often require extensive experience and tedious manual tuning.

Recently, we have seen tremendous progress in deep reinforcement learning

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_3820801fd125dbf15b4d032917d62e8f.png)


----

However, most of these studies are conducted in simulation, and a controller learned in simulation often performs poorly in the real world.


----

<img src='https://media.giphy.com/media/hUijeqgB7yRWp6SgAX/giphy.gif' >

<img src='https://media.giphy.com/media/tIoVPwJgRxktYOEeNd/giphy.gif'>

----

1) learning controllable locomotion policies
2) transferring the policies to the physical system.



----

To narrow the reality gap 
1. dynamics randomization
2. perturbation forces
3. compact design of observation space.



----

### contributions
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_8b3d19a7851967d12306c98aa9ee3715.png)



---

## II.RELATED WORK

1. Legged Locomotion Control
2. Overcoming the Reality Gap

----

Optimizing controllers:
1. black-box
2. Bayesian optimization


it is challenging to scale these methods to high-dimensional control space.

----

deep RL:

Proximal Policy Optimization (PPO)


----

1. system identification
2. matching the robot behaviors in the simulated and the real world
3. Gaussian Processes

---

## III.ROBOT PLATFORM AND PHYSICS SIMULATION

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_fab6abe9579d3dabf35a5c94fd5bd252.png)

---

## IV.LEARNING LOCOMOTION CONTROLLERS

A. Background

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_55ac72315a43ffbe33d4dd93685c6bba.png)

D is the distribution of initial states $s_0$, 
$P_{sas'}$ is the transition probability;
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_fa884de6ed4bb5d7bd79a38b01227307.png)

----

B. Observation and Action Space

observations include the roll, pitch, and the angular velocities of the base along these two axes, and the eight motor angles.

----

For example, the IMU also provides the yaw of the base. We exclude it because the measurement drifts quickly. The motor velocities can also be calculated but can be noisy. 

----

action sapce:

leg space and motor space
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_915c1ff4c4b326fe72d9dd979a9ae7bd.png)


----

C. Reward Function

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_4e9f4d7cf8e54bb81c5d368393345600.png)
$p_n$ and $p_{n−1}$ are the positions of the Minitaur’s base at the current and the previous time step respectively
$d$ is the desired running direction
$∆t$ is the time step 
$τ$ are the motor torques  
$q$˙ are the motor velocities 
$w$ is the weight that balances these two terms.

---

## V.NARROWING THE REALITY GAP
A. Improving Simulation Fidelity
a) Actuator Model:
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_18f98ca5ec9f8058163490b950227376.png)
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_191cbce0b726e42ac1778dc41464419f.png)

----

b) Latency:
It is the time delay between when a motor command is sent that causes the state of the robot to change and when the sensor measurement of this change is reported back to the controller.


----

B. Learning Robust Controllers
1. randomizing the dynamic parameters
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_2537110e3a3945b627302c36e1328991.png)

----

2. add random perturbations
The perturbations can knock the simulated Minitaur out of balance so that it needs to learn how to recover balance from different situations.


----

3. design of the observation space
If the observation space is high dimensional, the learned policy can easily overfit the simulated environment, which makes it difficult to transfer to the real robots. 


---


## VI.EVALUATION AND DISCUSSION

https://www.youtube.com/watch?v=lUZUr7jxoqM

https://github.com/bulletphysics/bullet3/tree/master/examples/pybullet/gym/pybullet_envs/minitaur/envs

---

## VII. CONCLUSION

We have shown that deep RL can be applied to learn agile locomotion automatically for robots.

### future work

1. Learning locomotion policies that can dynamically change running speed and direction. 
2. It would be interesting to extend this work to handle complex terrain structures by integrating vision as part of sensory input.

---

QA

---

1. What’s the problem you try to solve? What’s the gap?
2. What’s the algorithm of the benchmark?
3. What’s the algorithm of the proposed approach?
4. What does the benchmark demonstrate?
5. What will your approach demonstrate?


---

feedback


KS:
1. 要搞清楚DRL的input跟output,模擬器跟現實中馬達跟IMU的差距(速度、電流、扭力)
2. run 她的code 搞清楚它內部的網路設計。
3. 先在模擬器上實現，可以先把模擬器的馬達扭力之類的拔掉。
4. 多買幾個IMU裝在馬達上面。

好喔: 要自己想方法實作嗎。
A: 先用廉價版的方法。

MO: 之前的paper都沒有使用扭力就做出來的嗎
A: 可能要回去再看一下

Hsin: 機器人不一樣，模擬器跟現實差距會不會不一樣。
A: try and error

Yee: 用這篇paper實作嗎
A: 對
























