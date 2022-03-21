+++
date = "2021-08-19T15:30:00+09:01"
draft = false
title = "A Deep Reinforcement Learning Based Approach for Autonomous Overtaking" 
tags  = ["MA-DRL"]
categories = ["DRL"]


+++


ArXiv: [arXiv:xxxx.xxxxx](https://arxiv.org/pdf/xxxx.xxxx.pdf)


## Authors

- Xiaoxiang Li (EE, Tsinghua University) <lxx17@mails.tsinghua.edu.cn>
- Xinyou Qiu (EE, Tsinghua University) <qxy18@mails.tsinghua.edu.cn>
- Jian Wang (EE, Tsinghua University) <jian-wang@tsinghua.edu.cn>
- Yuan Shen (EE, Tsinghua University) <shenyuan_ee@tsinghua.edu.cn>


<small>\* Equal contribution.</small>


## Abstract

​	In this paper, we propose a deep reinforcement learning scheme, based on deep deterministic policy gradient, to
train the overtaking actions for autonomous vehicles. In contrast to conventional autonomous driving systems which require for
expensive LiDAR or visual cameras, our method uses low cost sensors like ultra-wide-band antenna arrays and inertial
measurement units to obtain easily available measurements such as distance, angle, and speed information. Our method
directly projects raw sensory measurements into continuous control signals for overtaking maneuvers. Simulation results
demonstrate that our method outperforms two other state-of-the-art algorithms. Besides, the technique can be generalized to
other areas of autonomous driving such as merging, platooning, formation, by modifying the parameters and conditions of the
reward function under the same framework.


<h2 id="abstract">Contents</h2>

​	The main contributions of our work are as follows:
1) We put forward a DRL model, based on DDPG, to train overtaking control instructions in a continuous action space. In the proposed scheme, the decision-making and control layers are tightly coupled. Simulation results show superior  performance compared with two other existing algorithms, fuzzy control and deep Q-network (DQN).
2) We propose a reward function design framework for autonomous overtaking, and apply it to the overtaking maneuver.
This framework can be easily extended to other areas of autonomous driving like merging, platooning, formation, just by modifying the parameters and conditions of the reward function.
3) We use low-cost sensors to get easily available measurements, but the proposed scheme still shows high robustness
to harsh environment, which guarantees that the algorithm is easy to implement on hardware and has high reliability.



<img src="../images/DRLovertaking/diagram.png" width="70%"/>

## Our Related Works
[Relative Formation and Obstacle Avoidance with Distributed Multi-agent Reinforcement Learning](/relativeformation/)<br>