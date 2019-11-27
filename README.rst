.. figure:: https://github.com/sjthursby/CandiMeth/blob/master/images/CandiMeth%20Logo.png
   :alt: CandiMeth Logo


Using CandiMeth for Feature Methylation Quantification in Galaxy
================================================================

A. `Step-by-Step Guide <https://drive.google.com/file/d/1HgPfKsN2GLNBAg9Nw36tpaeHZkWsvtN8/view?usp=sharing>`_
---------------------------------------------------

B.  `CandiMeth History with Test Data <http://bit.do/candimeth-history>`_
--------------------------------------------------------------------------

C. `CandiMeth Workflow <https://bit.do/candimeth/>`_
---------------------------------------------------

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

CandiMeth allows rapid, quantitative analysis of methylation at user-specified features without the need for coding and is freely available `here <https://bit.do/candimeth/>`_.


Thank you for using CandiMeth!




