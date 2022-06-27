# Si-H-GAP
Gaussian Approximation Potential for Si-H interactions. 

### Citation

If using this potential, please cite the following paper:

https://journals.aps.org/prmaterials/abstract/10.1103/PhysRevMaterials.6.065603

### Structural Data

This repository contains all of the structural data that was used to train the potential, as well as to validate it. All of this structural data can be found in the file structural_data.zip.

### Alternate Parameterization

Two different versions of the potential are contained in this repository, each of which was trained on the same data but using slightly different parameterizations for the regularization parameters. The parameterization used in the Physical Review Materials paper is contained in the files GAP/GAP_Si_H_PRM.xml*, while the alternate parameterization is contained in the files GAP/GAP_Si_H_PRM_alternate_parameterization.xml*.

This alternate parameterization doubled the prefactor for the virial sigmas for the amorphous structures, increasing the prefactor from 0.025 to 0.05.


