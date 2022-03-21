+++

date = "2022-03-19T15:30:00+09:01"
draft = false
title = "CRILS: A Cooperative Relative Infrastructure-free Localization Scheme for Multi-agent Systems" 
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

​     Current and future multi-agent applications strongly rely on precise localization awareness. However, in large-scale networks without absolute position reference, the information transmitted by agents is of limited use, which makes it difficult to achieve high-precision and large-capacity localization. In this paper, we propose a cooperative relative infrastructure-free localization scheme (CRILS) for multi-agent systems in   GNSS-denied environments. Different from traditional triangulation localization methods that need position-known base stations to give absolute coordinates, we introduce a backbone-listener scheme that adaptively select backbone nodes to bring more information to the system, meanwhile, a large amount of listener agents can complete distributed localization. The localization capacity and accuracy are guaranteed in harsh environments due to limited bandwidth or sparse links. The ultra-wideband (UWB) technology is used to obtain high-accuracy range and angle measurements, which are fused  with inertial navigation information in dynamic scenarios by a dead reckoning filtering. We implement the system on a low-cost hardware platform. The relative localization performance has been verified to achieve decimeter-level accuracy, which is close to the theoretical  Cramer–Rao lower bound (CRLB) limit.


<h2 id="Contents">Contents</h2>

<b><a href="#Architecture">Architecture</a></b><br>
<!-- <a href="#1.1">1.1 The CRILS architecture</a><br>-->

<b><a href="#Simulation Results">Simulation Results</a></b><br>
<!-- <a href="#2.1">2.1 Node activation strategies</a><br>
<a href="#2.2">2.2 Relative localization error of backbone agents</a><br>
<a href="#2.3">2.3 Relative localization error of listener agents</a><br>
<a href="#2.4">2.4 Simulation platform</a><br>-->

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
<th style="text-align: center">The CRILS architecture</th>
<th style="text-align: center">The Backbone-Listener  architecture</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CRILS/CRILS.png" width="85%"/></td>
<td style="text-align: center"><img src="../images/CRILS/system_model.png" width="85%"/></td>
</tr>
</tbody></table>



<h2 id="Simulation Results"> Simulation Results</h2>

<p><span id="2.1" name="Node activation strategies"></span></p>
<p><em> Node Activation Strategies</em></p>
<table><thead>
<tr>
<th style="text-align: center">The geometric  interpretation  of node activation</th>
<th style="text-align: center">SPEB comparison for different node activation strategies</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CRILS/node_act.png" width="80%"/></td>
<td style="text-align: center"><img src="../images/CRILS/nodeact_results.png" width="80%"/></td>
</tr>
</tbody></table>

<p><span id="2.2" name="Relative localization error of backbone agents"></span></p>
<p><em> Relative localization error of backbone agents</em></p>
<table><thead>
<tr>
<th style="text-align: center">The proposed BRL algorithm outperforms other benchmarks under two conditions  </th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CRILS/BRL_results.png" width="50%"/></td>
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
<td style="text-align: center"><img src="../images/CRILS/tdoa.png" width="80%"/></td>
<td style="text-align: center"><img src="../images/CRILS/tdoaaoa.png" width="80%"/></td>
<td style="text-align: center"><img src="../images/CRILS/pro_algo.png" width="80%"/></td>
</tr>
</tbody></table>

<table><thead>
<tr>
<th style="text-align: center">CDF of localization error of listener agents</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CRILS/cdf.png" width="40%"/></td>
</tr>
</tbody></table>

<p><span id="2.4" name="Simulation platform"></span></p>
<p><em>The simulation platform is able to visually diplay the  real-time localization results and RMSE</em></p>
<table><thead>
<tr>
<th style="text-align: center">Display of the simulated data </th>
<th style="text-align: center">Display of the external input data </th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CRILS/Simu_platform1.gif" width="100%"/></td>
<td style="text-align: center"><img src="../images/CRILS/Simu_platform2.gif" width="93%"/></td>
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
<td style="text-align: center"><img src="../images/CRILS/array.png" width="100%"/></td>
<td style="text-align: center"><img src="../images/CRILS/car.png" width="100%"/></td>
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
<td style="text-align: center"><img src="../images/CRILS/Static-ideal-1.png" width="85%"/></td>
<td style="text-align: center"><img src="../images/CRILS/Static-real-1.png" width="85%"/></td>
<td style="text-align: center"><img src="../images/CRILS/Static-data-1.png" width="85%"/></td>
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
<td style="text-align: center"><img src="../images/CRILS/Static-ideal-2.png" width="85%"/></td>
<td style="text-align: center"><img src="../images/CRILS/Static-real-2.png" width="85%"/></td>
<td style="text-align: center"><img src="../images/CRILS/Static-data-2.png" width="85%"/></td>
</tr>
</tbody></table>


<h2 id="Hardware Implementation in Dynamic Scenes"> Hardware Implementation in Dynamic Scenes</h2>
<p><span id="4.1" name="Translation and rotation in relative localization"></span></p>
<p><em> Translation and rotation in relative localization</em></p>
<table><thead>
<tr>
<th style="text-align: center"> Translation and rotation do not affect topology estimation in relative localizaiton scenarios </th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CRILS/relative.gif" width="75%"/></td>
</tr>
</tbody></table>


<p><span id="4.2" name="Real-world experiment on our practical hardware platform"></span></p>
<p><em> Real-world experiment on our practical hardware platform</em></p>
<table><thead>
<tr>
<th style="text-align: center"> Extensive  real-world  experiments validate our system   achieves decimeter-level relative localization accuracy </th>

</tr></thead><tbody>
<tr>
<td style="text-align: center"><img src="../images/CRILS/dynamic.gif" width="70%"/></td>
</tr>
</tbody></table>

## Our Related Works

[Relative Formation and Obstacle Avoidance with Distributed Multi-agent Reinforcement Learning](/relativeformation/)<br>

