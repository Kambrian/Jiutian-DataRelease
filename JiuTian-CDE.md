- Simulation Name: JiuTian-CDE

- Simulation Info: 
  
  * Code: ME-Gadget4
  * Number of Particles: 1024^3, 2048^3
  * BoxSize: 1.5 Gpc/h
  * Cosmology: LCDM, Conformal 0.03, Conformal 0.06, Disformal 45, Disformal 105, Quintessence 0.8, Quintessence 1.6
  * Path:
  /public/home/jjzhang/N-body-Kunshan/sim1024/LCDM/
  /public/home/jjzhang/N-body-Kunshan/sim1024/Conformal/alpha_0.03/
  /public/home/jjzhang/N-body-Kunshan/sim1024/Conformal/alpha_0.06/
  /public/home/jjzhang/N-body-Kunshan/sim1024/Disformal/Dm_45/
  /public/home/jjzhang/N-body-Kunshan/sim1024/Disformal/Dm_105/
  /public/home/jjzhang/N-body-Kunshan/sim1024/Quintessence/lambda_0.8/
  /public/home/jjzhang/N-body-Kunshan/sim1024/Quintessence/lambda_1.6/
  /public/home/jjzhang/N-body-Kunshan/sim2048/LCDM/
  /public/home/jjzhang/N-body-Kunshan/sim2048/Conformal/alpha_0.03/
  /public/home/jjzhang/N-body-Kunshan/sim2048/Conformal/alpha_0.06/
  /public/home/jjzhang/N-body-Kunshan/sim2048/Disformal/Dm_45/
  /public/home/jjzhang/N-body-Kunshan/sim2048/Disformal/Dm_105/
  /public/home/jjzhang/N-body-Kunshan/sim2048/Quintessence/lambda_0.8/
  /public/home/jjzhang/N-body-Kunshan/sim2048/Quintessence/lambda_1.6/


- Overview of Data Products:

    * Snapshots: Each snapshot records the position/velocity/id of each particle in the simulation box at a given time. 
       
       - Files: snapdir_$snapnum/snapshot_$snapnum.*.hdf5, with $snapnum ranging from 000 to 046/048/etc. Each snapdir is one snapshot, split into multiple subfiles.
       - File Formats: Gadget-4 HDF5 format 

    * Groups: Halos (also called groups) are identified at each snapshot with the FoF algorithm. 
        - Files: groups_$snapnum/
        - fof_tab_$snapnum.*.hdf5: group tab file (only in sim1024/)
        - fof_subhalo_tab_$snapnum.*.hdf5: group tab file with subhalo (only in sim2048/)
        - File Formats: SUBFIND HDF5 format. Note these files contain the FoF group info (for sim1024), and the SUBFIND subhalo info (for sim2048).

    * SUBFIND subhalos: subhalos are identified within each FoF group, as locally self-bound overdense structures. There are different codes (subhalo-finders) for building subhalos from FoF groups, and SUBFIND is the code that ships with the GADGET simulation code. 
        - Files: groups_$snapnum/ . 
        - fof_subhalo_tab_$snapnum.*.hdf5: group tab file with subhalo (only contained in sim2048/)
    * Powerspectrum: matter power spectrum are measured using the integrated module in Gadget4.
        - Files: powerspecs/ .
        - powerspec_$snapnum.txt: txt file recording the measured matter power spectrum from $snapnum snapshot.
