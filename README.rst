.. figure:: https://github.com/sjthursby/CandiMeth/blob/master/images/CandiMeth%20Logo.png
   :alt: CandiMeth Logo


Using CandiMeth for Feature Methylation Quantification in Galaxy
================================================================

A.  `CandiMeth History with Test Data <http://bit.do/candimeth-history>`_
--------------------------------------------------------------------------

B. `CandiMeth Workflow <http://bit.do/candimeth>`_
---------------------------------------------------

C. `CandiMeth Workflow Download (for personal or alternative Galaxy instances) <http://bit.do/candimeth-download>`_
--------------------------------------------------------------------------------------------------------------------

D. Prerequisites
----------------

Before starting you should have a working `Galaxy <https://www.usegalaxy.org/>`_ account with the following datasets that you can upload:

- Analysed methylation array data computed in either RnBeads or ChAMP
- A list of features for investigation in your methylation array data

E. Summary
----------
Using existing tools in the Galaxy environment we generated the workflow CandiMeth (CANDIdate feature METHylation). This takes as input a differential methylation table from an R-based package and maps it to a reference genome build. A simple interface then allows the user to query the dataset with inputs as straightforward as lists of gene names, or as detailed as bed files containing specific chromosomal coordinates, for more sophisticated analyses. 

The major outputs are: 

1. Tracks in the UCSC genome browser showing both absolute and differential methylation
2. Tables containing summary statistics on the candidate regions. The simultaneous visualization and statistical analysis make it a        powerful tool for the intuitive exploration of differences in the methylation landscape between samples. 

Cross-comparison to other open-resource data tracks at UCSC facilitates hypothesis formulation which can then be directly tested using the query function. 

CandiMeth allows rapid, quantitative analysis of methylation at user-specified features without the need for coding and is freely available `here <http://bit.do/candimeth>`_.


Thank you for using CandiMeth!

F. Quick Start Guide
--------------------

Click `here <http://bit.do/candimeth-history>`_ and click the + button at the top RHS of the page –
this will create a History containing the reference genome information to be used in the CandiMeth workflow in your own Galaxy account.

Uploading your data to Galaxy
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For this you need:

- At least one file containing information on methylation differences between two
  samples produced from either RnBeads or ChAMP (for Input Type 1 below) 
- A list of candidate features which you want to look at (Input Type 2 below)1. Example names for these files are given below, but         the actual files and names will be decided by the user each time

Upload Input Type 1: Differential Methylation Table
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. On the LHS of the Galaxy homepage click on > Get Data > Upload File > Choose Local File and locate your methylation data you wish to upload (e.g. Suppl. Table 1)

2. Set “Type (set all)” to whatever kind of file you are uploading, for example, RnBeads based outputs are usually comma separated variable files (.csv)
   
:Tip: The default **Auto-detect** setting works well for most file formats.

3. Set **“Genome (set all)”** to either **Human Feb. 2009 (GRCh37/hg19)** or **Human Dec. 2013 (GRCh38/hg38)** depending on what genome your array was mapped to (Supp Table 1 maps to hg19).

:Tip: You can type in Human here to bring up all the human genomes and save time.

4. Click **“Start”**: the file should upload to Galaxy and appear as a dataset on the RHS: this goes from grey to orange then finally green if all is well

5. The input Differential Methylation Table has to be converted from a table into the form of a Dataset Collection: This is in case there are multiple differential methylation tables to be assessed, then CandiMeth can assess them all simultaneously and present them in the typical Results and Tracks outputs, as opposed to multiple outputs that might make your history very crowded: 
   - Click on the already checked box at the top of the History panel (mouse over shows
   **“Operations on multiple datasets”**): this will cause checkboxes to appear beside all of your
   datasets as well as some choices to appear at top
   - Check the box beside the Differential Methylation Table dataset(s)
   - Under the pulldown menu beside **“For all selected"** choose **“Build Dataset List”**
   - In the window that appears, you can give the collection a new name e.g. “DMP set1” and
   click **“Create”**
   - A new entry will appear in the RHS with the new name and “a list with 1 (or more) items”-
   this is the Dataset Collection and is now ready to be processed by CandiMeth
   Upload Input Type 2: Candidate Features of interest

6. If you want to query individual candidate genes, the names of these genes can simply be written
   in by using >Get Data and chose Upload file, then click on **“Paste/Fetch data”**, which will open up
   a smaller window

7. Just type or paste in the names of the genes you wish to investigate onto separate lines as in the
   example below -

PICTURE HERE

8. Give the list a name e.g. “Features”, choose tabular as the Type, and then the relevant human
   genome release e.g. Human Feb. 2009 (GRCh37/hg19) as above.

9. Click **“Start”**: the file should upload to Galaxy and appear as a separate dataset on the RHS

:Tip: If you have a longer or more complex list, this can be uploaded directly from a .txt file format (e.g. Supp Table 2) by following  steps 4-6 above i.e. >Upload file>Choose local file, the format is Tabular (or use Auto-detect)

Using CandiMeth
^^^^^^^^^^^^^^^

- Go `here <http://bit.do/candimeth>`_ then click the + button at the top RHS of the page 
  - This will import the CandiMeth workflow to your Galaxy account so you can use it
  
- At the top of the Galaxy homepage, click on the **"workflows"** option

- Click on the newly imported CandiMeth workflow and on the pull-down menu at RHS
  marked with a downward arrow choose > Run
  
- In the History Options at the top of CandiMeth, click yes to **“Send results to a new history”**

- Under 1: **R Package Used: (1.1)** enter ‘RnBeads’ or ‘ChAMP’ depending on which was used to
  generate the Differential Methylation Data used as input in Step 3 above
  
- For 2: **Input Differential Methylation Table (1.2)** choose “DMP set1” or whatever other label
  was used at Step 5 above
  
- At 3: **Input Gene Features of Interest (1.3)** choose “Features” or whatever label was used at
  Step 10 above.
  
- Finally, for 4: **Input Genome Release Information (1.4)** pick a relevant dataset from the
  CandiMeth set uploaded into your History at Step 2 above e.g. “hg19_GB” if you want to
  look at gene body methylation in the genes listed in the Features list (i.e. miR if Supp. Table
  2 was used). If you want to look at promoters choose “hg19_prom” instead

- If all goes well, you should see a large green tick in the main (middle) window of Galaxy and **“Successfully invoked workflow           CandiMeth: the results will be sent to a new history, click here to switch to that history now”**

- New history “Test1” can be found by clicking the history button (looks like a book) at the top RHS of the page, navigate between history’s using the **“Switch       to”** function



