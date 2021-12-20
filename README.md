These scripts are for processing the entire genome for both Human and Mouse.

**Cas9**

For Cas9, we **need** to run the guidescan first. 

***Cas9_Human_Mouse_GuideScan_FlatFileProcessing.Rscript:***


For running this script, we need to give 4 arguments:<br />
 
<li> Argument 1 : "Human" or "Mouse" </li>
<li> argument 2 :  The gtf file assosiated with species </li>
<li> argument 3 :  The output file from the Guidescan tool </li>
<li> argument 4 :  The directory where we need to save the result </li>
<br />

The results will be saved in the Output Directory which is specified in argument 4.

**Cas12**

For Cas12, we **do not** run the guidescan. The guidescan scores are provided by the vidigal group in flat file format and is saved in the FRCE cluster shared drive under:

````
/mnt/CSS-Statistics/CRISPR/Cas12-GuideScan/Cas12a_hg38_ennumerations.txt
````

***1_Cas12_Human_Mouse_ChymeraScores_FlatFileProcessing.Rscript:***
   
For running the script, we need to have 3 arguments: 
<li> Argument 1: The species (Mouse or Human) </li>
<li> Argument 2: The gtf file assosiated with species </li>
<li> Argument 3: The output directory for saving the results </li>
<br />

The R script will save a fasta file for each chromosome under folder cas12_Human__Fullgtf_Chymera_FASTA if the species is Human or cas12_Mouse__Fullgtf_Chymera_FASTA if the species is Mouse.<br />

It will also save an ".RData file", which contains all the Cas12 sequences along with additional fields.<br />


***2_Cas12_Human_Mouse_MergeAll_FlatFileProcessing.Rscript*** <br />

This will merge all the files that we created and also the guide scan scores the vidigal group provided.  We need to give arguments 5 . <br />
        
<li> Argument 1: The .RData file that we saved by running the script *1_Cas12_Human_Mouse_ChymeraScores_FlatFileProcessing.Rscript*. </li>
<li> Argument 2: The species that we are processing  – “Human” or “Mouse” </li>
<li> Argument 3: The folder where we have the chymera scores. </li>
<li> Argument 4: The folder where we need to save the output. </li>
<li> Argument 5: The txt file from the vidigal group having the guidescan scores. </li>
 The guidescan score is saved in folder
    
    /mnt/CSS-Statistics/CRISPR/Cas12-GuideScan/Cas12a_hg38_ennumerations.txt. <br />

    This script will save the final file in the output folder specified in Argument 4.







