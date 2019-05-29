# pbs_scripts  
Some PBS scripts for a TORQUE job scheduler that I used to submit my jobs to the University of Arkansas's HPC cluster.  

## hzar.pbs  

Dependencies:  
```
GNU parallel
R (tested with v. 3.4.3)
```

The script uses awk to get the number of loci from a one-line, comma-separated file containing one field for each locus (e.g., the loci names).  If you want to manually specify $maxLocus, just change it in the script before running.  

Also requires my HZAR_runSingle.R script located in my [R_scripts Repository](https://github.com/btmartin721/R_scripts)  

The file structure is intended for the Uark AHPCC machine, so you might have to mess around with script to suit your needs.  

## bfd.pbs  

This script runs Bayes Factor Delimitation (BFD*). You'll probably need to change the number of threads and queue information depending on your HPC machine.  

There is a sed command to change BFD's root directory XML file so you can use the same PBS script for multiple runs easily. But it assumes that the root option in the XML file is specified as "temp&". If the sed command doesn't find "temp&" it won't do anything.  


