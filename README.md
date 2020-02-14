# epiEQTL
An R package to Identify cis-cis epistasis effects on gene expression

This package implements multiple analysis strategies for identifying cis-cis epistasis effects on gene expression for specific genes. 

To install:

install.packages("epiEQTL_1.0.tar.gz", repos=NULL, source=TRUE)

To run in R:
library(epiEQTL)

## An example
geno_file="geno_chr11_pass"
expression_file="expression_counts.csv"
covariate_file="gene_expression_covariates.txt"
subj_select="subject_select.txt"
folder = "/udd/redaq/epiRNA/newRcode/Example"
GENE = "MUC5B"
flank = 1000
design = "~Lc.Batchadapter.test+PC1+PC2+PC3+peer_factor_1+peer_factor_2+peer_factor_3"
MAC = "5"
missingRate = "0.01"
eQTLFile = "cisEQTL.txt"
plink2exe="/udd/redaq/tools/plink2"
plinkexe="/udd/redaq/tools/plink032819/plink"


results=compute_Epistasis_eQTL(plink2exe, plinkexe,geno_file, expression_file, covariate_file, subj_select, folder, GENE, flank, design, MAC, missingRate, LD_pruning = 0.7, scanThreshold = 1e-2, nperm=100, method="WaldSand") 


