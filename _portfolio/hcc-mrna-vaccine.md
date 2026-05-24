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
  teaser: /images/hcc-vaccine/3d-structure.png
---

## Overview

Hepatocellular carcinoma (HCC) is the most common primary liver cancer (~90% of cases) and the second leading cause of cancer-related mortality worldwide. In Ghana, it is the leading cause of cancer deaths, with over 3,700 new cases annually. Current systemic therapies offer limited survival benefit in advanced disease, underscoring the urgent need for novel targeted approaches (Llovet et al., 2021).

This project used computational methods to design a **safe, stable, and highly immunogenic multi-epitope mRNA vaccine** targeting two overexpressed tumour-associated antigens: ***CDC25C***, a phosphatase driving G2/M cell cycle progression (Chan et al., 2012), and 
***AURKA*** (Aurora Kinase A), a mitotic regulator associated with chromosomal instability and poor prognosis in HCC (Chen et al., 2017).

**Collaborators:** Helena Okyere, Ophelia Duodu  
**Supervisor:** Professor Luke Achenie

---

## Pipeline

| Step | Analysis | Tools |
|------|----------|-------|
| 1 | Transcriptomic validation of TAAs (TCGA-LIHC RNA-Seq) | TCGAbiolinks, DESeq2, clusterProfiler |
| 2 | Epitope prediction (CTL, HTL, BCL) | NetMHCpan, NetMHCIIpan 4.1, BepiPred-2.0, ElliPro |
| 3 | Vaccine construct assembly (6 constructs) | Manual + linker/adjuvant selection |
| 4 | Physicochemical characterisation | ExPASy ProtParam, Protein-Sol |
| 5 | 3D modelling, refinement & validation | AlphaFold2, GalaxyRefine, PROCHECK, ProSA-web |
| 6 | Molecular docking (vaccine–TLR2) | ClusPro |
| 7 | Normal mode analysis | iMODs |
| 8 | Molecular dynamics simulations | CHARMM-GUI, GROMACS |
| 9 | In silico immune simulation | C-ImmSim |
| 10 | Codon optimisation & in silico cloning | GenScript, SnapGene |

---

## Key Results

### Epitope Selection

Stringent multi-step screening including antigenicity (VaxiJen v2.0), allergenicity (AllerTOP v2.0), toxicity (ToxinPred), and immunogenicity (IEDB T cell immunogenicity predictor), yielded **16 CTL epitopes** from *CDC25C*, **13 CTL epitopes** from *AURKA*, **2 HTL epitopes** from *AURKA*, and **2 B-cell epitopes**, collectively covering a broad range of HLA-A, HLA-B, and HLA-DR alleles with relevance to diverse global populations.

---

### Vaccine Construct Design and Selection

Six multi-epitope vaccine constructs were assembled by systematically concatenating selected epitopes with adjuvants (P30 from tetanus toxin, large ribosomal subunit protein bL12) and linkers (EAAAK, GPGPG, AAY, KK, GGGGS) in varied arrangements. All six constructs were 
submitted to GalaxyRefine for 3D refinement. **Vaccine 6, Model 1** was selected as the candidate on the basis of the lowest RMSD (0.575 Å), highest GDT-HA (0.8908), best MolProbity score (1.017), lowest clash score (2.4), and 98.3% Ramachandran-favoured residues.

![3D structure of the candidate vaccine construct](/images/hcc-vaccine/3d-structure.png)

*3D representation of the candidate vaccine (Vaccine 6, Model 1) with components colour-coded: P30 adjuvant, bL12 adjuvant, MHC-I epitopes, MHC-II epitopes, B-cell epitopes, and linker sequences.*

---

### Structural Validation and Physicochemical Stability

The secondary structure, predicted by PSIPRED, is predominantly helical with interspersed 
coils and strands. The candidate vaccine comprises 600 amino acids (MW 65,979.14 Da, pI 5.45) 
and is physicochemically stable (instability index 37.32, aliphatic index 80.63). 
Structural validation confirmed stereochemical quality, with 97.1% of residues in the 
Ramachandran most-favoured region and a ProSA z-score of −1.56, consistent with experimentally 
resolved native proteins of comparable size. The mRNA secondary structure minimum free energy 
was −967.20 kcal/mol, supporting production stability.

![Secondary structure of the vaccine construct](/images/hcc-vaccine/secondary-structure.png)
*Secondary structure of the candidate vaccine predicted by PSIPRED, showing predominant helical regions (pink), coils (grey), and strands (yellow).*

![Secondary structure of the vaccine construct](/images/hcc-vaccine/mrna-secondary-structure.png)
*The secondary structure of the vaccine's mRNA sequence was predicted using the RNAfold web server. (A) The centroid secondary structure with a minimum free energy of -673.66 kcal/mol (B) The minimum free energy structure of the mRNA vaccine with stability for production at -967.20 kcal/mol.*

