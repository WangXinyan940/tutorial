# tutorial

Example of a general input parameter files for Gromacs 4 for using flexDQ water model.

md-xxx.mdp is the input parameter for mdrun
xxx.gro is the initial structure of the system
topol-xxx.top is the topology file
index-xxx.ndx is generated from make_ndx, grps name should be same with .mdp

-table gives the prefix of the tabulated potential files

Water .itp should be included in the .top file (#include flexdq.itp)

For CH4 system:
### Generate .tpr file
grompp -f md-ch4.mdp -c ch4.gro -p topol-ch4.top -n index-ch4.ndx -o md.tpr
### Launch the simulation
mdrun -deffnm md -table md

For Na system:
### Generate .tpr file
grompp -f md-na.mdp -c na.gro -p topol-na.top -n index-na.ndx -o md.tpr
### Launch the simulation
mdrun -deffnm md -table md

For Cl system:
### Generate .tpr file
grompp -f md-cl.mdp -c cl.gro -p topol-cl.top -n index-cl.ndx -o md.tpr
### Launch the simulation
mdrun -deffnm md -table md




