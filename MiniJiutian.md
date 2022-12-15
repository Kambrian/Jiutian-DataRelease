- Simulation Name: MiniJiutian

- Simulation info:

    * Code: PGadget-3
    * Number of Particles: 3000**3
    * Cosmology: Plank-20xx
    * Path: `/public/home/liming/NS_Data_150Mpc`
    
- Overview of Data Products:

    * Snapshots: Each snapshot records the position/velocity/id of each particle in the simulation box at a given time. 
       
       - Files: snapdir_$snapnum/snapshot_$snapnum.*, with $snapnum ranging from 000 to 128. Each snapdir is one snapshot, split into multiple subfiles.
       - File Formats: PGadget-3 binary format (see technical description in `/public/home/liming/NS_Data_150Mpc/ReadMe`) 

    * Groups: Halos (also called groups) are identified at each snapshot with the FoF algorithm. The group_id file contains the list of particle ids within each group. The group_tab file contains various bulk properties of each group, as well as some meta-data for the group_id file.
        - Files: groups_$snapnum/
        - subhalo_tab_$snapnum.*: group tab file
        - subhalo_ids_$snapnum.*: group id file
        - File Formats: SUBFIND binary format (see technical description in `/public/home/liming/NS_Data_150Mpc/ReadMe`). Note these files contain both the FoF group info, and the SUBFIND subhalo info (see below).

    * SUBFIND subhalos: subhalos are identified within each FoF group, as locally self-bound overdense structures. There are different codes (subhalo-finders) for building subhalos from FoF groups, and SUBFIND is the code that ships with the GADGET simulation code. 
        - Files: groups_$snapnum/ . These are the same set of files as the groups. These files contain both the FoF group info, and the SUBFIND subhalo info.

    * SUBFIND merger tree: subhalos at different time are not independent from each other. Rather they are largely the same population of objects recorded at different time. The merger tree files contain the information to link subhalos across snapshots, into evolution sequences. Note HBT+ files contain both the subhalos as well as their links accross time, so no separate tree files are needed.
        - Files: treedata/
        - File Format: ToBeAdded

    * HBT+ subhalos: subhalos are identified within each FoF group, as locally self-bound overdense structures. There are different codes (subhalo-finders) for building subhalos from FoF groups. HBT+ (https://github.com/Kambrian/HBTplus) is a unique code for robustly identifying subhalos. It also records the progenitor-descendant link between subhalos in neigbouring snapshots, i.e., the subhalo merger trees, in a fully consistent and physical way.
        - Files: hbt/$snapnum/SubSnap_$snapnum.*.hdf5, with each subhalos in snapshot split into multiple files
        - File Format: hdf5 format. See https://astroyzgu.github.io/csstmock/hbt.html for detailed file content info.
        - Documentation on the data and example io: https://github.com/Kambrian/HBTplus/wiki/Outputs

     * Subhalo lightcone for HBT+: ToBeAdded (Zhenlin Tan)
     * GAEA-HBT galaxy snapshots: ToBeAdded (Lizhi Xie)
     * GAEA-HBT lightcone: ToBeAdded (Zhenlin Tan & Lizhi Xie)

     * L-Galaxy Snapshots: ToBeAdded (Qi Guo, Yu Luo, ...)
     * L-Galaxy lightcone: ToBeAdded.

     * Lensing lightcone: ToBeAdded (Xi Kang)
