## Annotate Ensembl ids with gene symbols

You may have your gene expression data in form of a table with one column with Ensemble IDs (such as ENSG00000164850), as shown below. However, these are not very useful when you are interested in knowing which genes are differentially modulated. So, one can annotate the data using the gene symbols using the following commands. Note that this will require the R packages: **annotables** and **tidyverse**. The following example considers the gene expression data as a tab delimited text file.

### Get the requisite libraries
```
library(annotables)
library(tidyverse) 
```

### Read and view the data 
```
raw_countdata <- read.table(file.choose(), header=TRUE, sep="\t")
View(raw_countdata)
```
The first column in "raw_countdata" contains the Ensembl ids and the column header is "Geneid". The other columns are expression data for samples. Change the header from "Geneid" to "ensemble"
```
names(raw_countdata)[1] = "ensgene"
```
The annotables package contains a data frame which contains the annotations for each Ensemble ids based on the human genome build 38. If you want you can view that data frame with
```
View(grch38)
```
Now we can merge our raw count data table with the desired colmns from the grch38 file such that the Ensemble ids are matched. In the following command we are choosing to include teh **symbol** and **description** corresponding to the Ensembl ids. This can be done with the following commands
```
annot_raw_countdata <- left_join(x=raw_countdata, y=grch38[,c("ensgene","symbol","description")], by="ensgene")
```