![Structural validation: Ramachandran plot and ProSA z-score](/images/hcc-vaccine/ramachandran-prosa.png)
*(A) Ramachandran plot showing 97.1% of residues in the most-favoured region and only 0.4% in disallowed regions. (B) ProSA z-score plot with the candidate vaccine (dark spot, z = −1.56) falling within the range of native proteins resolved by NMR and X-ray crystallography.*

---

### Molecular Docking (Vaccine–TLR2 Complex)

The candidate vaccine was docked against TLR2 (PDB: 6NIG) using the ClusPro webserver. The optimal complex (Cluster 1, 34 members) achieved a lowest binding energy of **−1,258.9 kcal/mol**, indicating strong, energetically favourable interaction with the 
immune receptor. Normal mode analysis with iMODs confirmed the structural flexibility and deformability profile of the complex is consistent with a stable, functional binding conformation.

![Vaccine–TLR2 docked complex](/images/hcc-vaccine/docking-complex.png)

*3D model of the candidate vaccine–TLR2 docked complex. The vaccine construct and TLR2 receptor are shown in distinct colours, highlighting the binding interface.*

![Normal mode analysis of the vaccine–TLR2 complex](/images/hcc-vaccine/normal-mode-analysis.png)
*Normal mode analysis (iMODs) of the vaccine–TLR2 complex showing (A) deformability plot, 
(B) eigenvalue plot, (C) variance plot , (D) B-factor plot*

---

### Molecular Dynamics Simulations

Coarse-grained molecular dynamics (CG-MD) simulations were performed using CHARMM-GUI 
to evaluate the conformational stability and dynamic behaviour of both the apo vaccine 
construct and the vaccine–TLR2 complex. Simulations were conducted at **10, 100, and 200 ns** 
to capture short-, intermediate-, and long-timescale dynamics. Trajectory analysis including 
RMSD, RMSF, and radius of gyration is underway for comparative assessment of the 
unbound and bound systems.

![Molecular dynamics simulation trajectories](/images/hcc-vaccine/md-simulation.png)
*Apo vaccine coarse-grained MD analysis: system at 100 ns*

![Molecular dynamics simulation trajectories](/images/hcc-vaccine/rmsd-mrna-apo.png)
*RMSD of apo mRNA over MD simulation time. Black: 0–10 ns; red: 0–70 ns*

![Molecular dynamics simulation trajectories](/images/hcc-vaccine/structure-apo-vac-tp.png)
*Conformations of the vaccine–TLR2 complex sampled during a 10 ns MD simulation. Snapshots shown at 0.5, 1.0, 1.5, 3.0, 5.0, and 10.0 ns.*

---

### In Silico Immune Simulation

C-ImmSim modelling with three vaccine doses administered at 28-day intervals predicted a 
robust and physiologically consistent immune response. The simulation showed elevated IgG 
and IgM antibody titres following booster doses, strong CD8⁺ cytotoxic T lymphocyte 
activation, CD4⁺ T-helper cell expansion, and a cytokine and interleukin profile — 
including IL-2 and IFN-γ — consistent with a pro-inflammatory, anti-tumour immune response.

![In silico immune simulation results](/images/hcc-vaccine/immune-simulation.png)
*Simulated immune response to the candidate vaccine (C-ImmSim, 3 doses at 28-day intervals) 
showing (A) antigen levels and immunoglobulin titres, (B) B lymphocyte populations, 
(C) CD4⁺ T-helper lymphocyte counts, (D) CD8⁺ cytotoxic T lymphocyte counts, 
(E) macrophage activity, and (F) cytokine and interleukin concentrations.*

---

## Analysis Notebooks

Full reproducible computational analyses for this project:

- 📊 [Step 1 — Transcriptomic Validation of *CDC25C* and *AURKA* (TCGA-LIHC)](/files/analyses/HCC_TAA_Validation.html)

*Further notebooks for epitope prediction and downstream steps will be added.*

---

## References

Chan, T. H. M., Chen, L., Liu, M., Hu, L., Zheng, B., Poon, V. K.-M., Huang, P., Yuan, Y.-F., 
Huang, J., Yang, J., Tsao, G. S., & Guan, X.-Y. (2012). Translationally controlled tumor 
protein induces mitotic defects and chromosome missegregation in hepatocellular carcinoma 
development. *Hepatology*, *55*(2), 491–505. https://doi.org/10.1002/hep.24709

Chen, C., Song, G., Xiang, J., Zhang, H., Zhao, S., & Zhan, Y. (2017). AURKA promotes 
cancer metastasis by regulating epithelial-mesenchymal transition and cancer stem cell 
properties in hepatocellular carcinoma. *Biochemical and Biophysical Research 
Communications*, *486*(2), 514–520. https://doi.org/10.1016/j.bbrc.2017.03.075

Llovet, J. M., Kelley, R. K., Villanueva, A., Singal, A. G., Pikarsky, E., Roayaie, S., 
Lencioni, R., Koike, K., Zucman-Rossi, J., & Finn, R. S. (2021). Hepatocellular carcinoma. 
*Nature Reviews Disease Primers*, *7*(1), 6. https://doi.org/10.1038/s41572-020-00240-3

---

## Status

✅ In silico pipeline complete | 📝 Manuscript in preparation
