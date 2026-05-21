---
title: "Projects"
permalink: /projects/
author_profile: true
---

The projects below represent the main studies through which I explore my broader research interests in cancer genomics, immunology, human genetics, and computational biology, interests I describe in more detail on the [Research](/research/) page.

---

### Shared Genetic Architecture Between Syndromic Orofacial Clefts and Cancer Susceptibility {#clefts-cancer}
*MPhil Thesis · Human Genetics and Genomics Lab (HuGene Lab), KNUST · Supervisor: Dr. Lord J.J. Gowans*

<!-- <img src="/images/wes-clefts.png" alt="WES clefts project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Syndromic orofacial clefts arise from disruptions in craniofacial development, often caused by pathogenic variants in regulatory genes involved in human development and cellular homeostasis. Several of these genes have also been implicated in hereditary cancer susceptibility, suggesting a biological overlap between developmental disorders and cancer predisposition.

My MPhil research investigates this connection using whole-exome sequencing in a Ghanaian cohort. The project aims to determine whether individuals with syndromic orofacial clefts carry rare germline variants in known cancer predisposition genes and whether shared genetic mechanisms underlie these apparently distinct conditions. Beyond its biological significance, the work has potential implications for cancer risk surveillance and genetic counselling in affected families. The study is ongoing.

<details>
<summary><strong>Technical Approach</strong></summary>
<br>
Whole exome sequencing data is processed through a multi-stage bioinformatics pipeline: quality control and adapter trimming (FastQC, Trimmomatic), alignment to GRCh38 (Sentieon), variant calling (DNAscope), and VCF normalization (bcftools). Rare variant filtering uses population frequency thresholds against gnomAD v4.0, 1000 Genomes, and the African Genome Variation Database. Functional annotation is performed with Ensembl VEP v115, and pathogenicity is assessed using 11 in silico prediction tools including AlphaMissense, REVEL, CADD, ClinPred, and SpliceAI, with clinical cross-referencing against ClinVar, LOVD, DECIPHER, OMIM, and cBioPortal. Ongoing work includes ACMG variant classification, structural protein modelling (HOPE, GROMACS), regulatory variant interpretation (RegulomeDB, 3DSNP, AlphaGenome), protein interaction and pathway enrichment analysis (STRING, Cytoscape, Reactome, clusterProfiler), and single-cell expression mapping across craniofacial and cancer contexts (CancerSCEM 2.0, CZ CELLxGENE, CanCellVar).
<br><br>
<strong>Key tools:</strong> Sentieon · DNAscope · Ensembl VEP v115 · AlphaMissense · REVEL · CADD · ClinPred · SpliceAI · gnomAD · GROMACS · STRING · clusterProfiler · Reactome
</details>

---

### Ferroptosis Regulatory Programs in Tumour-Associated Macrophage Subtypes Across Pan-Cancer {#ferroptosis-tam}
*Independent Study · Structured for peer-review submission*

<!-- <img src="/images/ferroptosis-tam.png" alt="Ferroptosis TAM project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Ferroptosis, an iron-dependent form of regulated cell death, is an important regulator of tumour biology and anti-tumour immunity. Tumour-associated macrophages (TAMs) are the most heterogeneous and influential immune cell populations within the tumour microenvironment. Despite growing interest in both fields, how ferroptosis-related programs shape TAM biology across cancers remains poorly understood.

This project investigates how ferroptosis driver and suppressor pathways are distributed across transcriptionally distinct TAM subtypes in multiple cancer types, including breast, colorectal, kidney, liver, and non-small cell lung cancer. The project aims to determine whether these regulatory programs influence patient outcomes or reveal targetable therapeutic vulnerabilities. The single-cell TAM signature extraction and ferroptosis gene set construction phases are complete, and downstream analyses are ongoing.

<details>
<summary><strong>Technical Approach</strong></summary>
<br>
TAM subtypes are defined using the 18-subtype canonical framework (Rakina et al., <em>Heliyon</em>, 2024), operationalized through TISCH2 single-cell RNA-seq signatures across all five cancer types. Ferroptosis gene sets (12 total) are curated from FerrDb V2/V3 and MSigDB, covering driver and suppressor programs and manually defined axes (GPX4, ACSL4, iron metabolism, p53/NRF2). Bulk TAM deconvolution uses CIBERSORTx with custom 18-subtype signature matrices, with TIMER2.0 for cross-validation. ssGSEA scoring of ferroptosis programmes and TAM consensus signatures is performed with the GSVA package across TCGA STAR FPKM-UQ expression matrices. Prognostic modelling uses univariate Cox pre-selection followed by LASSO Cox regression (glmnet) per cancer type, validated in independent GEO cohorts (GSE25066, GSE39582, GSE73731, GSE109211, GSE72094). Drug sensitivity for ferroptosis-targeted agents (RSL3, Erastin, Sorafenib) is predicted via oncoPredict/GDSC2. Immunogenomic analyses include TIDE immune exclusion scoring and immune checkpoint expression profiling.
<br><br>
<strong>Key tools:</strong> GSVA · CIBERSORTx · TIMER2.0 · TISCH2 · FerrDb · glmnet (LASSO Cox) · oncoPredict/GDSC2 · TIDE · ComplexHeatmap · survminer · R (tidyverse, survival, TCGAbiolinks)
</details>

