# Stellar Clustering: Evaluating Clustering Methods for Reconstructing Hertzsprung–Russell Diagrams

## Overview

This project uses a quality filtered sample of Gaia Data Release 3 (DR3) stellar data to construct a Hertzsprung-Russel (HR) diagram, and performs unsupervised clustering using K-Means, DBSCAN (Density-Based Spatial Clustering of Applications with Noise), and GMM (Gaussian Mixture Modelling). The goal is to investigate whether these unsupervised clustering methods can recover meaningful stellar population groupings within the HR diagram, and determine which method gives the most astronomically informative results.

***

## Research Question

**Can unsupervised clustering of random Gaia DR3 star data return a plot similar to the Hertzsprung-Russell diagram? If so, which clustering method out of K-means, DBSCAN, GMM gives the best result?**

***

## Project Workflow

This project uses the following methods/techniques:

- Collect a quality filtered data set from Gaia DR3
- Calculate absolute magnitude values from apparent magnitude and parallax required for plotting an HR diagram
- Plot BP-RP colour index vs. absolute magnitude graph
- Perform unsupervised clustering on graph using outlined methods
- Analyze resulting plots, discuss limitations, and draw conclusions
- Discuss potential directions for future work

***

## Dataset used

**Source:** **[Gaia Data Release 3 (DR3)](https://www.cosmos.esa.int/web/gaia/dr3)**, queried directly from the [Gaia Archive](https://gea.esac.esa.int/archive/) with ADQL  

**Sample:** quality-filtered, random subset of 10000 stellar sources 

***

## Results

Three clustering methods were evaluated: K-Means, DBSCAN, and Gaussian Mixture Modelling (GMM).

- K-Means (k = 3) divided the HR diagram primarily according to geometric distance from cluster centroids. The resulting regions did not correspond clearly to distinct astrophysical populations, highlighting the limitations of K-Means for irregular and unevenly distributed stellar data.
- DBSCAN (eps = 0.0065 and 0.0080) successfully identified the dense main sequence but struggled to distinguish substructure within it. Small changes in the density threshold also produced substantially different clusters in the giants region.
- GMM (n = 5) produced the most detailed separation and revealed structure within the main sequence that was not captured by the other methods. Although its Gaussian assumptions do not perfectly match the complex structure of an HR diagram, GMM provided the most astronomically informative results of the three methods tested.

Overall, GMM performed best for this dataset, providing a more detailed representation of stellar structure than K-Means or DBSCAN. However, the results were influenced by the sample size, data quality, HR diagram construction, and assumptions of each clustering method.

Figures and visualizations can be found in the `Diagrams/` directory.

## Future Work

Future work could improve and extend the analysis by:

- Increasing the sample size to include a larger and more representative population of Gaia DR3 stars.
- Testing additional clustering methods, such as hierarchical clustering, spectral clustering, and advanced density-based approaches.
- Exploring different data-quality thresholds to assess the effects of measurement uncertainties and data selection on the resulting clusters.
- Improving the HR diagram representation to better capture less densely populated regions, such as white dwarfs and the giant branch.

***

## Authors

**[Elisa Liang]**

Women in Mathematics Directed Research Program (S26) — [University of Waterloo]

***

## Acknowledgements

[This research project was supervised by mentors Téa Fazio and Gaia Noseworthy]
Project was performed in reference to work by [Amelia Robles Delgaro](https://github.com/Ameliarbls/gaia-hr-diagram) and [Rohan Paul](https://github.com/rohanpauldev/hr-diagram-clustering-gaia-dr3)


