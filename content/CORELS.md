+++

date = "2022-03-19T15:30:00+09:01"
draft = false
title = "CORELS:  A Cooperative Relative LocalizationSystem for Multi-agent Networks" 
tags  = ["MAS-RelLoc"]
categories = ["MAS"]


+++


## Authors

- Xiaoxiang Li (EE, Tsinghua University) <lxx17@mails.tsinghua.edu.cn>
- Kai Ma (EE, Tsinghua University) <mk19@mails.tsinghua.edu.cn>
- Lingwei Xu (EE, Tsinghua University) <xlw18@mails.tsinghua.edu.cn>
- Jian Wang (EE, Tsinghua University) <jian-wang@tsinghua.edu.cn>
- Yuan Shen (EE, Tsinghua University) <shenyuan_ee@tsinghua.edu.cn>


## Abstract
Reliable and accurate spatio-temporal information is of great importance for multi-agent networks. Cooperative relativelocalization technologies provide a promising paradigm for such information, especially in GNSS-denied or infrastructure-freescenarios without absolute position reference. In this paper, we develop a cooperative relative localization system (CORELS) formulti-agent networks to achieve high-precision and low-latency capability. A backbone-listener architecture is proposed to encalbelarge-scale agents to complete high-precision localization. Backbone agents are selected to reduce information loss caused bytopological deformity, and meanwhile a large amount of listener agents complete position and orientation angle estimationsimultaneously. The localization capacity and accuracy are still maintained in harsh environments with limited bandwidth or sparselinks. Different from traditional triangulation localization methods, CORELS has no prerequisites for position-known base stations. Thelocalization capability is extend to relative dynamic scenarios by a dead reckoning filtering scheme, where spatio-temporal cooperationare accomplished by information fusion of ranging, angle and inertial navigation measurements. Moreover, we implement CORELS ona low-cost hardware platform with the ultra-wideband technology. Extensive simulation and real-world experiments demonstrate thatthe proposed system achieves decimeter-level relative localization, which is close to the theoretical Cramer–Rao lower bound  limit.


<h2 id="Contents">Contents</h2>

<b><a href="#Architecture">Architecture</a></b><br>
<!-- <a href="#1.1">1.1 The CORELS architecture</a><br>-->

<b><a href="#Simulation Results">Simulation Results</a></b><br>
<!-- <a href="#2.1">2.1 Node activation strategies</a><br>
<a href="#2.2">2.2 Relative localization error of backbone agents</a><br>
<a href="#2.3">2.3 Relative localization error of listener agents</a><br>
<a href="#2.4">2.4 Performance gain from GNA in dynamic scence </a><br>
<a href="#2.5">2.5 Simulation platform</a><br>-->

<b><a href="#Hardware Implementation in Static Scenes">Hardware Implementation in Static Scenes</a></b><br>
<!-- <a href="#3.1">3.1  Illustrations of the hardware platform </a><br>
<a href="#3.2">3.2 Rectangular placement  </a><br> 
<a href="#3.3">3.3 Random placement </a><br>-->

<b><a href="#Hardware Implementation in Dynamic Scenes">Hardware Implementation in Dynamic Scenes</a></b><br>
<!-- <a href="#4.1">4.1 Translation and rotation in relative localization </a><br>
<a href="#4.2">4.2 Real-world experiment on our practical hardware platform</a><br> -->


<h2 id="Architecture">Architecture</h2>
<p><span id="1.1" name="Architecture"></span></p>
<table><thead>
<tr>
<th style="text-align: center">The CORELS architecture</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/CORELS.png" width="70%"/></td>
</tr>
</tbody></table>
<table><thead>
<tr>
<th style="text-align: center">The Backbone-Listener architecture</th>
<th style="text-align: center">The dead reckoning filtering scheme</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/system_model.png" width="100%"/></td>
<td style="text-align: center"><img src="../images/CORELS/DRFS.png" width="70%"/></td>
</tr>
</tbody></table>



<h2 id="Simulation Results"> Simulation Results</h2>

<p><span id="2.1" name="Node activation strategies"></span></p>
<p><em> Node Activation Strategies</em></p>
<table><thead>
<tr>
<th style="text-align: center">SPEB comparison for different node activation strategies</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/nodeact_results.png" width="50%"/></td>
</tr>
</tbody></table>

 <p><span id="2.2" name="Relative localization error of backbone agents"></span></p>
<p><em> Relative localization error of backbone agents</em></p>
<table><thead>
<tr>
<th style="text-align: center">The proposed BRL algorithm outperforms other benchmarks under two conditions</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/BRL_results.png" width="60%"/></td>
</tr>
</tbody></table>