---

### Multi-Omic Characterization of Oxeiptosis Pathway Alterations in TCGA Pan-Cancer Cohorts: Immune Microenvironment Remodeling, Survival Implications, and Vaccine Candidacy {#oxeiptosis}
*Independent Study · Structured for peer-review submission*

<!-- <img src="/images/oxeiptosis.png" alt="Oxeiptosis project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Oxidative stress is a reactive oxygen species-dependent cell death pathway regulated by AIFM2, PGAM5, and KEAP1, genes frequently altered in cancer. Although these alterations are well documented at the genomic level, their effects on the tumour immune microenvironment remain largely unexplored.

In this project, I analysed approximately 2,055 patients across four TCGA cancer cohorts to investigate whether alterations in the oxeiptosis pathway are associated with changes in tumour immune composition, immune activity, and immunotherapy response. I am also exploring whether recurrent KEAP1 hotspot mutations generate neoantigens that could serve as targets for therapeutic cancer vaccines. Preliminary findings suggest altered macrophage and regulatory T cell infiltration patterns in affected lung adenocarcinomas, as well as broader immune subtype shifts in both lung and breast cancers.

<details>
<summary><strong>Technical Approach</strong></summary>
<br>
A binary alteration status variable (oxi_status) is derived from somatic mutation data (MC3 masked MAF) and GISTIC2 copy number scores for core oxeiptosis genes (AIFM2, PGAM5, KEAP1) and an extended gene set (NFE2L2, RIPK3, CASP8, HMOX1, GPX4). Genomic characterisation includes TMB computation (maftools), mutational signature decomposition targeting SBS4, SBS7, SBS18, and SBS36 (deconstructSigs), and co-mutation oncoprint analysis. Immune cell composition is quantified using CIBERSORTx (22-cell absolute mode), TIMER2.0, and IOBR v2.2.0, with pan-cancer immune subtype classification based on the Thorsson et al. (2018) framework. Differential expression analysis uses DESeq2 with apeglm LFC shrinkage, followed by random-effects meta-analysis across four cohorts using metafor (26,344 genes tested). Survival modelling combines multivariable Cox regression and pan-cancer mixed-effects Cox (coxme), with time-dependent AUC computed via timeROC. ICB response prediction integrates TIDE and ImmunoPhenoScore. A neoantigen prediction module targeting KEAP1 hotspot mutations (G333C, R320Q, R272C) using pVACtools/pVACseq is in progress.
<br><br>
<strong>Key tools:</strong> DESeq2 · maftools · deconstructSigs · CIBERSORTx · IOBR · TIMER2.0 · metafor · coxme · timeROC · TIDE · ImmunoPhenoScore · pVACtools · R (TCGAbiolinks, clusterProfiler, survminer)
</details>

---

### Integrative Cancer Genomics Approach to Design and Characterize a Multi-Epitope mRNA Vaccine Against Hepatocellular Carcinoma {#hcc-vaccine}
*Independent Investigator, KNUST · Completed*

<!-- <img src="/images/hcc-vaccine.png" alt="HCC vaccine project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Hepatocellular carcinoma (HCC) is one of the leading causes of cancer related mortality worldwide, and therapeutic options for advanced disease are limited. This project assessed the feasibility of a multi epitope mRNA vaccine targeting overexpressed oncogenic drivers in HCC.

Using transcriptomic analyses of TCGA liver cancer datasets and single-cell validation approaches, I identified CDC25C and AURKA as candidate targets for vaccine development. I then designed and characterized a multi-epitope mRNA vaccine construct using structural modelling, molecular dynamics simulation, and computational immune simulation. The analyses predicted robust immune activation and sustained immunological responses, supporting computationally guided therapeutic vaccine design as a promising strategy in cancer research.

