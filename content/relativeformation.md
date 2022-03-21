+++
date = "2021-08-19T15:30:00+09:01"
draft = false
title = "Distributed Relative Formation and Obstacle Avoidance with Multi-agent Reinforcement Learning"
tags  = ["MA-DRL"]
categories = ["DRL"]

+++


<!-- ArXiv: [arXiv:xxxx.xxxxx](https://arxiv.org/pdf/xxxx.xxxx.pdf) -->


## Authors

- Yuzi Yan (EE, Tsinghua University) <yan-yz17@tsinghua.org.cn>
- Xiaoxiang Li (EE, Tsinghua University) <lxx17@mails.tsinghua.edu.cn>
- Xinyou Qiu (EE, Tsinghua University) <qxy18@mails.tsinghua.edu.cn>
- Jiantao Qiu (EE, Tsinghua University) <qjt15@mails.tsinghua.edu.cn>
- Jian Wang (EE, Tsinghua University) <jian-wang@tsinghua.edu.cn>
- Yu Wang (EE, Tsinghua University) <yu-wang@tsinghua.edu.cn>
- Yuan Shen (EE, Tsinghua University) <shenyuan_ee@tsinghua.edu.cn>


## Abstract

Multi-agent formation as well as obstacle avoidance is one of the most actively studied topics in the field of multi-agent systems. Although some classic controllers like model predictive control (MPC) and fuzzy control achieve a certain measure of success, most of them require precise global information which is not accessible in harsh environments. On the other hand, some reinforcement learning (RL) based 
approaches adopt the leader-follower structure to organize different agents' behaviors, which sacrifices the collaboration between agents thus suffering from bottlenecks in maneuverability and robustness. 

In this paper, we propose a distributed formation and obstacle avoidance method based on multi-agent reinforcement learning (MARL). Agents in our system only utilize local and relative information to make decisions and control themselves distributively. Agents in the multi-agent system will reorganize 
themselves into a new topology quickly in case that any of them is disconnected. Our method achieves better performance regarding formation error, formation convergence rate and on-par success rate of obstacle avoidance compared with baselines (both classic control methods and another RL-based method). The feasibility of our method is verified by both  simulation and hardware implementation with Ackermann-steering vehicles


<h2 id="abstract">Contents</h2>
<b><a href="#render-results">Rendering</a></b><br>
<!-- <a href="#1.1">1.1 3 agents (triangle)</a><br>
<a href="#1.2">1.2 4 agents (square)</a><br>
<a href="#1.3">1.3 Formation Adapation </a><br> -->
<b><a href="#hardware">Hardware Implementation</a></b><br>
<!-- <a href="#2.1">2.1 MultiVehicleEnv </a><br>
<a href="#2.2">2.2 Hardware Platform </a><br> -->
<b><a href="#method">Method</a></b><br>
<!-- <a href="#3.1">3.1 Model Structure</a><br>
<a href="#3.2">3.2 Policy Distillation</a><br>
<a href="#3.3">3.3 Curriculum Learning</a><br> -->
<b><a href="#results">Results</a></b><br>
<!-- <a href="#4.1">4.1 Training Process </a><br>
<a href="#4.2">4.2 Formation Adaptation </a><br>
<a href="#4.3">4.3 Advantage of Curriculum Learning</a><br> -->



<h2 id="render-results">Rendering</h2>

<p><span id="1.1" name="3 agents"></span></p>
<p><em>3 agents  (triangle)</em></p>
<table><thead>
<tr>
<th style="text-align: center">3 agents in level-0 obstacle scenario</th>
<th style="text-align: center">3 agents in level-1 obstacle scenario</th>
<th style="text-align: center">3 agents in level-2 obstacle scenario</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/relativeformation/3agents-0obs-f.gif" width="80%"/></td>
<td style="text-align: center"><img src="../images/relativeformation/3agents-1obs-f.gif" width="80%"/></td>
<td style="text-align: center"><img src="../images/relativeformation/3agents-3obs-f.gif" width="80%"/></td>
</tr>
</tbody></table>

<p><span id="1.2" name="4 agents"></span></p>
<p><em>4 agents (square)</em></p>
<table><thead>
<tr>
<th style="text-align: center">4 agents in level-0 obstacle scenario</th>
<th style="text-align: center">4 agents in level-1 obstacle scenario</th>
<th style="text-align: center">4 agents in level-2 obstacle scenario</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/relativeformation/4agents-0obs-f.gif" width="80%"/></td>
<td style="text-align: center"><img src="../images/relativeformation/4agents-1obs-f.gif" width="80%"/></td>
<td style="text-align: center"><img src="../images/relativeformation/4agents-3obs-f.gif" width="80%"/></td>
</tr>
</tbody></table>


<p><span id="1.3" name="Formation Adaptation"></span></p>
<p><em>Formation Adaptation</em></p>
<table><thead>
<tr>
<th style="text-align: center">formation adaptation when agents die</th>
<th style="text-align: center">MVE relative triangle formation</th>
<th style="text-align: center">MVE relative triangle formation</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/relativeformation/formation_change.gif" width="80%"/></td>
<td style="text-align: center"><img src="../images/relativeformation/MVE_2.gif" width="80%"/></td>
<td style="text-align: center"><img src="../images/relativeformation/MVE_1.gif" width="80%"/></td>
</tr>
</tbody></table>

<h2 id="hardware">Hardware Implementation</h2>

<p><span id="2.1" name="3 agents formation"></span></p>
<p><em>Formation with Random Initialization</em></p>
<table><thead>
<tr>
<th style="text-align: center">Hardware</th>
<!-- <th style="text-align: center">Simulation on MVE</th> -->
<th style="text-align: center">OptiTrack</th>

</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/relativeformation/3agent_form_hard.gif" width="55%"/></td>
<!-- <td style="text-align: center"><img src="../images/relativeformation/3agent_form_mve.gif" width="80%"/></td> -->
<td style="text-align: center"><img src="../images/relativeformation/3agent_form_opi.gif" width="100%"/></td>
</tr>
</tbody></table>



<p><span id="2.2" name="Formation & Avoiding Obstacle"></span></p>
<p><em>Avoiding Obstacles</em></p>
<table><thead>
<tr>
<th style="text-align: center">Hardware</th>
<!-- <th style="text-align: center">Simulation on MVE</th> -->
<th style="text-align: center">OptiTrack</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/relativeformation/3agent_avoid_hard.gif" width="80%"/></td>
<!-- <td style="text-align: center"><img src="../images/relativeformation/MVE_2.gif" width="80%"/></td> -->
<td style="text-align: center"><img src="../images/relativeformation/3agent_avoid_opi.gif" width="70%"/></td>
</tr>
</tbody></table>


<h2 id="method">Method</h2>

<p><span id="3.1" name="Method"></span></p>

<table><thead>
<tr>
<th style="text-align: center">Model Structure</th>
<th style="text-align: center">Policy Distillation for Formation Adaptation</th>
<th style="text-align: center">Schematic Diagram of the MVE environment</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/relativeformation/network.png" width="80%"/></td>
<td style="text-align: center"><img src="../images/relativeformation/policy_distillation.png" width="80%"/></td>
<td style="text-align: center"><img src="../images/relativeformation/MVE_diag.png" width="70%"/></td>
</tr>
</tbody></table>

<h2 id="results">Results</h2>

<table><thead>
<tr>
<th style="text-align: center">Training</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/relativeformation/figure_training.png" width="100%"/></td>
</tr>
</tbody></table>


<table><thead>
<tr>
<th style="text-align: center">Formation Adapatation</th>
<th style="text-align: center">Curriculum Learning</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/relativeformation/figure_form_change.png" width="70%"/></td>
<td style="text-align: center"><img src="../images/relativeformation/figure_curriculum.png" width="70%"/></td>
</tr>
</tbody></table>

<table><thead>
<tr>
<th style="text-align: center">Benchmark</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/relativeformation/figure_benchmark.png" width="70%"/></td>
</tr>
</tbody></table>



## Our Related Works
[A Deep Reinforcement Learning Based Approach for Autonomous Overtaking](/drlovertaking/)<br>