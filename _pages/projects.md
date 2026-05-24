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
<summary><strong>Approach & Tools</strong></summary>
<br>
Whole exome sequencing data was processed through a multi-stage bioinformatics workflow beginning with quality assessment and adapter trimming using FastQC and Trimmomatic, followed by alignment to the GRCh38 reference genome with the Sentieon framework. Variant calling was performed using Sentieon's DNAscope, with downstream VCF normalization and processing conducted in bcftools.

For rare variant prioritization, I used filtered out common variants using population frequencies from gnomAD v4.0, the 1000 Genomes Project, and the African Genome Variation Database to retain variants enriched in underrepresented populations. Functional annotation was achieved with Ensembl VEP v115. The pathogenicity interpretation integrated multiple in silico prediction frameworks, including AlphaMissense, REVEL, CADD, ClinPred, and SpliceAI. Variants were cross-referenced against ClinVar, LOVD, DECIPHER, OMIM, and cBioPortal to assess prior disease associations and clinical relevance.

Current downstream analyses include ACMG-guided variant classification, structural protein modelling using HOPE and GROMACS, and regulatory variant interpretation through RegulomeDB, 3DSNP, and AlphaGenome. To place candidate variants within broader biological networks, I also perform protein interaction and pathway enrichment analyses using STRING, Cytoscape, Reactome, and clusterProfiler, alongside single-cell expression mapping across craniofacial developmental and cancer-related datasets using CancerSCEM 2.0, CZ CELLxGENE, and CanCellVar.
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
<summary><strong>Approach & Tools</strong></summary>
<br>
I defined TAM subtypes using the 18-subtype canonical framework described by <a href="https://doi.org/10.1016/j.heliyon.2024.e28332">Rakina et al. (<em>Heliyon</em>, 2024)</a>. Single-cell signatures from TISCH2 allowed me to apply this classification across five solid tumour types (breast, colon, lung, ovarian, and melanoma). I curated ferroptosis gene programmes from FerrDb V2/V3 and MSigDB, covering canonical drivers and suppressors. I manually curated regulatory axes involving <em>GPX4</em>, <em>ACSL4</em>, iron metabolism, and <em>p53</em>/<em>NRF2</em> signalling.
     
I deconvoluted bulk transcriptomes using CIBERSORTx with my custom 18‑subtype signature matrix. TIMER2.0 served as orthogonal validation to confirm robustness. Ferroptosis pathway activity and TAM consensus signatures were quantified using ssGSEA (GSVA package) across TCGA STAR FPKM‑UQ datasets.
     
To evaluate clinical significance, I performed prognostic modelling combining univariate Cox screening with LASSO Cox regression (glmnet). External validation was conducted across independent GEO cohorts: GSE25066, GSE39582, GSE73731, GSE109211, and GSE72094. I predicted drug sensitivity to ferroptosis‑targeting compounds (RSL3, Erastin, Sorafenib) using oncoPredict and GDSC2. For immunogenomic characterization, I applied TIDE to model immune exclusion and profiled immune checkpoint gene expression.
<br><br>
<strong>Key tools:</strong> GSVA · CIBERSORTx · TIMER2.0 · TISCH2 · FerrDb · glmnet (LASSO Cox) · oncoPredict/GDSC2 · TIDE · ComplexHeatmap · survminer · R (tidyverse, survival, TCGAbiolinks)
</details>

---

### Multi-Omic Characterization of Oxeiptosis Pathway Alterations in TCGA Pan-Cancer Cohorts: Immune Microenvironment Remodeling, Survival Implications, and Vaccine Candidacy {#oxeiptosis}
*Independent Study · Structured for peer-review submission*

<!-- <img src="/images/oxeiptosis.png" alt="Oxeiptosis project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Oxidative stress is a reactive oxygen species-dependent cell death pathway regulated by *AIFM2*, *PGAM5*, and *KEAP1*, genes frequently altered in cancer. Although these alterations are well documented at the genomic level, their effects on the tumour immune microenvironment remain largely unexplored.

In this project, I analysed approximately 2,055 patients across four TCGA cancer cohorts to investigate whether alterations in the oxeiptosis pathway are associated with changes in tumour immune composition, immune activity, and immunotherapy response. I am also exploring whether recurrent *KEAP1* hotspot mutations generate neoantigens that could serve as targets for therapeutic cancer vaccines. Preliminary findings suggest altered macrophage and regulatory T cell infiltration patterns in affected lung adenocarcinomas, as well as broader immune subtype shifts in both lung and breast cancers.

