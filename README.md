[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Docs](https://assets.readthedocs.org/static/projects/badges/passing-flat.svg)](https://leojklarner.github.io/gauche/)
[![CodeFactor](https://www.codefactor.io/repository/github/leojklarner/gauche/badge)](https://www.codefactor.io/repository/github/leojklarner/gauche)
<a href="https://github.com/psf/black"><img alt="Code style: black" src="https://img.shields.io/badge/code%20style-black-000000.svg"></a>
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/leojklarner/gauche/HEAD)

<!--[![DOI:10.48550/arXiv.2212.04450](https://zenodo.org/badge/DOI/10.48550/arXiv.2212.04450.svg)](https://doi.org/10.48550/arXiv.2212.04450)
[comment]: #[![fair-software.eu](https://img.shields.io/badge/fair--software.eu-%E2%97%8F%20%20%E2%97%8F%20%20%E2%97%8B%20%20%E2%97%8B%20%20%E2%97%8B-orange)](https://fair-software.eu)-->


<p align="left">
  <a href="https://arxiv.org/abs/2212.04450">
    <img src="imgs/gauche_banner_1.png"/>
  </a>
</p>

**GAUCHE** is a collaborative, open-source software library that aims to make state-of-the-art
probabilistic modelling and black-box optimisation techniques more easily accessible to scientific
experts in chemistry, materials science and beyond. We provide 30+ bespoke kernels for molecules, chemical reactions and proteins and illustrate how they can be used for Gaussian processes and Bayesian optimisation in 10+ easy-to-adapt tutorial notebooks. 

[Overview](#overview) | [Getting Started](#getting-started) | [Documentation](https://leojklarner.github.io/gauche/) | [Paper (NeurIPS 2023)](https://arxiv.org/abs/2212.04450)


## What's New?

* GAUCHE has been accepted to the [NeurIPS 2023 Main Track](https://neurips.cc/virtual/2023/poster/70081)! More details forthcoming!
* Check out our new [Molecular Preference Learning](https://github.com/leojklarner/gauche/blob/main/notebooks/Molecular%20Preference%20Learning.ipynb) and [Preferential Bayesian Optimisation](https://github.com/leojklarner/gauche/blob/main/notebooks/Preferential%20Bayesian%20Optimisation.ipynb) notebooks that show how you can use GAUCHE to learn the latent utility function of a human medicinal chemist from pairwise preference feedback!
* Check out our new [Sparse GP Regression for Big Molecular Data](https://github.com/leojklarner/gauche/blob/main/notebooks/Sparse%20GP%20Regression%20for%20Big%20Molecular%20Data.ipynb) notebook that shows how you can scale molecular GPs to thousands of data points with sparse inducing point kernels!

## Overview

General-purpose Gaussian process (GP) and Bayesian optimisation (BO) libraries do not cater for molecular representations. Likewise, general-purpose molecular machine learning libraries do not consider GPs and BO. To bridge this gap, GAUCHE provides a modular, robust and easy-to-use framework of 30+ parallelisable and batch-GP-compatible implementations of string, fingerprint and graph kernels that operate on a range of widely-used molecular representations.

<p align="left">
  <a href="https://leojklarner.github.io/gauche/">
    <img src="imgs/gauche_overview.png" width="100%" />
  </a>
</p>

### Kernels

Standard GP packages typically assume continuous input spaces of low and fixed dimensionality. This makes it difficult to apply them to common molecular representations: molecular graphs are discrete objects, SMILES strings vary in length and topological fingerprints tend to be high-dimensional and sparse. To bridge this gap, GAUCHE provides:

* **Fingerprint Kernels** that measure the similarity between bit/count vectors of descriptor by examining the degree to which their elements overlap.
* **String Kernels** that measure the similarity between strings by examining the degree to which their sub-strings overlap.
* **Graph Kernels** that measure between graphs by examining the degree to which certain substructural motifs overlap.

### Representations

GAUCHE supports any representation that is based on bit/count vectors, strings or graphs. For rapid prototyping and benchmarking, we also provide a range of standard featurisation techniques for molecules, chemical reactions and proteins:
 
<table>
<thead>
  <tr>
    <th>Domain</th>
    <th>Representation</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td rowspan="1">Molecules</td>
    <td>ECFP Fingerprints [1], rdkit Fragments, Fragprints, Molecular Graphs [2], SMILES [3], SELFIES [4] </td>
  </tr>
  <tr>
    <td rowspan="1">Chemical Reactions</td>
    <td>One-Hot Encoding, Data-Driven Reaction Fingerprints [5], Differential Reaction Fingerprints [6], Reaction SMARTS</td>
  </tr>
  <tr>
    <td rowspan="21">Proteins</td>
    <td>Sequences, Graphs [7]</td>
  </tr>
</tbody>
</table>

### Extensions

If there are any specific kernels or representations that you would like to see included in GAUCHE, please reach out or submit an issue/pull request.

## Getting Started

The easiest way to get started with GAUCHE is to check out our tutorial notebooks:

|   |   |
|---|---|
| [GP Regression on Molecules](https://leojklarner.github.io/gauche/notebooks/gp_regression_on_molecules.html)  |  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/leojklarner/gauche/blob/main/notebooks/GP%20Regression%20on%20Molecules.ipynb)   |
| [Bayesian Optimisation Over Molecules](https://leojklarner.github.io/gauche/notebooks/bayesian_optimisation_over_molecules.html)  |  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/leojklarner/gauche/blob/main/notebooks/Bayesian%20Optimisation%20Over%20Molecules.ipynb)   |
| [Multioutput Gaussian Processes for Multitask Learning](https://leojklarner.github.io/gauche/notebooks/multitask_gp_regression_on_molecules.html)  |  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/leojklarner/gauche/blob/main/notebooks/Multitask%20GP%20Regression%20on%20Molecules.ipynb)   |
| [Using GraKel Graph kernels](https://leojklarner.github.io/gauche/notebooks/external_graph_kernels.html)  |  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/leojklarner/gauche/blob/main/notebooks/external_graph_kernels.ipynb)   |
| [Sparse GP Regression for Big Molecular Data](https://leojklarner.github.io/gauche/notebooks/sparse_gp_regression_for_big_molecular_data.html)  |  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/leojklarner/gauche/blob/main/notebooks/Sparse%20GP%20Regression%20for%20Big%20Molecular%20Data.ipynb)   |
|[Molecular Preference Learning](https://github.com/leojklarner/gauche/blob/main/notebooks/Molecular%20Preference%20Learning.ipynb)|[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/leojklarner/gauche/blob/main/notebooks/Molecular%20Preference%20Learning.ipynb) |
|[Preferential Bayesian Optimisation](https://github.com/leojklarner/gauche/blob/main/notebooks/Preferential%20Bayesian%20Optimisation.ipynb)|[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/leojklarner/gauche/blob/main/notebooks/Preferential%20Bayesian%20Optimisation.ipynb) |

### Installation

We recommend using a conda virtual environment:
```
git clone https://github.com/leojklarner/gauche.git
cd gauche

conda env create -f conda_env.yml

pip install --no-deps rxnfp
pip install --no-deps drfp
pip install transformers
pip install mordred

# optional for running tests
pip install gpflow grakel
```

### Example Usage: GP Regression on Molecules

Fitting a GP model with a kernel from GAUCHE and using it to predict the properties of new molecules is as easy as this. For more detail, check out our [GP Regression on Molecules Tutorial](https://leojklarner.github.io/gauche/notebooks/gp_regression_on_molecules.html) and the corresponding section in the [Docs](https://leojklarner.github.io/gauche/modules/dataloader.html).

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/leojklarner/gauche/blob/main/notebooks/GP%20Regression%20on%20Molecules.ipynb)

```python
import gpytorch
from botorch import fit_gpytorch_model
from gauche.kernels.fingerprint_kernels.tanimoto_kernel import TanimotoKernel

class TanimotoGP(gpytorch.models.ExactGP):
  def __init__(self, train_x, train_y, likelihood):
    super(TanimotoGP, self).__init__(train_x, train_y, likelihood)
    self.mean_module = gpytorch.means.ConstantMean()
    self.covar_module = gpytorch.kernels.ScaleKernel(TanimotoKernel())
  
  def forward(self, x):
    mean_x = self.mean_module(x)
    covar_x = self.covar_module(x)
    return gpytorch.distributions.MultivariateNormal(mean_x, covar_x)

# initialise GP likelihood, model and 
# marginal log likelihood objective
likelihood = gpytorch.likelihoods.GaussianLikelihood()
model = TanimotoGP(X_train, y_train, likelihood)
mll = gpytorch.mlls.ExactMarginalLogLikelihood(likelihood, model)

# fit GP with BoTorch in order to use
# the LBFGS-B optimiser (recommended)
fit_gpytorch_model(mll)

# use the trained GP to get predictions and 
# uncertainty estimates for new molecules
model.eval()
likelihood.eval()
preds = model(X_test)
pred_means, pred_vars = preds.mean, preds.variance
```

### Example Usage: Bayesian Optimisation Over Molecules

|   |   |  
|---|---|
[Tutorial (Bayesian Optimisation Over Molecules)](https://leojklarner.github.io/gauche/notebooks/bayesian_optimisation_over_molecules.html)  | [Docs](https://leojklarner.github.io/gauche/modules/kernels.html)
| [![Open In Colab(https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/leojklarner/gauche/blob/main/notebooks/Bayesian%20Optimisation%20Over%20Molecules.ipynb) | |

```python
from botorch.models.gp_regression import SingleTaskGP
from gprotorch.kernels.fingerprint_kernels.tanimoto_kernel import TanimotoKernel

# We define our custom GP surrogate model using the Tanimoto kernel
class TanimotoGP(SingleTaskGP):

    def __init__(self, train_X, train_Y):
        super().__init__(train_X, train_Y, GaussianLikelihood())
        self.mean_module = ConstantMean()
        self.covar_module = ScaleKernel(base_kernel=TanimotoKernel())
        self.to(train_X)  # make sure we're on the right device/dtype

    def forward(self, x):
        mean_x = self.mean_module(x)
        covar_x = self.covar_module(x)
        return MultivariateNormal(mean_x, covar_x)
```

## Citing GAUCHE

If GAUCHE is useful for your work please consider citing the following paper:

```bibtex
@misc{griffiths2022gauche,
      title={GAUCHE: A Library for Gaussian Processes in Chemistry}, 
      author={Ryan-Rhys Griffiths and Leo Klarner and Henry B. Moss and Aditya Ravuri and Sang Truong and Bojana Rankovic and Yuanqi Du and Arian Jamasb and Julius Schwartz and Austin Tripp and Gregory Kell and Anthony Bourached and Alex Chan and Jacob Moss and Chengzhi Guo and Alpha A. Lee and Philippe Schwaller and Jian Tang},
      year={2022},
      eprint={2212.04450},
      archivePrefix={arXiv},
      primaryClass={physics.chem-ph}
}

```


## References

[1] Rogers, D. and Hahn, M., 2010. [Extended-connectivity fingerprints](https://pubs.acs.org/doi/abs/10.1021/ci100050t). Journal of Chemical Information and Modeling, 50(5), pp.742-754.

[2] Fey, M., & Lenssen, J. E. (2019). [Fast graph representation learning with PyTorch Geometric](https://arxiv.org/abs/1903.02428). arXiv preprint arXiv:1903.02428.

[3] Weininger, D., 1988. [SMILES, a chemical language and information system. 1. Introduction to methodology and encoding rules.](https://pubs.acs.org/doi/pdf/10.1021/ci00057a005) Journal of Chemical Information and Computer Sciences, 28(1), pp.31-36.

[4] Krenn, M., Häse, F., Nigam, A., Friederich, P. and Aspuru-Guzik, A., 2020. [Self-referencing embedded strings (SELFIES): A 100% robust molecular string representation](https://iopscience.iop.org/article/10.1088/2632-2153/aba947/meta). Machine Learning: Science and Technology, 1(4), p.045024.

[5] Probst, D., Schwaller, P. and Reymond, J.L., 2022. [Reaction classification and yield prediction using the differential reaction fingerprint DRFP](https://pubs.rsc.org/en/content/articlehtml/2022/dd/d1dd00006c). Digital Discovery, 1(2), pp.91-97.

[6] Schwaller, P., Probst, D., Vaucher, A.C., Nair, V.H., Kreutter, D., Laino, T. and Reymond, J.L., 2021. [Mapping the space of chemical reactions using attention-based neural networks](https://www.nature.com/articles/s42256-020-00284-w). Nature Machine Intelligence, 3(2), pp.144-152.

[7] Jamasb, A., Viñas Torné, R., Ma, E., Du, Y., Harris, C., Huang, K., Hall, D., Lió, P. and Blundell, T., 2022. [Graphein-a Python library for geometric deep learning and network analysis on biomolecular structures and interaction networks](https://proceedings.neurips.cc/paper_files/paper/2022/hash/ade039c1db0391106a3375bd2feb310a-Abstract-Conference.html). Advances in Neural Information Processing Systems, 35, pp.27153-27167.