---
title: Applications
description: "Background Material on Applications"
weight: 1
---

## Degas2
[Degas2](https://w3.pppl.gov/topdac/degas2.htm) is "A Monte Carlo code for the study of neutral atom and molecular transport in confined plasmas", developed at Princeton University.

### `.web` Files
`.web` files are used to write Degas2. Here is a comprehensive documentation for `.web` files: https://w3.pppl.gov/~krommes/fweb.html#Intro

## XGC
[XGC](https://xgc.pppl.gov/html/index.html) is a gyrokinetic fusion plasma simulation code, developed at Princeton University.
XGC has a robust way of installing on various platforms described in the [XGC Installation Guide](https://xgc.pppl.gov/html/building_xgc.html).
To install using Spack, use the following workflow [here]({{< relref "tutorials/xgc/_index.md" >}}).

### Coupled XGC-Degas2 Simulation using PCMS
[PCMS: Parallel Coupler For Multimodel Simulations](https://github.com/SCOREC/pcms) is a Adios2-based library for coupling simulations. It provides communication and field transfer methods.
PCMS has been demonstrated to couple XGC and Degas2 and it enabled them to use two different meshes. The installation and usage is described in this GitHub Gist: [XGC-Degas2 Coupled Simulation Workflow
](https://gist.github.com/Fuad-HH/ea6d4913adcfb4d857ef2a77aebaaa2c).

## PUMI-Tally
[PUMI-Tally](https://github.com/fuad-hh/pumi-tally) is a accelerated distributed unstructured mesh tally library built on top of [PUMI-PiC](https://doi.org/10.1016/j.jpdc.2021.06.004).
It is designed to work with different Monte Carlo particle transport codes. It is recently demonstrated to work with OpenMC ([draft paper](https://doi.org/10.48550/arXiv.2504.19048)).
To install OpenMC with PUMI-Tally, use this workflow: [Installation and Usage of PUMI-Tally with OpenMC](https://gist.github.com/Fuad-HH/bf16253e70ae0122800f2128b9fd4a8f).

