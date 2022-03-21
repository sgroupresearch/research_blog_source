+++
date = 2021-06-02T11:35:23+08:00
title = "AdaSpeech 3: Adaptive Text to Speech for Spontaneous Style"
tags = ["Speech"]
categories = ["Speech synthesis"]

+++

ArXiv: [arXiv:2107.02530](https://arxiv.org/pdf/2107.02530.pdf)

<small>Accepted by INTERSPEECH 2021</small>

## Author

- Yuzi Yan (EE, Tsinghua University) <yan-yz17@mails.tsinghua.edu.cn>
- Xu Tan (Microsoft Research Asia) <xuta@microsoft.com>
- Bohan Li (Microsoft Azure Speech) <bohan.li@microsoft.com>
- Guangyan Zhang (EE, The Chinese University of Hong Kong) <gyzhang@link.cuhk.edu.hk>
- Tao Qin (Microsoft Research Asia) <taoqin@microsoft.com>
- Sheng Zhao (Microsoft Azure Speech) <sheng.zhao@microsoft.com>
- Yuan Shen (EE, Tsinghua University) <shenyuan_ee@tsinghua.edu.cn>
- Wei-Qiang Zhang (EE, Tsinghua University) <wqzhang@tsinghua.edu.cn>
- Tie-Yan Liu (Microsoft Research Asia) <tie-yan.liu@microsoft.com>

<!-- ## Abstract

Text to speech (TTS) is widely used to synthesize speech. However, it is still a huge challenge to synthesize spontaneous speech like podcast or talk show for two main reasons: 1) lack of training data. Most mainstream datasets for TTS training are reading-style. 2) difficulty in modeling speaking style. Unlike reading-style speech, spontaneous speech has many natural filled pauses (um and uh). Besides, rhythm of it is more variable. In this paper, we propose a new method to address these problems by 1) constructing a spontaneous speech dataset, 2) analyzing the important factors in spontaneous speech like filled pauses (FPs) and rhythm, and 3) developing a spontaneous TTS pipeline through an adaptation way. Specifically, we introduce an FP predictor trained on spontaneous data to a TTS source model trained on reading-style data, which is managed to insert FPs appropriately. To obtain accurate control of the varying duration, we introduce MoE (Mixture of Experts) on duration predictor, which contains three seperate duration predictors that are responsible for the generation of fast, medium and slow speech respectively. We fine-tune it as well as a pitch predictor to achieve fine-grained duration and pitch control using spontaneous data. Besides, our model can also transfer the spontaneity to other speaker through speaker adaptation. Compared with previous TTS model, the proposed method achieves 0.30 better SMOS focusing on style similarity with spontaneous speech, and it achieves better results in MOS tests focusing on many different aspects.  -->

## Audio Samples

All of the audio samples use MelGAN as vocoder.

### Spontaneous Quality

*cecily package in all of that <font color="red">um</font> yeah so ...*

<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">GT Mel+Vocoder</th>
<th style="text-align: center">AdaSpeech</th>
<th style="text-align: center">AdaSpeech 3</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00005_gt.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00005_gt_melgan.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00005_ada.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00005_spon.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

<!-- *ugly surprised it was one of the actually the best color we've you performing cooler we've reviewed so far*


<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">GT Mel+Vocoder</th>
<th style="text-align: center">AdaSpeech</th>
<th style="text-align: center">adaspeech3</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00020_gt.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00020_gt_melgan.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00020_ada.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00020_spon.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table> -->


*lot of stuff with the even CSA had igaming tournament they sponsored teams and their really get into the gaming it's that's coming.*

<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">GT Mel+Vocoder</th>
<th style="text-align: center">AdaSpeech</th>
<th style="text-align: center">AdaSpeech 3</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00006_gt.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00006_gt_melgan.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00006_ada.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Quality_TC/00006_spon.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

### FP Insertion

#### Note: We did not use punctuation marks (, or .) in real practice.

*Input: Six spoons of fresh snow peas, five thick slabs of blue cheese, and maybe a snack for her brother Bob.*

*Output: Six spoons of fresh snow peas, <font color="red">um</font>, five thick slabs of blue cheese, and maybe a snack for her brother Bob.*

<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">Before Insertion</th>
<th style="text-align: center">After Insertion</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_quality/out00007_gt.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_quality/out00007_wo_FP.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_quality/out00007_w_FP.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

*Input: When the sunlight strikes raindrops in the air, they act as a prism and form a rainbow.*

*Output: When the sunlight strikes raindrops in the air, <font color="red">um</font>, they act as a prism and form a rainbow.*

<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">Before Insertion</th>
<th style="text-align: center">After Insertion</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_quality/out00010_gt.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_quality/out00010_wo_FP.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_quality/out00010_w_FP.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

*Input: Some have accepted it as a miracle without physical explanation.*

*Output: Some have accepted it <font color="red">um</font> as a miracle without physical explanation.*

<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">Before Insertion</th>
<th style="text-align: center">After Insertion</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_quality/out00003_gt.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_quality/out00003_wo_FP.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_quality/out00003_w_FP_new.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

### Speaker Adaptation (VCTK)

*cecily package in all of that <font color="red">um</font> yeah so something any jamaican upgrade yeah it like said.*

<table><thead>
<tr>
<th style="text-align: center">Original Sound</th>
<th style="text-align: center">Male Adaptation</th>
<th style="text-align: center">Female Adaptation</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Transfer/00005.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Transfer/out00005_male.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Transfer/out00005_female.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

*lot of stuff with the even CSA had igaming tournament they sponsored teams and their really get into the gaming it's that's coming.*

<table><thead>
<tr>
<th style="text-align: center">Original Sound</th>
<th style="text-align: center">Male Adaptation</th>
<th style="text-align: center">Female Adaptation</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Transfer/00006.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Transfer/out00006_male.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Transfer/out00006_female.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

*amplifier from them was a kinda interesting a jackson he really liked it it's a good way to get bluetooth.*

<table><thead>
<tr>
<th style="text-align: center">Original Sound</th>
<th style="text-align: center">Male Adaptation</th>
<th style="text-align: center">Female Adaptation</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Transfer/00021.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Transfer/out00021_male.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/Transfer/out00021_female.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

### Change the threshold to control the FP indensity

*The rainbow <font color="red">um</font> is a division of white light into many beautiful colors.*

*The rainbow <font color="red">um</font> is a division of white light <font color="green">uh</font>  into many beautiful colors.*

<!-- *The rainbow <font color="red">um</font> is a division of white light <font color="green">uh</font>  into many <font color="green">uh</font> beautiful colors.* -->

<table><thead>
<tr>
<th style="text-align: center">Threshold=0.1</th>
<th style="text-align: center">Threshold=0.5</th>
<!-- <th style="text-align: center">Threshold=0.9</th> -->
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_insert/out00011_1um_new.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_insert/out00011_1um1uh_newest.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<!-- <td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech3/FP_insert/out00011_1um2uh_new.wav" autoplay/>Your browser does not support the audio element.</audio></td> -->
</tr>
</tbody></table>

## Our Related Works
[AdaSpeech 2: Adaptive Text to Speech with Untranscribed Data](/adaspeech2/)<br>







