# Project report
###### tags: `mrl` `report` `robot`

## Abstract

$\quad$We train a quadruped robot in simuator by using Deep Q Network with Bezier Curves(DQN) and transfer to realworld, allowing them to traverse uneven terrain without sensing foot impacts. We present two result that trains on defference terrain. We compare the augmented random search(ARS) [1] and Deep Q Network. We find that DQN trains very slow. ARS can train faster and more stable.

## I. INTRODUCTION

$\quad$ In this project, we want to make a quadruped robot walk itself in real world. To achieve the gold, we train the robot on the simulator first. Specifically, we model leg trajectories using Bezier curve gaits from [2] and augment the underlying gait parameters using a policy trained with DQN in simulation. We have to overcome some problems for sim-to-real. The reality gap[3],[4], is caused by model discrepancies between the simulated and the real physical system. The latency is the time delay between when a motor command is sent that causes the state of the
$\quad$robot to change and when the sensor measurement of this change is reported back to the controller. This issue may cause fatal mistakes when we transfer the simulated-robot to real-robot. We will improve the algorism in the future.
$\quad$We assemble a quadruped robot model by using open $source^1$. Assemble the hardware by using $github^2$

1 Model of quadruped robot: https://www.thingiverse.com/thing:3445283
2 Hardware of quadruped robot: https://github.com/mike4192/spotMicro
## II. RELATED WORK

1. training on simulator
This seccsion shows that the robot trains on simulator. They train the computer by using DQL[5]. Train RoboschoolHumanoidFlagrun by using Proximal Policy Optimization(PPO)[6]. Train Robot in rich environment[7].Maximum Entropy[8].reinforcement learning to locomotion tasks[9][10][11][12][13][18].


2. Sim-to-real
This legged locomotion approach focuses on learning a policy in simulation and transferring it to a real robot.These ‘sim-to-real’ methods attempt to reduce the gap between learning in simulation and real-world evaluation. Real Minitaurs learned to gallop using deep reinforcement learning[14][15][17]. The work in [16] use Dynamics and Domain Randomized Gait Modulation with Bezier Curves($D^2-GMBC$) to overcome the non-terrain plane and make the robot walk perfectly. 

3. real robot
A simple robot[19] called crawler, which uses reinforce learning to train it forward. It slice the motors angle into five piece. It success crawler forward eventually.
Another project[17] train the robot on real, which has some risk: It may destory the hardward when it train or falldown.

## III. PROBLEM STATEMENT
A. General Formulation
We treat the learning problem as a partially observable Markov decision process (POMDP) where we have a set of uncertain observations of the robot’s state $o_t \in O$, a reward function $r_t = R(s_t, a_t)$ defining the quality of the locomotion task as a function of the state $s_t \in S$, and an action space $a_t \in A$ containing the set of control inputs to the system.A policy $a_t=\pi(o_t,\theta)$ map to $o_t$, where $\pi$ is the nueral network connect the obervations and the actions.Given this model, the goal is to find policy parameters $\theta$ such that the reward is maximized over a finite time horizon T using only partial observations of the state $o_t$.

B. Reinforcement Learning for Gait Modulation 
Let l be a label for the quadruped’s legs: FL (frontleft), FR (front-right), BL (back-left), BR (back-right). An open loop gait is a one-dimensional closed parametric curve $\Gamma(S(t),\zeta,\beta)$ embedded in $R^3$ and specifying the position of a foot in the frame of its corresponding hip. $S(t)$ : $R \rightarrow [0,1]$ is cyclic function.The leg is in stance for $S(t)=0$ and in swing $S(t)=1$.  $\zeta$ is contro input. $\beta$ is gait parameters.
![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_5aac8786f4c5509a9b752a61f7bfb344.png)

Fig. 1. System Diagram

the goad of the policy 
$$
(\Delta f_{xyz},\beta)=\pi(o_t,\theta)
$$
Here $\Delta f_{xyz}=[\Delta f^{FL}_{xyz},\Delta f^{FR}_{xyz},\Delta f^{BL}_{xyz},\Delta f^{BR}_{xyz}]$  $\beta ={\psi,\delta}$, where $\psi$  is the clearance height of the foot above the ground and $\delta$ is a virtual ground penetration depth.

The final foot positions are computed as a combination of the gait generator output and the policy residual:
$$
f_{xyz}=\Gamma(S(t),\zeta,\beta)+\Delta f_{xyz}
$$

where $f_{xyz} \in R^{12}$ is the vector of each three-dimensional foot position the robot should track. The policy both adds a residual term to the output and sets the $\beta$ parameter. Given the foot positions, the robot computes the inverse kinematics to move its leg joints to the appropriate angles as shown in Fig. 1.

## VI. ALGORITHM
Our observations $o_t \in R^{12}$ given $o_t=[r,p,\omega,v,S(t)]$. Where $r$ is the body roll, $p$ is the body pitch, $\omega$ is the body 3-axis angular velocity, $v$ is the body 3-axis linear acceleration and $S(t)_l$ is the phase of each leg.  
We use a deep network with three layers to train the robot, each layer has 64 nodes.Here, the policy outputs the nominal clearance height and virtual ground penetration depth of the Bezier curve and residual foot displacements that are added to the output of the Bezier curve.
The reward function is 
$$
r_t=\Delta x -10(|r|+|p|)-0.03\Sigma|\omega|
$$
where $\Delta x$ is the global distance traveled by the robot in horizental x-direction in one time step.





