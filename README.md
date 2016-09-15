# RClue_Ensemble
###Ensemble Clustering using R Clue pkg

####Abstract
Ensemble clustering has not been explored as exhaustively as ensemble classification. This project investigates whether ensemble clustering’s use of parallel soft partitioning methods can improve upon single iterations of certain base clustering algorithms. Appropriate (single) algorithms must be found before attempting to use ensemble clustering. Otherwise, the results can be misleading when comparing the internal cluster quality indices. Our results do show that the BagClust1 consensus criterion with multiple bootstrap replicates of PAM partitioning can refine results of singular PAM partitioning on the same data with the same k clusters, and that the results can be validated by internal quality metrics as well as by external validation via visualization (maps) and application of domain knowledge.

####Data: Sources and Pre-Processing
Our dataset is comprised of over 90 attributes for 1,980 geographical tracts in the Chicago area, compiled from the US Census Bureau for the years 2000 and 2013.  The attributes contain socioeconomic data including demographics, housing tenure, household income, housing costs, education, population density, age of housing, and housing density.
The dataset was split into two subsets of features, one for 2013, and one for ‘Change Over Time’ from 2000 to 2013.
We also use synthetic data, the Cassini dataset, to understand and compare algorithms. The Cassini dataset has two features and three classes, which form two non-convex, banana-shaped clusters curving around a circular cluster between them.

####Motivation and Problem
Initial clustering analyses using k-medoids algorithms and two-step (distance + hierarchical) methods revealed that about k=8 clusters were optimal for both feature subsets.  Boxplots and ANOVA tests for the strongest variables were combined with colored-by-cluster geographical maps to check and visualize these results.  
However, in a PAM partitioning of the data with 8 clusters, 10-20% of the observations have silhouette widths that suggest they are not well-clustered.  The average silhouette width with k=8 is only 0.041, and when we tally up the number of observations with negative silhouette widths of -0.500 to -0.0400, 20% of our dataset is affected.  This seems incorrect based on domain knowledge of the diversity of Chicagoland. 

####Goal
Using multiple cluster ensemble algorithms and cluster consensus methods, we will investigate whether using ensembles with algorithms besides PAM can match or beat the performance of the single and ensemble PAM partition. We will also check if ensemble clustering with PAM suggests a different optimal k clusters, and whether we can improve on the previous partitioning with ensemble clustering. Finally, we will investigate clustering quality validation indices besides silhouette width and external (geographical mapping) validation, in order to better assess the results of our ensemble clustering partitions against our existing single cluster partitions. 
