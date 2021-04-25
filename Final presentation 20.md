---
slideOptions:
  allottedMinutes: 17
  autoSlideStoppable: true


---

# Final presentation 2
###### tags: `robots` `report` `MRL`
## Dog of mathematics in NCU

 Yu-Yang Chen
Department of Mathematics
National Central University
2021.01.04

---

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_944ac85e39a1c920aec8b98cfb6693c4.png)



---

### outline
* Project introduction
* Hardware
* Problem formulation
* Methon
* Result

---

### Project introduction

benchmark:https://sites.google.com/view/d2gmbc

----

<img src='https://codimd.mcl.math.ncu.edu.tw/uploads/upload_07b8609bfbcdd6b2c73838b0527beff4.png' width=600>

> <i class="fa fa-image"></i> Spot mini

----

<img src='https://codimd.mcl.math.ncu.edu.tw/uploads/upload_b4f0d70f761ffae855cb0547be0b43d3.jpg' width=600>

---

### Hardware

https://github.com/mike4192/spotMicro

----

https://codimd.mcl.math.ncu.edu.tw/1tsuZrPZRbeDGIgkLvJ6CQ

---

### Problem formulation

----

observation space:

$[r,p,\omega,v,S(t)] \in R^{12}$

action space:
$$
(\Delta f_{xyz},\beta)=\pi(o_t,\theta)
$$
Here $\Delta f_{xyz}=[\Delta f^{FL}_{xyz},\Delta f^{FR}_{xyz},\Delta f^{BL}_{xyz},\Delta f^{BR}_{xyz}]$,  $\beta ={\psi,\delta}$, where $\psi$  is the clearance height of the foot above the ground and $\delta$ is a virtual ground penetration depth.

----

reward function:
$r=\Delta x -10(|r|+|p|)-0.03 \Sigma|\omega|$

----

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_7620768db747f6bb131b18c04da5da12.png)

---

### methon 

DQN

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_fb8b18b02785f9158769651efbe7b8c9.png)



---

### result

<img src='https://media.giphy.com/media/cbTm3z6ALlRjyZA6xp/giphy.gif'>

---

#### no train
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_d6d3327e1b1ff84bfa272c1442f287d9.png)
#### train
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_124bb95e79b3610d0eff350356ab81f9.png)



---

#### no train
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_c1a45403db2ae239c6eaac32f5ece6f3.png)
#### train
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_8694ba65aae0982df90adf5b2542ef53.png)

---


### future work


---

* Put the code on the rral robot.


---

### QAQ

---



### feedback

---


![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_4c958c29af856cca0c170da7663873bc.png)


