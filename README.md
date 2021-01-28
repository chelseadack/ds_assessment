# Ash tree susceptibility to Chalara ash dieback.

By analysing the relationship between disease susceptibility and gene expression levels in the common ash tree, it could be possible to identify which genes give rise to tolerance to Chalara ash dieback. This can be achieved by performing differential gene expression analysis of RNA-sequencing data. PCA and t-SNE can be used to help clarify trends and a tree's susceptibility to the disease can be predicted from its gene expression levels using a LDA model.

--------------- REQUIRED PACKAGES ---------------

Some packages are required in order to run this report, these can be installed by running the following code :
```{r}
#Install bioconductor manager
chooseCRANmirror(ind=51)
install.packages("BiocManager")
#Install DEseq2 package from Bioconductor (required for differential expression analysis)
BiocManager::install("DESeq2")
#Instal apeglm package from Bioconductor (required for log fold-change shrinkage)
BiocManager::install("apeglm")
```
The output of sessionInfo() can be found in [sessioninfo.md]("sessioninfo.md").

--------------- DATA SETS ---------------

The sample data used in this report consists of RNA-Seq data and trait data - these can be found in the data-raw file. Other data sets can be used providing they are in the same format of :

expression (RNA-Seq) data
- columns named "Ash0" where 0 is the tree number
- rows labelled with gene name

trait data
- column 1 named "tree" containing identities for trees sampled in the form "Ash0" where 0 is the tree number
- column 2 named "chalara" containing the tree's trait eg. "Susceptible" or "Tolerant"

N.B. data used must have fewer than 1000 tree samples but the code can be modified to process more. The code can also be modified for differential expression analysis of other diseases other than Chalara ash dieback.