## V. Experiments

## VI. Conclusion







## REFERANCE
[1] $\quad$H. Mania, A. Guy, and B. Recht, “Simple random search provides a competitive approach to reinforcement learning,” arXiv preprint arXiv:1803.07055, 2018.
[2] $\quad$D. J. Hyun, S. Seok, J. Lee, and S. Kim, “High speed trot-running: Implementation of a hierarchical controller using proprioceptive impedance control on the mit cheetah,” The International Journal of Robotics Research, vol. 33, no. 11, pp. 1417–1445, 2014. [Online]. Available: https://doi.org/10.1177/0278364914532150
[3]$\quad$Sylvain Koos, Jean-Baptiste Mouret, and St´ephane Doncieux. Crossing the reality gap in evolutionary robotics by promoting transferable controllers. In Proceedings of the 12th annual conference on Genetic and evolutionary computation, pages 119–126. ACM, 2010.
[4]$\quad$Adrian Boeing and Thomas Br¨aunl. Leveraging multiple simulators for crossing the reality gap. In Control Automation Robotics & Vision (ICARCV), 2012 12th International Conference on, pages 1113–1119. IEEE,2012.
[5]$\quad$Bellemare, M. G., Veness, J. & Bowling, M. Investigating contingency awareness
using Atari 2600 games. Proc. Conf. AAAI. Artif. Intell. 864–871 (2012).
[6]$\quad$Schulman, J.; Wolski, F.; Dhariwal, P.; Radford, A.; and Klimov, O. 2017. Proximal policy optimization algorithms. arXiv preprint
arXiv:1707.06347.
[7]$\quad$N. Heess, S. Sriram, J. Lemmon, J. Merel, G. Wayne, Y. Tassa, T. Erez, Z. Wang, A. Eslami, M. Riedmiller, et al. Emergence of locomotion behaviours in rich environments. arXiv preprint arXiv:1707.02286, 2017.
[8]$\quad$ Haarnoja, T., Zhou, A., Abbeel, P., and Levine, S. Soft actor-critic: Off-policy maximum entropy deep reinforcement learning with a stochastic actor. arXiv preprint arXiv:1801.01290, 2018.
[9] Hamid Benbrahim and Judy A Franklin. Biped dynamic walking using reinforcement learning. Robotics and Autonomous Systems, 22(3-4):283–302, 1997.
[10] Russ Tedrake, Teresa Weirui Zhang, and H Sebastian Seung. Stochastic policy gradient reinforcement learning on a simple 3d biped. In Intelligent Robots and Systems, 2004.(IROS 2004). Proceedings. 2004 IEEE/RSJ International Conference on, volume 3, pages 2849–2854. IEEE.
[11] Gen Endo, Jun Morimoto, Takamitsu Matsubara, Jun Nakanishi, and Gordon Cheng. Learning CPG sensory feedback with policy gradient for biped locomotion for a full-body humanoid. In Proceedings of the 20th
national conference on Artificial intelligence-Volume 3, pages 1267–1273. AAAI Press, 2005.
[12] Nate Kohl and Peter Stone. Policy gradient reinforcement learning for fast quadrupedal locomotion. In Proceedings of the IEEE International Conference on Robotics and Automation, 2004.
[13] Masaki Ogino, Yutaka Katoh, Masahiro Aono, Minoru Asada, and Koh Hosoda. Reinforcement learning of humanoid rhythmic walking parameters based on visual information. Advanced Robotics, 18(7):677–697, 2004.
[14]Jie Tan, Tingnan Zhang, Erwin Coumans, Atil Iscen, Yunfei Bai, Danijar Hafner, Steven Bohez, and Vincent Vanhoucke.Sim-to-Real: Learning Agile Locomotion For Quadruped Robots. Google Brain,X Google DeepMind. 2019.
[15]JEMIN HWANGBO1, JOONHO LEE, ALEXEY DOSOVITSKIY, DARIO BELLICOSO, JOONHO LEE, VASSILIOS TSOUNIS, VLADLEN KOLTUN, AND MARCO HUTTER. Learning Agile and Dynamic Motor Skills for Legged Robots.Robotic Systems Lab, ETH Zurich.24 Jan 2019.
[16]Maurice Rahme, Ian Abraham, Matthew L. Elwin, Todd D. Murphey.Dynamics and Domain Randomized Gait Modulation with Bezier Curves for Sim-to-Real Legged Locomotion.2020.
[17]Z. Xie, G. Berseth, P. Clary, J. Hurst, and M. van de Panne. Feedback control for cassie with deep reinforcement learning. arXiv preprint arXiv:1803.05580, 2018.
[18]X. B. Peng, G. Berseth, and M. Van de Panne. Terrainadaptive locomotion skills using deep reinforcement learning. ACM Transactions on Graphics (TOG), 35 (4):81, 2016.
[19] The Crawler, A Class Room Demonstrator for Reinforcement Learning.

![](https://codimd.mcl.math.ncu.edu.tw/uploads/upload_87c5aad0e2d5b6e05cb7d59b1e174cbb.png)

