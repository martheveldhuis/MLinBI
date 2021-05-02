# MLBio
**Paper Notes**

_\*10 minutes per group per week presentation_

**Jargon:**

** Three phases of CML:** Chronic, Accelerated, and Blast (in increasing order of severity)

**Blast Crisis:** A stage in leukaemia when 30% cells in blood/bone marrow are blast cells (abnormal cells which multiply rapidly)

**Hematopoiesis:** the process through which the body manufactures blood cells.

**RPKM:** Is a unit of normalized transcript expression (Reads per Kilobase of Transcript per Million mapped reads); RPKM >= 1 means that gene is expressed in that cell.

**CML-SC:** Leukemic Stem Cells

**MMR:** Major Molecular Response - a patient achieving an MMR or not is captured in the variable "Responder_Status" in the metadata

**HSC:** Normal Stem Cells (Hematopoietic Stem Cells)

**K562:** A type of immortal Leukemic cell line

**CP-CML:** Chronic phase CML

**NOTES**

1. Dis-regulated hematopoesis occurs through extrinsic disruption of normal HSC as well as proliferation of internal leukemic SCs.

2. Identifying the BCR-ABL fusion gene is the only reliable way to identify CML-SCs. Hence, need a sensitive enough method for that

3. The protocol mentioned in the paper, BCL-ABL tSS2, has been asserted to be a valid method to differentiate BCR-ABL+ stem-cells from BCR-ABL- ones.

4. Along with tSS2, unbiased whole-transcriptome analysis is performed on the same single cell

5. &quot;Using the top 245 differentially expressed genes, BCR-ABL+ SCs cluster differently from BCR-ABL- SCs&quot;

6. CML-SCs are selectively resistant to TKI therapy and therefore persist in patients, resulting in a relapse post treatment discontinuation.

7. CML-SCs show the same surface phenotypes as their normal counterpart SCs

8. BUT, non-clonal BCR-ABL- SC-populations are also involved (according to the paper) in the CML disease phenotype.
 
9. &quot; Chronic-phase CML (CP-CML) is propagated by rare CML-SCs that are selectively resistant to TKI therapy and incompletely eradicated in most patients&quot;


**QUESTIONS**

**Why sequence single-cells?**

Tumour mass can be genetically very heterogeneous.

So, not all cells will react to the treatment similarly.

Potentially, all cells will need to be studied individually and then build a bigger picture from bottom up.

**What are good/bad responders and the genes which mark these two different patient-type?**

**Did the CML-SCs emerge as a result of the treatment or were they present to begin with?** 
This question is important because it determines the course of treatment

**TOOLS EXPLORED IN R**

1. DESeq2 (works only on counts data)

2. DEVis for visualisations (implemented code to enable visualisations but need counts data for it)

3. DESingle (works on RPKM but too long runtime ~12 hours for our dataset; maybe we come back to this later once we've identified appropriate ideas to group cell populations)

**EXTRACTED OBJECTIVES**

1. Can we visualise the point #5 in notes using the gene expression data and 'BCR_ABL_Status' variable in the metadata? 

2. What is the correct interpretation of different variables in the metadata? More specifically, how do we interpret “Stage_1” and “Stage_2” variables?

3. Why is predicting the TKI response of SCs useful?

4. Develop a methodology to characterise quiescent CML-SCs which persist during TKI therapy.

5. Can we identify “clues” (in terms of gene expression) pointing towards propagation of Chronic Phase to Blast Crisis (read section “Analysis of CML-SC heterogeneity during blast crisis”)?

6. Should/can we eliminate batch effects?


**CONCLUSIONS DRAWN**

1. All patient IDs starting with NB are all healthy donors. Hence, their gene expression data should serve as a reference for what does the gene activity of healthy cells look like.
 
**FEEDBACK**

1. Does the data cluster NATURALLY in some way?


You need question for differential equation (for making comparison). So for now, don't focus on this (there is information about this as well in the book). 

Instead, start from the bottom up:

1. Cluster using the gene expression data. Find meta datavariables that are responsible for that.

2. Plot scatterplots to find correlations between variables (so we can use SPLOM here too). Pick variables based on the results of the clustering. Try to find the largest source of variation (PCA/tSNE), maybe for later.

3. Formulate some questions from this information.


