# $\texttt{graphLa+}\Psi$

This is the Official GitHub repository for the paper *A data-dependent regularization method based on the graph Laplacian* by D. Bianchi, D. Evangelista, S. Aleotti, M. Donatelli, E. Loli Piccolomini and W. Li.

## Introduction
In this work we aim to solve CT-related problems in the form

$$
    y^\delta = Kx_{gt} + \eta, \quad || \eta || \leq \delta
$$

by considering the minimization problem

$$
    \min_{x \in \mathbb{R}^n} \frac{1}{2} || Kx - y^\delta ||_2^2 + \alpha|| Lx ||_1.
$$

In particular, we consider $L$ to be the Graph Laplacian operator defined by a coarse approximation $\tilde{x}$ of $x_{gt}$. The approximation $\tilde{x}$ is constructed by a reconstruction algorithm $\Psi_{\Theta}(y^\delta)$ and the resulting operator is 

$$
    L = \Delta_{\Psi^\delta_{\Theta}}.
$$

We consider different choices of $\Psi_{\Theta}$, for example:

- $\Psi_{\Theta}$ = Filtered Back-Projection (FBP);
- $\Psi_{\Theta}$ = Tikhonov-Regularized solution;
- $\Psi_{\Theta}$ = TV-Regularized solution;
- $\Psi_{\Theta}$ = Neural Network;

For each of the choices above, we compute the associated Graph Laplacian solution given by the minimization problem above. Extensive numerical results show the effectiveness of the proposed method.

## Installation and requirements
To install the software to replicate the experiments, simply clone the repository by running

```
git clone https://github.com/devangelista2/GraphLaPlus.git
```

The code to replicate the experiments is almost self-contained in the repository and only few requirements are needed. In particular, we ran our experiments on Matlab version R2023a, with the Image Processing Toolbox and DeepLearning Toolbox installed. Besides them, the IRTools package from S.Gazzola, P.C.Hansen and J.Nagy is required. To install it, just follow the instruction on the official repository at the following link: https://github.com/jnagy1/IRtools. 

## Data and pretrained models
To replicate our results, it is also required to download the data and the pretrained weights for the models. Due to their dimension, it was not possible to upload them directly on GitHub. For this reason, we made them available to download from Google Drive at the following link:

- COULE:
  - data > https://drive.google.com/drive/folders/1UlXc2llAoaRX-tPchlT5ukRc4SaQX7Lv?usp=sharing
  - weights > https://drive.google.com/drive/folders/1b-UWR_DzTs0d3vdAVyy2_IlOjHYC7pLt?usp=sharing

- Mayo:
    - data > https://drive.google.com/drive/folders/1mlT-87fK_aPSkgSvh8KYZPYhJiUoscWr?usp=sharing
    - weights > https://drive.google.com/drive/folders/1ySJICWKFIEqsR_g3BdQWFnc-80UhXxfG?usp=sharing

To make them work, just download the files and place them into a folder tree with the following structure:

```
|- data/
   |- COULE_train/
      |- ...
   |- COULE_test/
      |- ...
   |- Mayo_train/
      |- ...
   |- Mayo_test/
      |- ...
|- model_weights
   |- COULE
      |- ...
   |- Mayo
      |- ...
|- OTHER FILES
```

## Cite the work
```
@misc{bianchi2023datadependent,
      title={A data-dependent regularization method based on the graph Laplacian}, 
      author={Davide Bianchi and Davide Evangelista and Stefano Aleotti and Marco Donatelli and Elena Loli Piccolomini and Wenbin Li},
      year={2023},
      eprint={2312.16936},
      archivePrefix={arXiv},
      primaryClass={math.NA}
}
```
