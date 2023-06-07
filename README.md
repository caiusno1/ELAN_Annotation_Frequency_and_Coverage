# ELAN Annotation Frequency and Coverage
A python project to count annotation lables on one tier (per speaker) and calculate the coverage of all lablels on tier per Speaker.
# Some word of warning
The project is currently adapted to counting number lables e.g. 1, 2, 2.1 .... If you want to count other lable types some manual adjustments to the scripts are needed. Some insights are given in the Getting Started paragraph below
## Getting Startet
Step 1: You need the following python packages to be installed:
- pympi
- nltk
- pandas
  
And you need a jupyter notebook setup  
  
Your can skip steps 2-7 if you need no automatic correction
Step 2: Put your ELAN files in ELAN_correction\in  
  
Step 3: Change ELAN_correction\Nodeaufstellung.csv to include all lables of the tier of interest that should exist  
  
Step 4: open ELAN_correction\analysis.ipynb
The tiers analysed per default are:
-EE_Gamenodes
-EX_Gamenodes  
If your tiers are labled different change all occurences with your tier names. Notice that sometimes "_Gamenodes" is appended to a role (EE vs. EX). These occurences also have to be replaced.  
If your roles to analyse are not EE and EX also change the role names accordingly  
  
Step 5: implement own corretion strategies in cell 3  

Step 6: Run the jupyter notebook ELAN_correction\analysis.ipynb  

Step 7: Copy the changed files from ELAN_correction\out to ELAN_node_statistics\in  

Step 7a: If you have done no correction place your ELAN files in ELAN_node_statistics\in  

Step 8:  Change ELAN_node_statistics\Nodeaufstellung.csv to include all lables of the tier of interest that should exist  

Step 9: open ELAN_node_statistics\analysis.ipynb
The tiers analysed per default are:
-EE_Gamenodes
-EX_Gamenodes  
If your tiers are labled different change all occurences with your tier names. Notice that sometimes "_Gamenodes" is appended to a role (EE vs. EX). These occurences also have to be replaced.    
If your roles to analyse are not EE and EX also change the role names accordingly  
If you do not need the provided error correction for analysis (remove X,x; adding points) you need to remove it manually (It should do no harm if you have only word lables that do not contain X).   

Step 10: Inspect the results in ELAN_node_statistics\out  

## Warning and errors
In the out folder of the respective subproject you find error.log and warning.log files.   
In these files you can see which lables are renamed to which other lables (for correction) in the analysis and in the preprocessing correction.  
Also you can see which lables occure in your data but do not occure in the prespecified Nodeaufstellung.csv. This typically can inform you of bad coding in your data.