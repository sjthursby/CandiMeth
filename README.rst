.. figure:: https://github.com/sjthursby/CandiMeth/blob/master/candimeth%20for%20epigenetis%20workshop.png
   :alt: CandiMeth Logo


Using CandiMeth for Feature Methylation Quantification in Galaxy
================================================================

A. Prerequisites
----------------

Before starting you should have a working `Galaxy <www.usegalaxy.org>`_ account with the following datasets that you can upload:

- Analysed methylation array data computed in either RnBeads or ChAMP
- A list of features for investigation in your methylation array data

B. Uploading your data to Galaxy
--------------------------------

If you have not done so already, the data to be analysed needs to be uploaded to Galaxy in order to be used. There is a very comprehensive `tutorial <https://galaxyproject.org/tutorials/upload/>`_ on this, provided by the Galaxy Developers, but in brief;

- Log into `Galaxy <www.usegalaxy.org>`_
- On the LHS of the Galaxy homepage click on >Get Data > Upload File > Choose Local File and locate your methylation data you wish to upload
-	Set “Type (set all)” to whatever kind of file you are uploading, for example, RnBeads based outputs are usually comma separated variable files (.csv)
-	Set “Genome (set all)” to either Human Feb. 2009 (GRCh37/hg19) or Human Dec. 2013 (GRCh38/hg38) – depending on what genome your array was analysed in accordance to.
-	Click “Paste/Fetch data” and paste in the features you wish to investigate and set the type to “Tabular” as below

.. figure:: https://github.com/sjthursby/CandiMeth/blob/master/upload_file_example.png
   :alt: Example Upload


-	Click “Start” and close that window
-	Your files should appear in the History column at the RHS under the name of the file. At first, the uploaded file will appear on a grey background (loading) then yellow (working) and finally green (complete)
-	Once the upload appears on a green background within the history column, you are ready to use CandiMeth

C. Using CandiMeth
------------------

- Click `here <http://bit.do/CandiMeth>`_ to get the CandiMeth workflow, then click the plus button at the top RHS of the page, this will import the CandiMeth workflow to your Galaxy account so you can use it
-	Following this, go to the `CandiMeth History <http://bit.do/CandiMeth-History>`_ and click the same button to import and start using this history – this is the data used in the fourth input step of CandiMeth, to annotate the features for investigation
- At the top of the Galaxy homepage, click on the "workflows" option to see all the workflows that are available to you
- Click on the newly imported CandiMeth workflow and click on the downwards facing arrow > Run
- To demonstrate how CandiMeth works, `Example data <http://bit.do/CandiMeth-test-data>`_ will be used
-	In this example, RnBeads based data will be used as an input, although as can be seen from the test data, ChAMP data is also accepted
-	Input RnBeads or ChAMP data has to be in the form of a dataset collection. However, an excellent tutorial on how to create these can be found `here <https://galaxyproject.org/tutorials/collections/#creating-a-collection-from-datasets-in-your-history>`_
-	In the History Options at the top of CandiMeth, click yes to “Send results to a new history” – we recommend doing this, as CandiMeth generates a lot of hidden background jobs so it is more convenient if the workflow runs by itself in the background while other tasks can be completed in the interim
-	In R Package Used: (1.1) enter ‘Rnbeads’ if using the test data or RnBeads based data or ‘Champ’ / ‘Custom’ if using ChAMP or Custom generated outputs. This will tell CandiMeth the R package the input data has originated from and therefore how to process the data for feature investigation
-	For Step 2: Input Differential Methylation Table (1.2) input “Step 2 Example Input: d10 rnbeads output” (from the test data). In this box differential methylation data from RnBeads, ChAMP or a custom package should be input (see the CandiMeth paper for definition of suitable custom package definitions).
-	In Step 3: Input Features of Interest (1.3) the features you wish to investigate should be input here. In the test data, this is “Step 3 Example Input: mir379 Cluster list.txt”. This data will tell CandiMeth which portions of the genome to be annotated and investigated within your data.
-	Finally, for step 4 input “Step 4 Example Input: hg19_Prom_NHLF_CHMM.txt” or any data from the CandiMeth History mentioned above. This will provide CandiMeth with the necessary genomic data to annotate and calculate the methylation of, in this case, the chromatin segmentations of normal human lung fibroblasts across your chosen features.

D. CandiMeth Outputs
-------------------
CandiMeth produces two outputs; tracks and results. The tracks cover a variety of visualization methods for UCSC Genome Browser including displaying; absolute methylation, the difference in methylation between control and experimental (delta beta) and FDR significant sites i.e. those deemed statistically significant after correction for multiple testing. These tracks can help identify further targets for investigation or design pyrosequencing primers for verification of results at specific regions.

CandiMeth Results show each feature input, either in the gene body, promoter or overlapped with another genomic annotation such as chromatin state segmentation or RepeatMasker, the probe coverage in that area, median methylation across that area, standard deviation, mean methylation, maximum and minimum methylation in that area. These results can be used in the already available visualisation tools within Galaxy (using the graph button when previewing data) or downloaded and plotted in alternative software.

A video tutorial of using CandiMeth can also be found `here <https://drive.google.com/file/d/1LjEP0gy3aoZi26Jr0N6JbUx584LA0cD0/view?usp=sharing>`_
            


