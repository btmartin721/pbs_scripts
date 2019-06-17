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

## bfd_resume.pbs  

This script resumes a BFD* run. It requires GNU parallel to work. GNU parallel runs multiple BFD threads in parallel. You may have to change the max number of threads where it says: <(seq 0 23).  

You'll have to change the path to the resume.sh script in parallel command.  

The script will fail if the user doesn't have execute permissions for resume.sh in all the step{} directories. For some reason user execute permissions are off by default with BFD.   

The script will also fail if the likelihood.log files have recorded likelihoods at different frequencies than the other log files.  

## submit_str.pbs

Will need to modify the parameters in the script.  
