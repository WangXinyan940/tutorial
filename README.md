# tutorial

Example of a general input parameter files for Gromacs 4 for using flexDQ water model.

For the usage of Gromacs, please check http://www.gromacs.org/

md-xxx.mdp is the input parameter for mdrun

xxx.gro is the initial structure of the system

topol-xxx.top is the topology file

index-xxx.ndx is generated from make_ndx, grps name should be same with .mdp

-table gives the prefix of the tabulated potential files

Water .itp should be included in the .top file (#include flexdq.itp)

Here, we put all the input parameter files used in each files folder.

User can run a simulation directly in the certain directory.

###For Na system:
#### Generate .tpr file
grompp -f md-na.mdp -c na.gro -p topol-na.top -n index-na.ndx -o md.tpr
#### Launch the simulation
mdrun -deffnm md -table md

###For Cl system:
#### Generate .tpr file
grompp -f md-cl.mdp -c cl.gro -p topol-cl.top -n index-cl.ndx -o md.tpr
#### Launch the simulation
mdrun -deffnm md -table md

###For CH4 system:
#### Generate .tpr file
grompp -f md-ch4.mdp -c ch4.gro -p topol-ch4.top -n index-ch4.ndx -o md.tpr
#### Launch the simulation
(For CH4 system, one first need to choose ./ch4-b/ or ./ch4-s/ to run. 

 Then rename the md_CH4_O-x.xvg to md_CH4_O.xvg, md_CH4_H-x.xvg to md_CH4_H.xvg.
 
 So that we do not have to modified the parameters in .mdp or .ndx)
 
mdrun -deffnm md -table md

###For DPPC membrane system:
#### Generate .tpr file
grompp -f md-mem.mdp -c mem.gro -p topol-mem.top -n index-mem.ndx -o md.tpr
#### Launch the simulation
mdrun -deffnm md -table md
(For DPPC-water system, the parameters of DPPC are from MARTINI force field. 
We combine DPPC parameters with our flexDQ parameters directly.)

