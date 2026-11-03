# Rubin_SDSS_Crossmatching_Morphology
Rubin Observatory cross-matching tool, plus a utility to calculate morphology for galaxies in the SDSS and LSST.

**Data Structure**

1. _rubin_crossmatch.ipynb_ takes an input variable named CATALOG. It assumes you have a file called "targets_{CATALOG}.csv" containing two columns titled ra,dec with the coordinates of each galaxy you'd like to find. The notebook then defines several helper functions and checks the DP1 and DP2 tracts for your input CATALOG. If you'd only like to check one of the data previews, use the TO_RUN variable at the top of cell 4. The output is saved as {CATALOG}_rubin_coverage.csv, and an optional sky plot is available in cell 6 to check where the matches are on sky.

2. _rubin_morphology.ipynb_


**AI DISCLOSURE**
Generative AI tools ([Claude Opus 5.5]) were used to aid production of these resources. Any AI-assisted code is tested/supervised on the line-level by a human, and all comments/explanations are written by a human. Any AI-assistance is strictly to aid with implementation of code. No part of this project is directed by generative AI. 