<details>
<summary><strong>Technical Approach</strong></summary>
<br>
Oncogene targets (CDC25C, AURKA) were identified from the TCGA-LIHC dataset using DESeq2 differential expression analysis (Bioconductor, R) and validated at single-cell resolution via TISCH2. Immunogenic MHC-I and MHC-II epitopes were predicted using IEDB, with antigenicity, allergenicity, and toxicity screening via VaxiJen, AllerTop, and ToxinPred respectively. The multi-epitope vaccine peptide was structurally modelled with AlphaFold2 and refined using GalaxyRefine. Molecular dynamics simulations assessing stability and flexibility of the vaccine–TLR2 complex were run in GROMACS over 100 ns, with trajectory analysis performed using the MDAnalysis Python package. Computational immune simulation using C-IMMSIM predicted B cell antibody titers, T cell activation profiles, and long-term immunological memory. In silico cloning and codon optimisation were performed using SnapGene and GenScript.
<br><br>
<strong>Key tools:</strong> DESeq2 · TISCH2 · IEDB · VaxiJen · AllerTop · ToxinPred · AlphaFold2 · GalaxyRefine · GROMACS · MDAnalysis · C-IMMSIM · SnapGene · GenScript
</details>

---

### Multi-Epitope Subunit Vaccine Against Lymphatic Filariasis {#lf-vaccine}
*Undergraduate Dissertation · KNUST · Advisor: Dr. Alexander Kwarteng · Manuscript in preparation*

<!-- <img src="/images/lf-vaccine.png" alt="Lymphatic filariasis vaccine project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Lymphatic filariasis, caused by Wuchereria bancrofti, affects millions of people globally yet lacks a licensed vaccine. My undergraduate dissertation identified and designed a potential vaccine candidate against the parasite using immunoinformatics approaches.

The project targeted the Ig-like domain-containing protein from the parasite proteome and used epitope prediction tools to design a multi-epitope subunit vaccine that elicits CD4⁺ T cell, CD8⁺ T cell, and B cell responses. Molecular docking analyses predicted interaction with the innate immune receptor TLR4, while in silico immune simulations suggested sustained antibody production and immune memory formation.

<details>
<summary><strong>Technical Approach</strong></summary>
<br>
Comprehensive B cell and T cell epitope mapping was performed using IEDB prediction tools. The primary and secondary vaccine structure was constructed and assessed using PSIPRED, and the tertiary structure was modelled for docking studies. Protein–protein docking with TLR4 was performed using ClusPro, with binding interaction analysis in PyMol and Discovery Studio. In silico immune simulation used the C-IMMSIM webserver to quantify predicted antibody titers, cytokine production profiles, and long-term memory cell formation. In silico cloning and codon optimisation were carried out using SnapGene and GenScript.
<br><br>
<strong>Key tools:</strong> IEDB · PSIPRED · ClusPro · PyMol · Discovery Studio · C-IMMSIM · SnapGene · GenScript
</details>

---

### Genetic Variant Annotation for Craniosynostosis and Mandibuloacral Dysplasia {#variant-annotation}
*Teaching and Research Assistant · HuGene Lab, KNUST · Supervisor: Dr. Lord J.J. Gowans · Completed*

<!-- <img src="/images/variant-annotation.png" alt="Variant annotation project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Rare craniofacial and skeletal disorders are often caused by highly penetrant pathogenic variants. However, interpreting these variants in African populations is difficult because African genomic data remain underrepresented in reference databases.

As part of my work at HuGene Lab, I contributed to the genetic characterisation of Ghanaian patients with craniosynostosis and mandibuloacral dysplasia through systematic variant annotation and prioritisation. This work identified a recurrent pathogenic variant in the LMNA gene in a Ghanaian multiplex family affected by mandibuloacral dysplasia. The project demonstrated the value of genomic medicine in rare disease diagnosis and the importance of expanding genetic studies within African populations.

<details>
<summary><strong>Technical Approach</strong></summary>
<br>
Genetic variants were annotated and prioritised using Ensembl VEP, the GeneCards suite, and VarElect. Pathogenicity was assessed using SIFT, PolyPhen2, AlphaMissense, ClinPred, and ClinVar, with population frequency filtering against gnomAD. Structural consequences of candidate variants were modelled using HOPE, and protein-level effects were contextualised through STRING interaction networks and OMIM disease association data.
<br><br>
<strong>Key tools:</strong> Ensembl VEP · GeneCards · VarElect · SIFT · PolyPhen2 · AlphaMissense · ClinPred · ClinVar · gnomAD · HOPE · STRING · OMIM
</details>

---

*[Back to Research themes](/research/)*
