# ELAN Annotation Frequency and Coverage [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.8014393.svg)](https://doi.org/10.5281/zenodo.8014393)
A Python project to count annotation labels on one tier (per speaker) and calculate the coverage of all labels on tier per Speaker.
# Some word of warning
The project is currently adapted to counting number labels e.g. 1, 2, 2.1 .... If you want to count other label types some manual adjustments to the scripts are needed. Some insights are given in the Getting Started paragraph below
## Getting Started
Step 1: You need the following Python packages to be installed:
- pympi
- nltk
- pandas
  
And you need a jupyter notebook setup  
  
You can skip steps 2-7 if you need no automatic correction  
Step 2: Put your ELAN files in ELAN_correction\in  
  
Step 3: Change ELAN_correction\Nodeaufstellung.csv to include all labels of the tier of interest that should exist  
  
Step 4: open ELAN_correction\analysis.ipynb
The tiers analyzed per default are:
-EE_Gamenodes
-EX_Gamenodes  
If your tiers are labeled differently change all occurences with your tier names. Notice that sometimes "_Gamenodes" is appended to a role (EE vs. EX). These occurrences also have to be replaced.  
If your roles to analyze are not EE and EX also change the role names accordingly  
  
Step 5: implement your own correction strategies in cell 3  

Step 6: Run the jupyter notebook ELAN_correction\analysis.ipynb  

Step 7: Copy the changed files from ELAN_correction\out to ELAN_node_statistics\in  

Step 7a: If you have done no correction place your ELAN files in ELAN_node_statistics\in  

Step 8:  Change ELAN_node_statistics\Nodeaufstellung.csv to include all labels of the tier of interest that should exist  

Step 9: open ELAN_node_statistics\analysis.ipynb
The tiers analyzed per default are:
-EE_Gamenodes
-EX_Gamenodes  
If your tiers are labeled differently change all occurences with your tier names. Notice that sometimes "_Gamenodes" is appended to a role (EE vs. EX). These occurrences also have to be replaced.    
If your roles to analyze are not EE and EX also change the role names accordingly  
If you do not need the provided error correction for analysis (remove X,x; adding points) you need to remove it manually (It should do no harm if you have only word labels that do not contain X).   

Step 10: Inspect the results in ELAN_node_statistics\out  

## Warning and errors
In the out folder of the respective subproject, you find error.log and warning.log files.   
In these files, you can see which labels are renamed to which other labels (for correction) in the analysis and in the preprocessing correction.  
Also, you can see which labels occur in your data but do not occur in the prespecified Nodeaufstellung.csv. This typically can inform you of bad coding in your data.
