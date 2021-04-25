---

slideOptions:
  allottedMinutes: 20
  autoSlideStoppable: true
  spotlight:
      enable:true
transition: convex
#  Proximal Policy Optimization Algorithms
    
---

# Proximal Policy Optimization Algorithms
###### tags: `report` `program`
數學3B
陳宇揚、蔡沐霖

Department of Mathematics
National Central University

2021.1.06

---

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_6bcae240e8fbbf5c8c0a60b7dcbc87be.png)


---

## Introduction

<!-- .reveal .slides:text-align- left -->



$\quad$In recent years, several different approaches have been proposed for reinforcement learning with neural network function approximators. 

$\quad$However, there is room for improvement in developing a method that is scalable , data efficient, and robust.

$\quad$The leading contenders are deep Q-learning , and trust region policy gradient methods(TRPO).

----

$\quad$However, Q-learning fails on many simple problems and is poorly understood.

$\quad$TRPO is relatively complicated,and is not compatible with architectures that include noise or parameter sharing.


$\quad$This paper seeks to improve the current state of affairs by introducing an algorithm that attains the data efficiency and reliable performance of TRPO, while using only first-order optimization.

---

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_6cce89b2a8a9ca21bf754e236ad9ef78.png)


---


## Background
### DQN(Deep Q-learning Network)

----

### Value Based

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_6e0a0b3d701cfc5a3704172ec104a128.png)

----

### algorithm 
<img src='https://codimd.mcl.math.ncu.edu.tw/uploads/upload_e3e650d0ae753f261debd4c3664e333f.png' width=700>




---

## Policy Gradient


----

### Policy-based
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_a53e07156946ffb8a99c245993c185da.png)


----

### algorithm 

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_e33d9392f5d7a814ae90d63e27e000b4.png)


---

## Actor Critic and Deep Deterministic Policy Gradient (DDPG)

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_7b01ad909f8c6fdb734dd776f079ba5c.png)




---

### PPO


----

### Algorithm
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_53a9fbcf7c5bfe23fe15089b7bcf57d4.png)


---

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_2426dfd546e727ffba6f478548a918fa.png)

---

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_579d99341f1a4502a02f41af44eae273.png)

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_e204768f94b5ed0e34c93fe147df91d4.png)

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_4970a493e4b3d02bde64eff6d2cf131a.png)


----

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_7e8d64467e5497dc5a1e60d2f3d89452.png)



---

### demo
    
----
    
### OpenAI

<video src='https://mofanpy.com/static/results/reinforcement-learning/6-4-demo_openai.mp4'  controls></video>



----

### deep mind
<img src='https://mofanpy.com/static/results/reinforcement-learning/6-4-demo_google2.gif'></img>




----


<img src='https://mofanpy.com/static/results/reinforcement-learning/6-4-demo_google1.gif'></img>

---

### Experiment
#### Comparison of Surrogate Objectives
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_2288984a93c4e39bb25f0008fcae77a6.png)
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_c673f152e69396c96fd128d9e821f00d.png)

----

Comparison to Other Algorithms in the Continuous Domain
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_5602e631482498f5979ceec4bf521fc7.png)


----

Showcase in the Continuous Domain: Humanoid Running and Steering
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_62c86d4abfccc614d634cda365dab264.png)

----

Comparison to Other Algorithms on the Atari Domain
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_9f3b267a8a86becd29f99eb1826e5b27.png)

----

<img src='https://codimd.mcl.math.ncu.edu.tw/uploads/upload_648277e791816b4760f80f740de6c0b5.png' width=500></img>


---

### Conclusion
* **PPO** use multiple epochs of stochastic gradient ascent to perform each policy update. 
* These methods have the stability and reliability of **trust-region** methods but are much simpler to implement, applicable in more general settings (for example, when using a joint architecture for the policy and value function), and have better overall performance.


---

## source

https://arxiv.org/pdf/1707.06347.pdf

https://mofanpy.com/tutorials/machine-learning/reinforcement-learning/DPPO/

---

## QA

---




