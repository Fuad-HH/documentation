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

### OpenMC Geometry Concepts
OpenMC uses geometry in two distinct ways:

1. **Transport Geometry** — defines the physical domain for particle transport, including material assignments and boundary conditions. This can be specified in either **CSG** (Constructive Solid Geometry) or **DAGMC** format.
2. **Mesh Tally Filter** — a volume mesh used as a filter for tallying quantities over spatial regions. Unlike transport geometry, the tally mesh filter does not require material information.

These two are fundamentally different: the DAGMC transport geometry (`.h5m`) is a **surface mesh**, whereas the tally mesh filter is a **volume mesh** (confusingly has the same file extension `.h5m`). For more details, see the [OpenMC documentation on CAD-based geometries](https://docs.openmc.org/en/stable/usersguide/geometry.html#using-cad-based-geometry).

### Preparing CAD Geometry for DAGMC Neutron Transport
[DAGMC](https://svalinn.github.io/DAGMC/) (Direct Accelerated Geometry Monte Carlo) enables the use of CAD-based geometry in Monte Carlo particle transport codes such as OpenMC.
To use DAGMC geometry with OpenMC, a CAD model must first be converted to the DAGMC format (`.h5m`) using [Coreform Cubit](https://coreform.com/products/coreform-cubit/).
The following resources provide step-by-step guidance on preparing and exporting DAGMC geometry:

- [Coreform Cubit DAGMC Tutorial](https://coreform.com/coreform-cubit-tutorials/tutorial_1/) — Official Coreform tutorial on model preparation for DAGMC.
- [DAGMC Model Preparation and Export Tutorial (Forum)](https://forum.coreform.com/t/coreform-dagmc-model-preparation-and-export-tutorial/2073) — Community tutorial on the Coreform forum covering the full DAGMC export workflow.
- [Video: DAGMC Geometry Preparation with Coreform Cubit](https://youtu.be/mSXP1o3VXps) — Video walkthrough of the geometry preparation process.
- [Video: CAD to DAGMC Workflow](https://youtu.be/2TzgTQidfwk) — Video tutorial on the complete CAD-to-DAGMC conversion pipeline.

### Preparing DAGMC Geometry for OpenMC Tally Mesh Filter
Volume meshes from many types (for example, GMSH, EXODUS, VTK, etc.) can be converted to DAGMC format (`.h5m`) using `mbconvert` which is part of DAGMC.