<details>
<summary><strong>Approach & Tools</strong></summary>
<br>
I derived a binary alteration status, oxi_status, marking tumours with any somatic mutation or copy number alteration in core oxeiptosis regulators (<em>AIFM2</em>, <em>PGAM5</em>, <em>KEAP1</em>). I then extended this set to include pathway‑associated genes such as <em>NFE2L2</em>, <em>RIPK3</em>, <em>CASP8</em>, <em>HMOX1</em>, <em>GPX4</em>, using MC3 masked MAF files and GISTIC2 scores.

For genomic characterization, I estimated tumour mutational burden with maftools. Mutational signature decomposition (deconstructSigs) prioritized SBS4, SBS7, SBS18, and SBS36 because of their known links to oxidative stress and inflammation. Co‑mutation patterns were visualised using oncoprints. Immune cell composition was quantified with CIBERSORTx (absolute mode), TIMER2.0, and IOBR v2.2.0. Pan‑cancer immune subtypes were assigned following the framework of <a href="https://doi.org/10.1016/j.immuni.2018.03.023">Thorsson et al. (<em>Immunity</em>, 2018)</a>.

I performed differential expression analysis using DESeq2 with apeglm shrinkage, followed by a random‑effects meta‑analysis across four cohorts (metafor), encompassing 26,344 genes. Survival analysis integrated multivariable Cox regression with mixed‑effects pan‑cancer Cox models (coxme). Predictive performance was evaluated using time‑dependent ROC analysis. Immunotherapy response prediction incorporated both TIDE and ImmunoPhenoScore. In parallel, I am predicting neoantigens derived from recurrent <em>KEAP1</em> hotspot mutations (G333C, R320Q, R272C) using pVACtools and pVACseq, to assess immunogenicity in patient cohorts.
<br><br>
<strong>Key tools:</strong> DESeq2 · maftools · deconstructSigs · CIBERSORTx · IOBR · TIMER2.0 · metafor · coxme · timeROC · TIDE · ImmunoPhenoScore · pVACtools · R (TCGAbiolinks, clusterProfiler, survminer)
</details>

---

### Integrative Cancer Genomics Approach to Design and Characterize a Multi-Epitope mRNA Vaccine Against Hepatocellular Carcinoma {#hcc-vaccine}
*Independent Investigator, KNUST · Completed*

<!-- <img src="/images/hcc-vaccine.png" alt="HCC vaccine project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Hepatocellular carcinoma (HCC) is one of the leading causes of cancer related mortality worldwide, and therapeutic options for advanced disease are limited. This project assessed the feasibility of a multi epitope mRNA vaccine targeting overexpressed oncogenic drivers in HCC.

Using transcriptomic analyses of TCGA liver cancer datasets and single-cell validation approaches, I identified *CDC25C* and *AURKA* as candidate targets for vaccine development. I then designed and characterized a multi-epitope mRNA vaccine construct using structural modelling, molecular dynamics simulation, and computational immune simulation. The analyses predicted robust immune activation and sustained immunological responses, supporting computationally guided therapeutic vaccine design as a promising strategy in cancer research.

<details>
<summary><strong>Approach & Tools</strong></summary>
<br>
I validated <em>CDC25C</em> and <em>AURKA</em> as candidate oncogenic targets through differential expression analysis of TCGA‑LIHC (DESeq2). The findings were corroborated at single‑cell resolution using TISCH2 datasets. I predicted MHC class I and II epitopes using IEDB tools, then screened the candidates for antigenicity (VaxiJen), allergenicity (AllerTop), and toxicity (ToxinPred) to select only safe, immunogenic epitopes.

I modelled the multi‑epitope vaccine construct with AlphaFold2 and refined the structure using GalaxyRefine to correct steric clashes and improve side‑chain packing. To assess structural stability and receptor interaction dynamics, I performed molecular dynamics simulations of the vaccine–TLR2 complex in GROMACS over 100 ns, with trajectory analyses using the MDAnalysis Python package.

I simulated immune responses using C‑IMMSIM, quantifying antibody titres, T cell activation kinetics, and the generation of long‑term immune memory. For translational feasibility, I performed in silico cloning and codon optimisation using SnapGene and GenScript.
<br><br>
<strong>Key tools:</strong> DESeq2 · TISCH2 · IEDB · VaxiJen · AllerTop · ToxinPred · AlphaFold2 · GalaxyRefine · MDAnalysis · C-IMMSIM · SnapGene · GenScript
</details>

