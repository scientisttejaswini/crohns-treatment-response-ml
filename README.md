# Machine Learning-Based Prediction of Treatment Response in Crohn's Disease

### A Computational Genomics and Precision Medicine Research Project

## Overview

Crohn's disease is a chronic inflammatory bowel disease characterised by considerable variation in disease progression and treatment response.

Infliximab, an anti-TNF biological therapy, is commonly used to treat Crohn's disease. However, not all patients respond to treatment.

This project investigates whether baseline blood transcriptomic profiles can help identify molecular signatures associated with response to infliximab.

Using publicly available gene-expression datasets, statistical analysis, machine learning and pathway enrichment, this project explores molecular differences between treatment responders and non-responders and evaluates the reproducibility of selected findings in an independent cohort.

## Research Question

Can baseline blood transcriptomic profiles help identify molecular signatures associated with infliximab treatment response in Crohn's disease?

## Research Objectives

- Investigate gene-expression patterns associated with infliximab treatment response.
- Perform transcriptomic data preprocessing and exploratory data analysis.
- Identify informative genes using statistical and machine learning-based feature selection.
- Develop and compare predictive machine learning models.
- Evaluate model performance using stratified cross-validation.
- Investigate biological pathways associated with selected genes.
- Assess the reproducibility of candidate gene-expression patterns using an independent dataset.

## Computational Workflow

1. Public dataset collection and selection.
2. Data preprocessing and quality assessment.
3. Exploratory data analysis (EDA).
4. Differential gene-expression analysis.
5. Feature selection.
6. Machine learning model development.
7. Model evaluation and comparison.
8. Biological interpretation and pathway enrichment.
9. Independent cohort validation.

## Datasets

### Discovery Dataset – GSE107865

- Source: NCBI Gene Expression Omnibus (GEO).
- 22 Crohn's disease patients.
- Baseline blood gene-expression profiles collected before infliximab treatment.
- 17 responders and 5 non-responders.
- Treatment response assessed at week 14.
- Platform: GPL23159 (Affymetrix Clariom S Human).

### Independent Validation Dataset – GSE42296

- Source: NCBI Gene Expression Omnibus (GEO).
- 20 baseline Crohn's disease samples selected for validation.
- 14 responders and 6 non-responders.
- Platform: GPL6244 (Affymetrix Human Gene 1.0 ST Array).

The validation dataset was used to assess whether candidate genes showed consistent expression directions across independent cohorts.

## Key Results

### Differential Gene Expression

Differential expression analysis identified candidate genes associated with differences between responders and non-responders.

RELT was the only gene among the top-ranked results with an adjusted p-value below 0.05.

### Feature Selection

Twenty candidate genes were selected using SelectKBest with an ANOVA F-test.

Genes identified across the statistical and feature-selection analyses included RELT, SOD2, DMWD and ZNF619.

### Machine Learning Model Comparison

Three machine learning algorithms were evaluated using five-fold stratified cross-validation.

 Model                Accuracy          Balanced Accuracy           ROC-AUC 
 Logistic Regression   0.76                     0.57                    0.45 
 Random Forest          0.67                     0.51                   0.53 
 SVM                    0.76                     0.57                   0.73 

SVM achieved the highest ROC-AUC among the evaluated models. However, confusion matrix analysis showed that the model struggled to identify non-responders.

### Biological Pathway Enrichment

Pathway enrichment analysis identified significant enrichment of:

## TNF-alpha Signaling via NF-κB

- Adjusted p-value: 0.0163
- Contributing genes: NINJ1, DENND5A and SOD2.

This finding provides an interesting biological connection to inflammatory signalling and anti-TNF treatment in Crohn's disease.

### Independent Validation

Candidate gene-expression patterns were compared between the discovery and independent validation cohorts.

- 18 candidate genes were available for comparison.
- 11 of 18 genes (61.1%) showed consistent expression directions across both datasets.
- The comparison provides exploratory evidence of reproducible gene-expression patterns.

## Visual Results

Key visualisations generated during the analysis include:

- Gene-expression distribution and quality-control plots.
- Differential gene-expression analysis.
- Machine learning model comparison.
- Random Forest feature importance.
- Biological pathway enrichment.
- Independent validation heatmap.

## Tools and Technologies

- Programming: Python
- Data analysis: Pandas, NumPy
- Statistical analysis: SciPy, Statsmodels
- Machine learning: Scikit-learn
- Visualisation: Matplotlib, Seaborn
- Pathway enrichment: GSEApy, Enrichr
- Data source: NCBI Gene Expression Omnibus (GEO)



## Research Background

This independent project is scientifically inspired by research into the genetic and molecular mechanisms underlying inflammatory bowel disease, including publications co-authored by Professor Jeffrey C. Barrett.

## Related publication:

Huang et al. (2017). Fine-mapping inflammatory bowel disease loci to single-variant resolution. Nature.

DOI: https://doi.org/10.1038/nature22969

## Conclusion

This project identified preliminary gene-expression patterns associated with infliximab treatment response in Crohn's disease.

The analysis highlighted candidate genes, identified enrichment of a TNF-alpha/NF-κB-related pathway and found that 11 of 18 candidate genes showed consistent expression directions in an independent cohort.

These findings suggest that baseline transcriptomic profiles may contain biologically relevant information associated with treatment response. However, the small sample sizes and limited identification of non-responders by the machine learning models mean that further validation using larger independent cohorts is necessary.

## Project Status

Completed – Exploratory Computational Analysis and Independent Gene-Level Validation.

## Limitations

- The discovery cohort included only 22 patients, with 5 non-responders.
- The independent validation cohort included 20 baseline Crohn's disease samples.
- Different microarray platforms were used across the two datasets.
- Independent validation assessed gene-expression direction, not predictive model performance.
- The findings are exploratory and require validation in larger cohorts.

## Disclaimer

This is an independent computational research project using publicly available datasets. The findings are exploratory and are not intended for clinical decision-making.