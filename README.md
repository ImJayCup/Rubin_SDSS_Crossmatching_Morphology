# Rubin_SDSS_Crossmatching_Morphology
Rubin Observatory cross-matching tool, plus a utility to calculate morphology for galaxies in the SDSS and LSST.

**Data Structure**

1. _rubin_crossmatch.ipynb_ takes an input variable named CATALOG. It assumes you have a file called "targets_{CATALOG}.csv" containing two columns titled ra,dec with the coordinates of each galaxy you'd like to find. The notebook then defines several helper functions and checks the DP1 and DP2 tracts for your input CATALOG. If you'd only like to check one of the data previews, use the TO_RUN variable at the top of cell 4. Each galaxy is given a **Galaxy ID (gid)**, used as an identifier throughout this project. The output is saved as {CATALOG}_rubin_coverage.csv, and an optional sky plot is available in cell 6 to check where the matches are on sky. 

2. _rubin_morphology.ipynb_ takes an input variable CATALOG. It assumes you have a file "{CATALOG}_coverage.csv," which is generated upon successfully running _rubin_crossmatch.ipynb_. For each galaxy present in the Rubin footprint, the notebook will create a dynamic cutout of the galaxy according to its size, use photutils.segmentation to generate a segment map of the galaxy, use the segment map to mask out contaminants in the field, and run statmorph (Rodriguez-Gomez+19, Sazonova+2025) on the galaxy. The output is saved as "{CATALOG}_dp2_morphology.csv" and Source_Morphology() objects (see [here]((https://statmorph.readthedocs.io/en/latest/api.html#statmorph.source_morphology)) are stored in a folder called "{CATALOG}_dp2_morphology_pkl."

3. _sdss_morphology.ipynb_ is similar to (2), but uses the Sloan Digital Sky Survey Science Archive Server (SDSS SAS) to retrieve r-band image frames of galaxies observed by the SDSS (see [here](https://data.sdss.org/sas/dr17/eboss)). Takes an input file "{CATALOG}_coverage.csv" and gives an output file "{CATALOG}_sdss_r_morphology.csv." Source_Morphology() objects are stored in a folder called "{CATALOG}_sdss_morphology_pkl."


**AI DISCLOSURE**
A generative AI tool [Claude Opus 5.5] was used to aid production of the code found in this repository. All AI-assisted code is tested/supervised on the line-level by a human, and all comments/explanations are written by a human. Any AI-assistance is strictly to aid with implementation of code. No part of this project is directed by generative AI. Generative AI is used to format some figures for accessibility and readability. 

**Contact**
Please direct questions to jacob.yuzovitskiy@macaulay.cuny.edu.
