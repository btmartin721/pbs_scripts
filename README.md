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

