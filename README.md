# Bioinformatic Workflows for Clinical Oncology

**Pediatric CNS tumor classification from RNA-seq expression profiles.**
UCSD Carter Lab · Israni Biomedical Facility · Summer 2025

[![Poster](docs/poster_thumbnail.png)](docs/poster.pdf)

---

## Overview

This project analyzes **1,791 RNA-seq samples** from pediatric central nervous system (CNS) brain tumors and builds a machine learning classifier to support diagnostic decision-making. The work was conducted at UCSD's Department of Genomics and Precision Medicine under PI Hannah Carter, Ph.D., and mentor Timothy J. Sears (Ph.D. Candidate).

### Tumor Subtypes Studied
- **HGG** — High-Grade Glioma (111 samples)
- **LGG** — Low-Grade Glioma (125 samples)
- **MB** — Medulloblastoma (98 samples)
- **Healthy controls** — 270 cortex (HGG/LGG comparisons), 241 cerebellum (MB comparisons), from the GTEx portal

---

## Key Results

- **Random Forest classifier achieved 82.1% accuracy** in distinguishing HGG, LGG, and Medulloblastoma on a held-out test set, outperforming Logistic Regression and SVC baselines.
- Classified a challenging external case (the "Rady case") as **High-Grade Glioma (HGG)** with the lowest z-score distance among all tumor types — demonstrating clinical applicability beyond the training cohort.
- Identified statistically significant **downregulation of tumor suppressors** (TP53, SUFU, PTEN, CDKN2A, CDKN2B, BRCA2) and **HLA-class I antigen presentation genes** (HLA-A, HLA-B, HLA-C, HLA-DQA1, HLA-DPB1, HLA-DPA1), consistent with immune evasion mechanisms in pediatric tumors.
- Detected **PDGFRA overexpression in gliomas** and **MYC elevation in HGG**, recovering known pediatric oncogene patterns.

---

## Methods

- **Data**: RNA-seq expression in TPM (Transcripts Per Million); preprocessed in Python/JupyterLab.
- **Statistical analysis**: Mann–Whitney U tests for tumor-vs-control comparisons; z-score analysis for external sample classification.
- **Machine learning**: Random Forest classifier with feature selection over curated gene panels (tumor suppressors, oncogenes, HLA genes, antigen-presentation pathway).
- **Evaluation**: Confusion matrix on held-out test set; per-class precision and recall.

---

## Repository Structure

```
.
├── GeneExpression_Cancer_vs_Normal_GTEx.ipynb   # Tumor vs. healthy comparisons
├── Rady_GeneGroups_Boxplots.ipynb               # External "Rady case" analysis
├── classification_model.ipynb                   # Random Forest classifier (main result)
├── convert_ENSG_to_Symbol.ipynb                 # Gene ID mapping
├── separate_types_of_cancer.ipynb               # Cohort splitting and labeling
└── docs/
    └── poster.pdf                               # Research poster (UCSD symposium)
```

---

## Future Directions

- Refining pediatric-specific transcriptomic references (the current pipeline uses adult GTEx as control, which is a known limitation).
- Expanding gene panels to include **KIAA1549-BRAF fusions, TERT, MET, MYB, FOXR1**, and additional immune-evasion markers.
- Subtype-level classification within HGG/LGG using deep learning approaches.

---

## Acknowledgments

- **PI**: Hannah Carter, Ph.D. — UCSD Department of Genomics and Precision Medicine
- **Mentor**: Timothy J. Sears, Ph.D. Candidate — Carter Lab
- **Co-author**: Alexandra Villalpando Solórzano
- Special thanks to Olivia A. Graeve, Ph.D., and the Universidad Autónoma de Baja California, Fundación UABC, A.C., Jacinto Licea y Enlace for institutional support.

---

## Citation / Contact

If you'd like to discuss this work:
- Alberto Montero Molina — [LinkedIn](https://www.linkedin.com/in/alberto-montero-412b3a249/) · [Portfolio](https://albertomontero.vercel.app)
