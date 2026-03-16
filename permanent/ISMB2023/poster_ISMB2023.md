---

layout: page
title: ISMB/ECCB 2023 - Poster
permalink: /permanent/ISMB2023/poster_ISMB2023.html
---
# Using low-rank tensor formats to enable computations of cancer progression models in large state spaces
**Simon Pfahler**<sup>1</sup>, Peter Georg<sup>1</sup>, Y. Linda Hu<sup>2</sup>, Stefan Vocht<sup>2</sup>, Rudolf Schill<sup>2,3</sup>, Andreas Lösch<sup>2</sup>, Kevin Rupp<sup>2,3</sup>, Stefan Hansch<sup>2</sup>, Maren Klever<sup>4</sup>, Lars Grasedyck<sup>4</sup>, Rainer Spang<sup>2</sup>, Tilo Wettig<sup>1</sup>

<sup>1</sup> Department of Physics, University of Regensburg\
<sup>2</sup> Department of Informatics and Data Science, University of Regensburg\
<sup>3</sup> Department of Biosystems Science and Engineering, ETH Zürich\
<sup>4</sup> Institute for Geometry and Applied Mathematics, RWTH Aachen University

Correspondence: [simon.pfahler@ur.de](mailto:simon.pfahler@ur.de)

## Poster
<iframe src="poster_ISMB2023.pdf" width="100%" height="600px" style="border:none;">
    Your browser does not support iframes. [Download instead](poster_ISMB2023.pdf").
</iframe>

## Code availability
**pRC**: C++ library for efficient calculations in the Tensor Train format, [open source](https://gitlab.com/pjgeorg/pRC)
    
**cMHN**: C++ library to work with Mutual Hazard Networks in the Tensor Train format, [open source](https://phygit.ur.de/physics/mhn/cmhn)

## Funding
This work is supported by the German Research Foundation (DFG) through the project "Tensorapproximationsmethoden zur Modellierung von Tumorprogression".

## Simulation results
The data used to plot the KL-divergences and runtimes can be accessed here: <br>
Runtime plot:
- [non-TT](Scaling_nonTT.txt)
- [TT - RP=16, RQ=8](Scaling_TT_RP16_RQ8.txt)
- [TT - RP=32, RQ=8](Scaling_TT_RP32_RQ8.txt)
- [TT - RP=32, RQ=16](Scaling_TT_RP32_RQ16.txt)

Accuracy plot:
- [TT - RP=16, RQ=8](Accuracy_RP16_RQ8.txt)
- [TT - RP=32, RQ=8](Accuracy_RP32_RQ8.txt)
- [TT - RP=32, RQ=16](Accuracy_RP32_RQ16.txt)
