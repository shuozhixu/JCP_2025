# Confined layer slips

## Foreword

The purpose of this project is to calculate the confined layer slip (CLS) process in nanolaminated Ag and two types of Ag/Cu nanolaminates containing a void due to irradiation.

Read the following journal articles to learn more about nanolaminates

- Irene J. Beyerlein, Zezhou Li, Nathan A. Mara, [Mechanical properties of metal nanolaminates](https://doi.org/10.1146/annurev-matsci-081320-031236), Annu. Rev. Mater. Sci 52 (2022) 281--304
- Mohammad Nasim, Yuncang Li, Ming Wen, Cuie Wen, [A review of high-strength nanolaminates and evaluation of their properties](https://doi.org/10.1016/j.jmst.2020.03.011), J. Mater. Sci. Tech. 50 (2020) 215--244
- I.J. Beyerlein, J. Wang, [Interface-driven mechanisms in cubic/noncubic nanolaminates at different scales](https://doi.org/10.1557/mrs.2018.319), MRS Bull. 44 (2019) 31--39
- Samikshya Subedi, Irene J. Beyerlein, Richard LeSar, Anthony D. Rollett, [Strength of nanoscale metallic multilayers](https://doi.org/10.1016/j.scriptamat.2017.04.009), Scr. Mater. 145 (2018) 132--136
- Jian Wang, Qing Zhou, Shuai Shao, Amit Misra, [Strength and plasticity of nanolaminated materials](https://doi.org/10.1080/21663831.2016.1225321), Mater. Res. Lett. 5 (2017) 1--19
- A. Misra, J.P. Hirth, R.G. Hoagland, [Length-scale-dependent deformation mechanisms in incoherent metallic multilayered composites](https://doi.org/10.1016/j.actamat.2005.06.025), Acta Mater. 53 (2005) 4817--4824

Read the following journal articles to understand how the CLS process can be calculated:

- Weisen Ji, Wu-Rong Jian, Yanqing Su, Shuozhi Xu, Irene J. Beyerlein, [Role of stacking fault energy in confined layer slip in nanolaminated Cu](http://dx.doi.org/10.1007/s10853-023-08779-8), J. Mater. Sci. (in press)
- Wu-Rong Jian, Shuozhi Xu, Yanqing Su, Irene J. Beyerlein, [Role of layer thickness and dislocation distribution in confined layer slip in nanolaminated Nb](http://dx.doi.org/10.1016/j.ijplas.2022.103239), Int. J. Plast. 152 (2022) 103239
- Wu-Rong Jian, Yanqing Su, Shuozhi Xu, Weisen Ji, Irene J. Beyerlein, [Effect of interface structure on dislocation glide behavior in nanolaminates](http://dx.doi.org/10.1557/s43578-021-00261-y), J. Mater. Res. 36 (2021) 2802--2815

Most papers above are not in the Cu/Ag system. The following are some prior work on Cu/Ag nanolaminates:

- Experiments
	- Min Wang, Irene J. Beyerlein, Jian Zhang, Wei-Zhong Han, [Bi-metal interface-mediated defects distribution in neon ion bombarded Cu/Ag nanocomposites](https://doi.org/10.1016/j.scriptamat.2019.06.016), Scr. Mater. 171 (2019) 1--5
	- Min Wang, Irene J. Beyerlein, Jian Zhang, Wei-Zhong Han, [Defect-interface interactions in irradiated Cu/Ag nanocomposites](https://doi.org/10.1016/j.actamat.2018.09.003), Acta Mater. 160 (2018) 211--223
	- Shijian Zheng, Shuai Shao, Jian Zhang, Yongqiang Wang, Michael J. Demkowicz, Irene J. Beyerlein, Nathan A. Mara, [Adhesion of voids to bimetal interfaces with non-uniform energies](http://dx.doi.org/10.1038/srep15428), Sci. Rep. 5 (2015) 15428
- Modeling
	- Yanxiang Liang, Aibo Luo, Lingwei Yang, Jianfeng Zhao, Luobing Wang, Qiang Wan, [Effect of interface structure and layer thickness on the mechanical properties and deformation behavior of Cu/Ag nanolaminates](https://doi.org/10.1016/j.physb.2023.414933), Phys. B Condens. Matter 661 (2023) 414933
	- X.F. Kong, N. Gao, I.J. Beyerlein, B.N. Yao, S.J. Zheng, X.L. Ma, D. Legut, T.C. Germann, H.J. Zhang, R.F. Zhang, [Interface facilitated transformation of voids directly into stacking fault tetrahedra](https://doi.org/10.1016/j.actamat.2020.02.044), Acta Mater. 188 (2020) 623-634
	- X.F. Kong, I.J. Beyerlein, Z.R. Liu, B.N. Yao, D. Legut, T.C. Germann, R.F. Zhang, [Stronger and more failure-resistant with three-dimensional serrated bimetal interfaces](https://doi.org/10.1016/j.actamat.2018.12.051), Acta Mater. 166 (2019) 231--245
	- A. Kardani, A. Montazeri, [Temperature-based plastic deformation mechanism of Cu/Ag nanocomposites: A molecular dynamics study](https://doi.org/10.1016/j.commatsci.2017.12.041), Comput. Mater. Sci. 144 (2018) 223--231

## LAMMPS

LAMMPS on OSCER does not come with many packages. To build more packages into LAMMPS, please visit [this page](https://docs.lammps.org/Build_package.html).

To finish this project, build our own LAMMPS version with the following two packages included:

- MANYBODY package. This is to use the manybody potential such as the embedded-atom method potential.
- VORONOI package. This is to calculate Voronoi tessellation of the atoms in the simulation cell. To learn more, please visit [this page](https://docs.lammps.org/compute_voronoi_atom.html).

60 LAMMPS simulations will be conducted in this project. Each time we run a new simulation, create a new directory.

The interatomic potential is the same one used in our previous project.

## Related to a previous project

In [a previous project of ours](https://github.com/shuozhixu/Materials_2024), the CLS processes in nanolaminated Ag and two types of Ag/Cu nanolaminates were studied. The layer thickness for each metal was 5 nm. No cavities were involved. According to four experimental Ag/Cu nanolminates papers above, (i) there is a cavity-free zone within 20 nm from the interface in the Cu layer and (ii) the cavity can be a void or a He bubble. For cavities near the interface, they adhere to the interface in the Ag layer rather than straddling the interface in both metals. Therefore, if one were to insert a cavity in our previous 5-nm-thick model, the cavity either adheres to the interface in the Ag layer or sits in the middle of the Ag layer. In addition, the cavity's diameter varies from 1 nm to 12 nm according to [Wang et al.](https://doi.org/10.1016/j.actamat.2018.09.003)

Unfortunately, there is no interatomic potentials for Ag/He, and so we only consider void.

## Nanolaminated Ag

Our previous project considered CLS in all three different slip planes. Here, let's consider all of them.

Therefore, we need to insert a void either at the interface or in the middle of a Ag layer where CLS takes place. For each slip plane, let the dislocation glide through the center of the void. The insertion of the void can be done in [LAMMPS](https://docs.lammps.org/delete_atoms.html) or [atomsk](https://atomsk.univ-lille.fr/tutorial_removeatoms.php). Three void diameters can be considered: 1 nm, 2 nm, and 3 nm.

Since there are three void sizes, two void locations, and three slip planes, 18 LAMMPS simulations need to be conducted.

## Ag/Cu Nanolaminate - type 1

Our previous project considered CLS in 10 different slip planes, which possess different critical stresses for CLS. Here, let's consider three planes: one with the maximum critical stress, one with the minimum critical stress, and another with the average critical stress.

As a result, 18 LAMMPS simulations need to be conducted.

## Ag/Cu Nanolaminate - type 2

Along the same line of thought, let's consider three planes here too. Similarly, another 18 LAMMPS simulations should be conducted.

## Single crystalline pure metals

There are two pure metals, Cu and Ag. To provide references, we can simulate the dislocation/void interactions in Ag, and compare results with those in nanolaminates. The dislocation line should be 5 nm, the same as those used in nanolaminates. There are two types of boundary conditions along the dislocation line direction: periodic boundary conditions and traction-free boundary conditions. Thus, there are 6 cases in total.

The dislocation/void interactions in a Cu single crystal where the periodic boundary conditions were applied along the dislocation line were modeled in [a previous paper](http://dx.doi.org/10.1088/1361-651X/ab8358), which should be studied closely.

## References

If you use any files from this GitHub repository, please cite

- Wu-Rong Jian, Yanqing Su, Shuozhi Xu, Weisen Ji, Irene J. Beyerlein, [Effect of interface structure on dislocation glide behavior in nanolaminates](http://dx.doi.org/10.1557/s43578-021-00261-y), J. Mater. Res. 36 (2021) 2802--2815
- Wu-Rong Jian, Min Zhang, Shuozhi Xu, Irene J. Beyerlein, [Atomistic simulations of dynamics of an edge dislocation and its interaction with a void in copper: A comparative study](http://dx.doi.org/10.1088/1361-651X/ab8358), Modelling Simul. Mater. Sci. Eng. 28 (2020) 045004