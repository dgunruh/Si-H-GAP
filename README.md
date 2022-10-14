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

### LAMMPS and ASE usage

First, unpack the sparseX files GAP_Si_H_PRM.xml.sparseX.\*. These files are all compressed in the bzip2 file format. On unix/linux, unpack the files by running the command:
```code
bzip2 -d GAP_Si_H_PRM.xml.sparseX.*
```

To load this potential in LAMMPS, first ensuring that you have built LAMMPS with [QUIP](https://github.com/libAtoms/QUIP), include the following commands in your LAMMPS input file:

```code
pair_style  quip
pair_coeff  * * ../potential/GAP_Si_H_PRM.xml "Potential xml_label=GAP_2021_5_28_-420_7_13_1_584" 1 14
```
To load this potential in ASE, it is required that you add the [quippy](https://github.com/libAtoms/QUIP) program to your python environment. Once you have done so, you can load the potential with:
```code
from quippy.potential import Potential
calculator = Potential('IP GAP', param_filename="GAP_Si_H_PRM.xml")
