# Continuous Bayesian Variant Interpretation Accounts for Incomplete Penetrance among Mendelian Cardiac Channelopathies

Providing quantitative estimates of disease probability given the presence of a variant in a disease-associated gene is a major challenge in contemporary genetics. We elaborate a method to construct continuous estimates of Long QT Syndrome Type 1 for all single nucleotide variants in KCNQ1.
This method relies on observations of affected and unaffected heterozygotes from literature reports, population databases of putatively healthy controls, and detailed phenotyping from international arrhythmia genetics centers.
Our approach supplements heterozygote observations with variant-specific features: functional data from channel electrophysiology, structural parameters obtained from cryo-EM, and various 'in silico' predictors of variant pathogenicity. 
We integrate these lines of evidence using a Bayesian approach and expectation-maximization. 
Crucially, this approach explicitly acknowledges incompleete penetrance in providing a probability of disease given the variant and a defined uncertainty associated with that estimate. A severe limitation of current variant-interpretation strategies is the inconsistency of categorical descriptions, where Pathogenic variants may variably affect heterozygotes, and LQTS may nevertheless manifest in Benign variant heterozygotes. 

We complete this analysis using 3 RMDs described below and found in the 'RMDs and Scripts' folder. Knitted implementation of the code is available in html format. 

bayes_kcnq1_data_process.Rmd - Bayes KCNQ1 Data Process – these scripts merge the cohort data with the curated literature data and provide counts of affected LQT1 heterozygotes and total heterozygotes for each variant. The clinical heterozygote data is found in the 'Heterozygote Data' folder, and the protein covariates are found in the 'Covariates' folder. Functional, in silico, and structural data are combined in a separate dataframe for all variants that could arise from a single nucleotide substitution (not permitting all amino acids at each position). These dataframes are then combined and used in the subsequent scripts.

bayes_kcnq1_model_application.Rmd - Bayes KCNQ1 Model Evaluation – these scripts implement the prior and posterior probability derivations described in Supplemental Methods I. The significance of each covariate is calculated using Spearman and Pearson correlations. To assess the robustness of the method, we implemented 10-fold cross validation for Spearman, Pearson, and Brier scores as described in Supplemental Methods. 

bayes_kcnq1_model_evaluation.Rmd - Bayes KCNQ1 Model Application – these scripts construct the model and derive prior and posterior probabilities as described above. We then use scripts to generate the prior and posterior penetrance histograms, conduct analyses of variant penetrance with ClinVar annotations, export the penetrance data that is superimposed on structure, and make forest plots of prior and posterior probabilities for all variants. Details are available in the Supplemental Methods.  


A manuscript describing the results obtained from these investigations has been deposited at medRxiv: https://www.medrxiv.org/content/10.1101/2022.07.07.22277385v1
