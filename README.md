# GraphOmics-HCC

## Biologically Informed Graph Neural Networks for Multi-Cohort Hepatocellular Carcinoma Classification

**GraphOmics-HCC** is a biologically informed deep-learning framework for hepatocellular carcinoma (HCC) classification from transcriptomic data. The framework integrates multi-cohort gene-expression profiles with prior biological knowledge from the **STRING protein-protein interaction network** and **MSigDB canonical pathways**.

The project is designed for reproducible cancer transcriptomics research and includes preprocessing, graph construction, graph neural network training, conventional machine-learning baselines, ablation studies, external validation, explainability analysis, pathway interpretation, exploratory survival analysis, and publication-ready visualization.

---

# Overview

GraphOmics-HCC combines:

- Multi-cohort transcriptomic datasets
- Protein-protein interaction information
- Biological pathway knowledge
- Graph neural networks
- Cross-validation
- Independent external validation
- Model calibration
- Explainable AI
- Survival analysis
- Publication-quality visualization

The central idea is to represent genes as nodes in a biologically constrained graph rather than treating every gene as an independent feature.

Gene-gene relationships are obtained from STRING, while gene-to-pathway relationships are obtained from MSigDB.

The resulting architecture is intended to provide both predictive performance and biologically structured interpretation.

---

# Study Design

The project currently uses:

## Development cohort

- TCGA-LIHC

## External validation cohorts

- GSE14520
- GSE25097
- GSE36376
- GSE76427
- GSE64041

After preprocessing and quality control, the final harmonized dataset contains approximately:

- **2,002 samples**
- **13,084 genes**
- **6 independent cohorts**

The exact number of samples may depend on quality-control filters and exclusion criteria.

---

# Graph Construction

The biological graph integrates two major knowledge sources.

## STRING

Protein-protein interactions are obtained from:

**STRING v12.0**

The primary graph uses high-confidence interactions with:

```text
Combined STRING score ≥ 700

# GraphOmics-HCC

<p align="center">
  <b>Biologically Informed Graph Neural Networks for Multi-Cohort Hepatocellular Carcinoma Classification</b>
</p>

<p align="center">
  Multi-cohort transcriptomics • STRING PPI • MSigDB pathways • Graph Neural Networks • Explainable AI • External validation
</p>

---

## Project Status

GraphOmics-HCC is an active research software project developed for reproducible computational oncology experiments.

Current pipeline status:

| Component | Status |
|---|---|
| Multi-cohort data collection | ✅ Completed |
| Transcriptomic preprocessing | ✅ Completed |
| Cross-platform harmonization | ✅ Completed |
| STRING graph construction | ✅ Completed |
| MSigDB pathway integration | ✅ Completed |
| GraphOmics-HCC training | ✅ Completed |
| Five-fold cross-validation | ✅ Completed |
| External validation | ✅ Completed |
| Conventional ML baselines | ✅ Completed |
| Ablation analysis | ✅ Completed |
| Integrated Gradients | ✅ Completed |
| Pathway interpretation | ✅ Completed |
| Explainability sanity checks | ✅ Completed |
| Exploratory survival analysis | ✅ Completed |
| Publication figures | ✅ Completed |
| Prospective clinical validation | ⏳ Future work |

---

# Highlights

GraphOmics-HCC provides an end-to-end framework for integrating transcriptomic data with prior biological knowledge.

### Key capabilities

- Multi-cohort HCC transcriptomic analysis
- TCGA and GEO integration
- Cross-platform sample harmonization
- STRING-based protein-protein interaction graph
- MSigDB pathway-constrained pooling
- Graph neural network classification
- Nested development validation
- Independent external validation
- Probability calibration
- Conventional machine-learning benchmarks
- Architecture ablation studies
- Integrated Gradients
- pathway-level interpretation
- SHAP-based pathway analysis
- explainability randomization tests
- exploratory survival analysis
- automatic publication-quality figures
- publication-ready result tables

---

# Why GraphOmics-HCC?

Most conventional transcriptomic classifiers treat genes as independent numerical variables.

GraphOmics-HCC instead introduces biological structure into the learning process.

A gene does not operate independently inside a cell. Genes interact through signaling cascades, protein complexes, metabolic systems, and regulatory pathways.

GraphOmics-HCC therefore integrates:

```text
Gene expression
      +
STRING protein interactions
      +
MSigDB pathway membership
      ↓
Biologically constrained graph model
      ↓
HCC classification

**Conceptual Architecture**

                    MULTI-COHORT TRANSCRIPTOMICS
                              │
                ┌─────────────┴─────────────┐
                │                           │
             TCGA-LIHC                  GEO cohorts
                │                           │
                └─────────────┬─────────────┘
                              │
                              ▼
                    QUALITY CONTROL
                              │
                              ▼
                  GENE HARMONIZATION
                              │
                              ▼
               RANK-NORMALIZED EXPRESSION
                              │
                              ▼
              ┌─────────────────────────┐
              │ Gene-level input tensor │
              │ Expression + Coverage   │
              └────────────┬────────────┘
                           │
                           ▼
               STRING-constrained graph
                           │
                           ▼
                    Graph convolution
                           │
                           ▼
                Learned gene embeddings
                           │
                           ▼
                 MSigDB pathway pooling
                           │
                           ▼
               Pathway-level representation
                           │
                           ▼
                    Classification head
                           │
                           ▼
                  HCC probability score
                           │
           ┌───────────────┼────────────────┐
           │               │                │
           ▼               ▼                ▼
     External         Explainability      Survival
     validation        analysis           analysis