<br><br>
  📊 <a href="/portfolio/hcc-mrna-vaccine/"><strong>View full results, figures & analysis notebooks →</strong></a>
</details>

---

### Multi-Epitope Subunit Vaccine Against Lymphatic Filariasis {#lf-vaccine}
*Undergraduate Dissertation · KNUST · Advisor: Dr. Alexander Kwarteng · Manuscript in preparation*

<!-- <img src="/images/lf-vaccine.png" alt="Lymphatic filariasis vaccine project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Lymphatic filariasis, caused by Wuchereria bancrofti, affects millions of people globally yet lacks a licensed vaccine. My undergraduate dissertation identified and designed a potential vaccine candidate against the parasite using immunoinformatics approaches.

The project targeted the Ig-like domain-containing protein from the parasite proteome and used epitope prediction tools to design a multi-epitope subunit vaccine that elicits CD4⁺ T cell, CD8⁺ T cell, and B cell responses. Molecular docking analyses predicted interaction with the innate immune receptor TLR4, while in silico immune simulations suggested sustained antibody production and immune memory formation.

<details>
<summary><strong>Approach & Tools</strong></summary>
<br>
I mapped B cell epitopes with Bepipred 2.0 and T cell epitopes with NetMHCpan (MHC class I) and NetMHCIIpan (MHC class II) to identify regions critical for antibody recognition and T cell receptor activation. I predicted secondary structure with PSIPRED. For tertiary structure, I modelled the vaccine construct using AlphaFold2 to enable subsequent docking with TLR4.
     
I docked the vaccine construct against TLR4 using ClusPro, then analysed and visualised binding interfaces (hydrogen bonds, hydrophobic contacts) in PyMol. I used C‑IMMSIM to simulate immune outcomes, predicting antibody titres, cytokine profiles (IL‑2, IFN‑γ), and the persistence of memory cells after antigen exposure.
<br><br>
<strong>Key tools:</strong> IEDB · PSIPRED · ClusPro · PyMol ·  C-IMMSIM 
</details>

---

### Genetic Variant Annotation for Craniosynostosis and Mandibuloacral Dysplasia {#variant-annotation}
*Teaching and Research Assistant · HuGene Lab, KNUST · Supervisor: Dr. Lord J.J. Gowans · Completed*

<!-- <img src="/images/variant-annotation.png" alt="Variant annotation project"
     style="float:right; width:310px; margin:0 0 15px 25px; border-radius:6px;"> -->

Rare craniofacial and skeletal disorders are often caused by highly penetrant pathogenic variants. However, interpreting these variants in African populations is difficult because African genomic data remain underrepresented in reference databases.

As part of my work at HuGene Lab, I contributed to the genetic characterisation of Ghanaian patients with craniosynostosis and mandibuloacral dysplasia through systematic variant annotation and prioritisation. This work identified a recurrent pathogenic variant in the LMNA gene in a Ghanaian multiplex family affected by mandibuloacral dysplasia. The project demonstrated the value of genomic medicine in rare disease diagnosis and the importance of expanding genetic studies within African populations.

<details>
<summary><strong>Approach & Tools</strong></summary>
<br>
I first annotated variants with Ensembl VEP, then used GeneCards and VarElect to prioritise genes based on disease relevance and functional evidence. Pathogenicity was assessed using SIFT, PolyPhen2, AlphaMissense, and ClinPred, requiring consensus from at least three tools. I filtered against gnomAD to retain only rare variants (MAF < 0.01). ClinVar annotations were used to flag previously reported pathogenic variants.

I modelled the structural impact of prioritized variants using HOPE. To place them in a broader biological context, I built protein interaction networks (STRING) and cross‑referenced disease associations (OMIM), specifically to identify whether candidate genes form known disease‑relevant clusters (e.g., craniosynostosis or skeletal dysplasia pathways) and to assess their clinical validity.
<br><br>
<strong>Key tools:</strong> Ensembl VEP · GeneCards · VarElect · SIFT · PolyPhen2 · AlphaMissense · ClinPred · ClinVar · gnomAD · HOPE · STRING · OMIM
</details>


---

*[Back to Research themes](/research/)*
