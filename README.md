# Tutorials for Finite Element Method

This repository is mainly based on [finite-element-analysis](https://github.com/Lejeune-Lab-Graduate-Course-Materials/finite-element-analysis). The tutorials for Assignment 3 part 4 can be found in the folder named as "tutorials".

[![python](https://img.shields.io/badge/python-3.12-blue.svg)](https://www.python.org/)
![os](https://img.shields.io/badge/os-ubuntu%20|%20macos%20|%20windows-blue.svg)
[![license](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/sandialabs/sibl#license)


### Conda environment, install, and testing

Note: this is an extremely minimalist readme, but the code is highly documented and will get built out over the coures of assignment 3.

```bash
conda create --name finite-element-analysis-env python=3.12.9
```

```bash
conda activate finite-element-analysis-env
```

```bash
python --version
```

```bash
pip install --upgrade pip setuptools wheel
```

```bash
pip install -e .
```

```bash
pytest -v --cov=finiteelementanalysis --cov-report term-missing
```

It is recommended to run the tutorials in VSCode. The tutorials are mainly based on [example provided by Prof Lejeune](https://github.com/Lejeune-Lab-Graduate-Course-Materials/finite-element-analysis/blob/main/tutorials/full_code_example_2.py).

## Tutorial 1: Bending of a Beam and comparison with Analytical Result.

This is available in [tutorial1.ipynb](https://github.com/rishabh022298/A3P4/blob/main/tutorials/tutorial1.ipynb). 

A cantilever beam is subjected to a uniformly distributed load. This leads to deflection in the beam which is compared with the analytical result. The analytical and numerical results are compared for the tip deflection which can be calculated as:\

$$w(L) = \frac{qL^4}{8EI}$$

Where,\
$w(L) =$ Tip deflection\
$L =$ Length of the cantilever beam\
$q =$ Uniformly distributed load\
$E =$ Young's modulus\
$I =$ Second moment of inertia

For a domain with dimensions of the order of $10^1$, the analytical and numerical results were within the order of $10^{-3}$.

## Tutorial 2: Large Deformation and h and p Refinement

This is available in [tutorial2.ipynb](https://github.com/rishabh022298/A3P4/blob/main/tutorials/tutorial2.ipynb).

Same problem as tutorial 1 was implemented.

### h-refinement

h-refinement study was done using "D2_nn4_quad" element. Different mesh refinement factors were used to generate meshes of finer quality and it was observed that the result started to converge as the finer mesh was used.

### p-refinement

Same mesh parameters were used across the four different element types. Those were:
1. `D2_nn3_tri`
2. `D2_nn4_quad`
3. `D2_nn6_tri`
4. `D2_nn8_quad`

It was found that as the number of nodes per element increased, the solution started convering to the same values as in theh-refinement study.

## Tutorial 3: Failure to Converge
