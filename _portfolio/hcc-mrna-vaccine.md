---
title: "Integrative Cancer Genomics Approach to Design and Characterize a Multi-Epitope mRNA Vaccine Against Hepatocellular Carcinoma"
excerpt: "A complete immunoinformatics pipeline targeting *CDC25C* and *AURKA* as tumour-associated antigens in HCC — from transcriptomic validation through molecular docking and immune simulation."
collection: portfolio
date: 2026-05-01
tags:
  - Immunoinformatics
  - mRNA vaccine
  - Hepatocellular carcinoma
  - Bioinformatics
  - Molecular docking
header:
  teaser: /images/hcc-vaccine-teaser.png   # add a figure from your paper later
---

## Overview

Hepatocellular carcinoma (HCC) is the common primary liver cancer (~90% of cases) and the second leading cause of cancer-related mortality worldwide. In Ghana, it is the leading cause of cancer deaths, with over 3,700 new cases annually. Current systemic therapies 
offer limited survival benefit in advanced disease, underscoring the urgent need for novel targeted approaches (Llovet et al., 2021).

This project used computational methods to design a **safe, stable, and highly immunogenic multi-epitope mRNA vaccine** targeting two overexpressed tumour-associated antigens: ***CDC25C***, a phosphatase driving G2/M cell cycle progression (Chan et al., 2012) and ***AURKA*** (Aurora Kinase A), a mitotic regulator associated with chromosomal instability and poor prognosis in HCC (Chen et. al., 2017).

**Collaborators:** Helena Okyere, Ophelia Duodu  
**Supervisor:** Professor Luke Achenie

---

## Pipeline

| Step | Analysis | Tools |
|------|----------|-------|
| 1 | Transcriptomic validation of TAAs (TCGA-LIHC RNA-Seq) | TCGAbiolinks, DESeq2, clusterProfiler |
| 2 | Epitope prediction (CTL, HTL, BCL) | NetMHCpan 4.1, IEDB, BepiPred-2.0, ElliPro |
| 3 | Vaccine construct assembly (6 constructs) | Manual + linker/adjuvant selection |
| 4 | Physicochemical characterisation | ExPASy ProtParam, Protein-Sol |
| 5 | 3D modelling, refinement & validation | AlphaFold2, GalaxyRefine, PROCHECK, ProSA-web |
| 6 | Molecular docking (vaccine–TLR2) | ClusPro |
| 7 | Normal mode analysis | iMODs |
| 8 | Molecular dynamics simulations | GROMACS |
| 9 | In silico immune simulation | C-ImmSim |
| 10 | Codon optimisation & in silico cloning | GenScript, SnapGene |

---

## Key Results

**Epitope selection:** Stringent screening (antigenicity, allergenicity, toxicity, 
immunogenicity) yielded 16 CTL epitopes from *CDC25C*, 13 from *AURKA*, 2 HTL epitopes from 
*AURKA*, and 2 B-cell epitopes — covering a broad range of HLA alleles relevant to 
diverse populations.

**Construct selection:** Six vaccine constructs were assembled and refined. **Vaccine 6, 
Model 1** was selected as the candidate based on the lowest RMSD (0.575), highest GDT-HA 
(0.8908), best MolProbity score (1.017), and 98.3% Ramachandran-favoured residues.

**Structural stability:** The candidate vaccine (600 amino acids, MW 65,979 Da) was 
stable (instability index 37.32), with a z-score of −1.56 within the range of native 
proteins. mRNA secondary structure minimum free energy: −967.20 kcal/mol.

**Molecular docking:** Docking against TLR2 (PDB: 6NIG) using ClusPro produced a 
favourable complex with lowest binding energy of **−1,258.9 kcal/mol** (Cluster 1, 
34 members), indicating strong, stable interaction with the immune receptor.

**Molecular dynamics simulations:** Coarse-grained molecular dynamics simulations of the apo vaccine and vaccine–TLR2 complex were performed at 10, 100, and 200 ns. Comparative trajectory analysis throughout the simulation window, with RMSD, RMSF, and Rg profiles are underway.

**Immune simulation:** C-ImmSim modelling (3 doses, 28-day intervals) predicted robust 
humoral and cellular responses: elevated IgG and IgM titres, CD8+ CTL activation, 
CD4+ T-helper expansion, and a cytokine profile consistent with a pro-inflammatory 
anti-tumour response.

---

## References

Chan, T. H. M., Chen, L., Liu, M., Hu, L., Zheng, B., Poon, V. K.-M., Huang, P., Yuan, Y.-F., Huang, J., Yang, J., Tsao, G. S., & Guan, X.-Y. (2012). Translationally controlled tumor protein induces mitotic defects and chromosome missegregation in hepatocellular carcinoma development. Hepatology, 55(2), 491–505. https://doi.org/10.1002/hep.24709

Chen, C., Song, G., Xiang, J., Zhang, H., Zhao, S., & Zhan, Y. (2017). AURKA promotes cancer metastasis by regulating epithelial-mesenchymal transition and cancer stem cell properties in hepatocellular carcinoma. Biochemical and Biophysical Research Communications, 486(2), 514–520. https://doi.org/10.1016/j.bbrc.2017.03.075

Llovet, J. M., Kelley, R. K., Villanueva, A., Singal, A. G., Pikarsky, E., Roayaie, S., Lencioni, R., Koike, K., Zucman-Rossi, J., & Finn, R. S. (2021). Hepatocellular carcinoma. Nature Reviews Disease Primers, 7(1), 6. https://doi.org/10.1038/s41572-020-00240-3

---

## Analysis Notebooks

Full reproducible computational analyses for this project:

- 📊 [Step 1 — Transcriptomic Validation of CDC25C and AURKA (TCGA-LIHC)](/files/analyses/HCC_TAA_Validation.html)

*Further notebooks for epitope prediction and downstream steps will be added.*

---

## Status

✅ In silico pipeline complete | 📝 Manuscript in preparation