<p><span id="2.3" name="Relative localization error of listener agents"></span></p>
<p><em>Relative localization error of listener agents</em></p>
<table><thead>
<tr>
<th style="text-align: center">RMSE  distribution  of  TDoA-based algorithm  </th>
<th style="text-align: center">RMSE  distribution  of  TDoA-AoA-based algorithm</th>
<th style="text-align: center">RMSE  distribution  of  The proposed algorithm</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/tdoa.png" width="80%"/></td>
<td style="text-align: center"><img src="../images/CORELS/tdoaaoa.png" width="80%"/></td>
<td style="text-align: center"><img src="../images/CORELS/pro_algo.png" width="80%"/></td>
</tr>
</tbody></table>

<table><thead>
<tr>
<th style="text-align: center">CDF of relative localization error </th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/cdf.png" width="40%"/></td>
</tr>
</tbody></table>

<p><span id="2.4" name="Performance gain from GNA in dynamic scence"></span></p>
<p><em>Performance gain from GNA in dynamic scence</em></p>
<table><thead>
<tr>
<th style="text-align: center">The GNA strategy changes the anchor configuration when topologically deformed </th>
<th style="text-align: center">The GNA strategy (in blue) significantly reduces error accumulation   </th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/dynamic_test.gif" width="100%"/></td>
<td style="text-align: center"><img src="../images/CORELS/dynamic_error.gif" width="90%"/></td>
</tr>
</tbody></table>

<p><span id="2.5" name="Simulation platform"></span></p>
<p><em>The simulation platform is able to visually diplay the  real-time localization results and RMSE</em></p>
<table><thead>
<tr>
<th style="text-align: center">Display of the simulated data </th>
<th style="text-align: center">Display of the external input data </th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/Simu_platform1.gif" width="100%"/></td>
<td style="text-align: center"><img src="../images/CORELS/Simu_platform2.gif" width="91%"/></td>
</tr>
</tbody></table>

<h2 id="Hardware Implementation in Static Scenes"> Hardware Implementation in Static Scenes</h2>
<p><span id="3.1" name="Illustrations of the hardware platform"></span></p>
<p><em> Illustrations of the hardware platform</em></p>
<table><thead>
<tr>
<th style="text-align: center"> The 4-antenna UWB array </th>
<th style="text-align: center"> The  intelligent  agent  (vehicle)  and  its  architecture diagram</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/array.png" width="130%"/></td>
<td style="text-align: center"><img src="../images/CORELS/car.png" width="75%"/></td>
</tr>
</tbody></table>
<table><thead>
<tr>
<th style="text-align: center"> The  OptiTrack  motion  capture  system </th>
<th style="text-align: center"> Photo of the experiment in an actual scene</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/figure_hardware.png" width="87%"/></td>
<td style="text-align: center"><img src="../images/CORELS/realsense.jpg" width="85%"/></td>
</tr>
</tbody></table>

<p><span id="3.2" name="Rectangular placement"></span></p>
<p><em> Rectangular placement</em></p>
<table><thead>
<tr>
<th style="text-align: center">Ideal topology </th>
<th style="text-align: center">Estimated topology</th>
<th style="text-align: center">Localization results </th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/Static-ideal-1.png" width="85%"/></td>
<td style="text-align: center"><img src="../images/CORELS/Static-real-1.png" width="85%"/></td>
<td style="text-align: center"><img src="../images/CORELS/Static-data-1.png" width="85%"/></td>
</tr>
</tbody></table>


<p><span id="3.3" name="Random placement"></span></p>
<p><em> Random placement</em></p>
<table><thead>
<tr>
<th style="text-align: center">Ideal topology </th>
<th style="text-align: center">Estimated topology</th>
<th style="text-align: center">Localization results </th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/Static-ideal-2.png" width="85%"/></td>
<td style="text-align: center"><img src="../images/CORELS/Static-real-2.png" width="85%"/></td>
<td style="text-align: center"><img src="../images/CORELS/Static-data-2.png" width="85%"/></td>
</tr>
</tbody></table>


<h2 id="Hardware Implementation in Dynamic Scenes"> Hardware Implementation in Dynamic Scenes</h2>
<p><span id="4.1" name="Translation and rotation in relative localization"></span></p>
<p><em> Translation and rotation invariance in relative localization</em></p>
<table><thead>
<tr>
<th style="text-align: center"> Translation and rotation do not affect topology estimation in relative localizaiton scenarios </th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/relative.gif" width="75%"/></td>
</tr>
</tbody></table>


<p><span id="4.2" name="Real-world experiment on our practical hardware platform"></span></p>
<p><em> Real-world experiments on our practical hardware platform</em></p>
<table><thead>
<tr>
<th style="text-align: center"> Extensive  real-world  experiments validate our system   achieves decimeter-level relative localization accuracy </th>

</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CORELS/dynamic.gif" width="70%"/></td>
</tr>
</tbody></table>

## Our Related Works

[Relative Formation and Obstacle Avoidance with Distributed Multi-agent Reinforcement Learning](/relativeformation/)<br>

