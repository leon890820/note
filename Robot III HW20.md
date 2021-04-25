# Robot III HW2
###### tags: `mrl` `project`

https://ieeexplore.ieee.org/abstract/document/5509226
https://onlinelibrary.wiley.com/doi/abs/10.1002/ad.2394
https://link.springer.com/chapter/10.1007/978-981-13-7983-3_39
https://ieeexplore.ieee.org/abstract/document/8260889
https://ieeexplore.ieee.org/abstract/document/8206174
https://cjme.springeropen.com/articles/10.1186/s10033-020-00485-9
https://ieeexplore.ieee.org/abstract/document/8642912
https://ieeexplore.ieee.org/abstract/document/8793669
https://www.mdpi.com/2076-3417/9/7/1335
https://ieeexplore.ieee.org/abstract/document/7354099
https://onlinelibrary.wiley.com/doi/abs/10.1002/zamm.200310068

## Related Work

### A.  Training in simulators
Since  quadruped  robots  could  be  damaged  during  learning  processing,  parts  of  research  let  the  robot  learn  to  walk  insimulators.  In  [5],  this  paper  demonstrates  the  computer  can  play  games  via  DQN.  In  [6]  [7],  robots  are  trained  usingDQN with inertial measurement unit(IMU) and motors’ torque feedback to calculate robots’ actions. In [8], reinforcementlearning methods are applied to locomotion of 2-legs robot. In [6], Proximal Policy Optimization (PPO) is adopted to trainRoboschoolHumanoidFlagrun. It trains 2-legs human in a simulator to walk forward toward the target with some traps onthe way. Upon the human touches the target, it will get positive rewards. If the human falls down, it gets negative rewards.DeepMind also proposes PPO to train a quadruped robot in complex environment [9]. The PPO could learn policies for awhile but it strikes a good balance on the speed of the optimization. 
In  [10],  the  self  scaling  reinforcement  (SSR)  learning  algorithm  was  proposed  to  deal  with  the  problems  in  continuousaction  domains.  The  learning  architecture  was  developed  to  solve  complex  control  problems.  In  [11][12],  Policy  gradient(PG) is applied to train a quadruped robot. This paper describes a learning framework for a central pattern generator basedbiped  locomotion.  The  PG  is  efficient  on  high-dimension  and  continuous  action  space  but  takes  much  time  on  training.The  goal  is  to  search  the  sets  of  possible  parameters  for  finding  the  fastest  walking.  The  humanoid  robot  is  trained  byreinforcement learning (RL) [13]. Deep reinforcement learning (DRL) is to train a robot to walk [14]. In [15], this researchadopts  a  mixture  of  actor-critic  experts  (MACE)  approach  that  learns  dynamic  locomotion  skills  on  a  rough  terrain.  TheMACE learns more quickly than the actor-critic approach.
### B.  real robot
One of the simplest robots is called crawler, which consists of two motors [16]. It adopts reinforce learning to learn howto move forward by Q-table. However, it can’t solve the locomotion problem of quadruped robots since the states are hugeand the learning processing cannot converge in short time. To avoid damaging of the robots while learning, the researchersproposed a method, sample-efficient DRL algorithm based on maximum entropy [17] that requires minimal per-task tuningand a modest number of trials to learn neural network policies. The method can acquire a stable gait from scratch directlyin the real world in about 2 hours to without simulations.The  research  in  [18]  inspires  the  development  of  robotic  vehicles  that  use  legs  for  their  locomotion,  thereby  embracingnature’s mobility solutions. This work introduces a hierarchical framework to automatically decompose complex locomotiontasks on real robot [19].
### C.  Simulation-to-real

Since quadruped robots could damage themselves while learning procedures, learning in simulators and then transferring toa real robot are feasible approaches. These ‘sim-to-real’ methods attempt to reduce the gap between learning in simulationand  real-world  [20].  The  Real  Miniatures  learned  to  gallop  using  deep  reinforcement  learning  [4][21].  These  researchesdecrease  the  error  between  in  simulation  and  in  reality  via  adding  perturbations  in  simulation  and  calculating  the  latency.However,  the  mechanism  of  this  robot  is  different  from  that  of  this  project.  The  work  in  [22]  proposes  Dynamics  andDomain Randomized Gait Modulation with Bezier Curves(D2−GMBC) and trained by Augmented random search (ARS)to overcome the non-terrain plane. ARS can get more rewards than PPO and DDPG at the same trials

### D. Recently Technology

Many quadruped robots are trafficed in the market, for instance, BigDog ,LS3 or Spot Classic. Some of paper use online Zero Momentum Point(ZMP) to execute dynamic gaits including trot, pace and dynamic lateral walk.



## Reference







