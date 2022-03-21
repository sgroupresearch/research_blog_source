+++
date = 2021-03-05T11:35:23+08:00
title = "AdaSpeech 2: Adaptive Text to Speech with Untranscribed Data"
tags = ["Speech"]
categories = ["Speech synthesis"]

+++

ArXiv: [arXiv:2104.09715](https://arxiv.org/pdf/2104.09715.pdf)

<small>Accepted by ICASSP 2021</small>

## Author

- Yuzi Yan (EE, Tsinghua University) <yan-yz17@mails.tsinghua.edu.cn>
- Xu Tan (Microsoft Research Asia) <xuta@microsoft.com>
- Bohan Li (Microsoft Azure Speech) <bohan.li@microsoft.com>
- Tao Qin (Microsoft Research Asia) <taoqin@microsoft.com>
- Sheng Zhao (Microsoft Azure Speech) <szhao@microsoft.com>
- Yuan Shen (EE, Tsinghua University) <shenyuan_ee@tsinghua.edu.cn>
- Tie-Yan Liu (Microsoft Research Asia) <tie-yan.liu@microsoft.com>



## Audio Samples

All of the audio samples use MelGAN as vocoder.

### Audio Quality 

*When a man looks for something beyond his reach, his friends say he is looking for the pot of gold at the end of the rainbow.*

#### VCTK Female

<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">GT Mel+Vocoder</th>
<th style="text-align: center">Joint-training</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/recording/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/gt/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/nautilus/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

<table><thead>
<tr>
<th style="text-align: center">PPG-based</th>
<th style="text-align: center">AdaSpeech</th>
<th style="text-align: center">Ours(AdaSpeech 2)</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/ppgs/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/fs2/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/untrans/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

#### VCTK Male

<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">GT Mel+Vocoder</th>
<th style="text-align: center">Joint-training</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/recording/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/gt/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/nautilus/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

<table><thead>
<tr>
<th style="text-align: center">PPG-based</th>
<th style="text-align: center">AdaSpeech</th>
<th style="text-align: center">Ours(AdaSpeech 2)</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/ppgs/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/fs2/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/untrans/GeneralSentence/00002.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

*Some have accepted it as a miracle without physical explanation.*


#### VCTK Female

<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">GT Mel+Vocoder</th>
<th style="text-align: center">Joint-training</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/recording/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/gt/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/nautilus/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

<table><thead>
<tr>
<th style="text-align: center">PPG-based</th>
<th style="text-align: center">AdaSpeech</th>
<th style="text-align: center">Ours(AdaSpeech 2)</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/ppgs/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/fs2/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/228F/untrans/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

#### VCTK Male

<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">GT Mel+Vocoder</th>
<th style="text-align: center">Joint-training</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/recording/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/gt/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/nautilus/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

<table><thead>
<tr>
<th style="text-align: center">PPG-based</th>
<th style="text-align: center">AdaSpeech</th>
<th style="text-align: center">Ours(AdaSpeech 2)</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/ppgs/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/fs2/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/245M/untrans/GeneralSentence/00004.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

*the invention of movable metal letters in the middle of the fifteenth century may justly be considered as the invention of the art of printing.*

#### LJSpeech
<table><thead>
<tr>
<th style="text-align: center">GT</th>
<th style="text-align: center">GT Mel+Vocoder</th>
<th style="text-align: center">Joint-training</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/Lj/0000000005.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/Lj/gt.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/Lj/nautilus.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

<table><thead>
<tr>
<th style="text-align: center">PPG-based</th>
<th style="text-align: center">AdaSpeech</th>
<th style="text-align: center">Ours(AdaSpeech 2)</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/Lj/ppgs.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/Lj/trans.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/Lj/untrans.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>



### Analyses on adaptation strategy

*When a man looks for something beyond his reach, his friends say he is looking for the pot of gold at the end of the rainbow.*

<table><thead>
<tr>
<th style="text-align: center">Origin</th>
<th style="text-align: center">Without L2 loss constraint</th>
<th style="text-align: center">Fine-tune mel encoder & decoder</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/Analyses/Origin.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/Analyses/withoutL2.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/Analyses/Both.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

### Varying Adaptation Data

*Please call stella.*

<table><thead>
<tr>
<th style="text-align: center">1 samples</th>
<th style="text-align: center">2 samples</th>
<th style="text-align: center">5 samples</th>
<th style="text-align: center">10 samples</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/vary/1.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/vary/2.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/vary/5.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/vary/10.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

<table><thead>
<tr>
<th style="text-align: center">20 samples</th>
<th style="text-align: center">50 samples</th>
<th style="text-align: center">100 samples</th>
</tr></thead><tbody>
<tr>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/vary/20.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/vary/50.wav" autoplay/>Your browser does not support the audio element.</audio></td>
<td style="text-align: center"><audio controls="controls" ><source src="../audio/adaspeech2/vary/100.wav" autoplay/>Your browser does not support the audio element.</audio></td>
</tr>
</tbody></table>

## Our Related Works
[FastSpeech: Fast, Robust and Controllable Text to Speech](/fastspeech/)<br>




