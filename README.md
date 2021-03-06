# MRInstruments

This is an R package that contains a number of data files from various sources to provide instruments in two sample MR. To install this package use:

```r
devtools::install_github("MRCIEU/MRInstruments")
library(MRInstruments) 
```

For more information about performing two sample MR see [https://github.com/MRCIEU/TwoSampleMR](https://github.com/MRCIEU/TwoSampleMR)

## Contents

- `aries_mqtl`: [https://scmv-ieugit.epi.bris.ac.uk/gh13047/aries_mqtl_catalog](https://scmv-ieugit.epi.bris.ac.uk/gh13047/aries_mqtl_catalog)
- `drug_interactions`: [https://scmv-ieugit.epi.bris.ac.uk/gh13047/gtex_data](https://scmv-ieugit.epi.bris.ac.uk/gh13047/gtex_data)
- `gene_trials`: [https://scmv-ieugit.epi.bris.ac.uk/gh13047/gtex_data](https://scmv-ieugit.epi.bris.ac.uk/gh13047/gtex_data)
- `gtex_eqtl`: [https://scmv-ieugit.epi.bris.ac.uk/gh13047/gtex_data](https://scmv-ieugit.epi.bris.ac.uk/gh13047/gtex_data)
- `gwas_catalog`: [https://scmv-ieugit.epi.bris.ac.uk/gh13047/gwas_catalog_standardisation](https://scmv-ieugit.epi.bris.ac.uk/gh13047/gwas_catalog_standardisation)
- `proteomic_qtls`: [https://scmv-ieugit.epi.bris.ac.uk/gh13047/proteomic_qtls](https://scmv-ieugit.epi.bris.ac.uk/gh13047/proteomic_qtls)
- `metab_qtls`: [https://scmv-ieugit.epi.bris.ac.uk/gh13047/metabolomic_qtls](https://scmv-ieugit.epi.bris.ac.uk/gh13047/metabolomic_qtls)


## Maintenance

To add a dataset copy to `/data` as a `.RData` file, and create a corresponding `.R` file in `/R` to enter the documentation for the data. For example, the GTEx data set is documented like this in the `R/eqtl_mrbase.R` file:

```r
#' Data frame of eQTLs from GTEx study
#'
#' A total of 273700 Gene expression - SNP associations from 27094 gene names and 44 tissues. Obtained from \url{http://www.gtexportal.org/home/}.
#' These data only include associations that GTEx labelled as \code{is_choson_snp}.
#' Where available, genes that are used as drug targets are annotated
#' The drug information comes from PMID 26121088
#'
#' @format A data frame with 273700 rows and 16 columns
#'  \describe{
#'  \item{gene_name}{Gene name}
#'  \item{tissue}{Tissue}
#'  \item{gene_start}{Gene chromosome : gene start position (b37)}
#'  \item{SNP}{SNP rs ID}
#'  \item{snp_position}{SNP chromosome : SNP position (b37)}
#'  \item{effect_allele}{Effect allele}
#'  \item{other_allele}{Non effect allele}
#'  \item{beta}{Effect size}
#'  \item{se}{Standard error}
#'  \item{P_value}{p-value}
#'  \item{n}{samplesize}
#'  \item{drug_proxy}{Binary value for whether used as drug proxy}
#'  \item{MeSH1}{MeSH term 1}
#'  \item{MeSH2}{Top MeSH term}
#'  \item{drug_phase}{Phase of drug development}
#'  \item{approved}{Approved in EU or US}
#'  }
#'
#' @source \url{https://scmv-ieugit.epi.bris.ac.uk/gh13047/gtex_data}
eqtl_mrbase
```

Please try to follow this convention for naming columns:

```
phenotype_col="Phenotype"
snp_col="SNP"
beta_col="beta"
se_col="se"
eaf_col="eaf"
effect_allele_col="effect_allele"
other_allele_col="other_allele"
pval_col="pval"
units_col="units"
ncase_col="ncase"
ncontrol_col="ncontrol"
samplesize_col="samplesize"
gene_col="gene"
```
