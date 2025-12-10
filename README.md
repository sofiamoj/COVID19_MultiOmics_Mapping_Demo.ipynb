# COVID-19 Multi-Omics Mapping Using pyMultiOmics

This repository contains a complete demonstration of **multi-omics integration, biological entity mapping, and network construction** using the `pyMultiOmics` framework. The analysis is based on the proteomics and metabolomics dataset described in:

**Shen et al., “Proteomic and Metabolomic Characterization of COVID-19 Patient Sera”, Cell (2020)**

The notebook showcases how multi-omics data can be combined into a unified structure, mapped onto Reactome biological pathways, and queried for system-level relationships between proteins, metabolites, reactions, and pathways.

---

## Project Objectives

This repository demonstrates how to:

* Integrate proteomics and metabolomics datasets into a **MultiOmicsData** container
* Use **Reactome knowledgebase mapping** to connect genes, proteins, compounds, reactions, and pathways
* Construct a large-scale multi-omics network representing biological interactions in COVID-19 serum samples
* Perform targeted network queries for biological interpretation
* Reproduce a practical systems biology workflow suitable for research, teaching, and further development

This project is particularly relevant for applications in computational biology, translational systems medicine, and multi-omics data science.

---

## Dataset Summary

The analysis uses processed data from Shen et al. (Cell, 2020), including:

**Proteomics**

* 791 quantified proteins
* 70 patient samples
* Matrix of log-transformed abundance values
* Design file containing sample metadata

**Metabolomics**

* 220 quantified metabolites
* 96 patient samples
* Matrix of processed compound intensities
* Corresponding design metadata

The dataset consists of severe, non-severe, and control COVID-19 patient serum samples, enabling multi-omics comparisons relevant to disease severity.

---

## Workflow Overview

The notebook (`Covid_19_Mapping.ipynb`) follows a structured computational workflow:

### 1. Environment Initialization

* Jupyter autoreload for dynamic development
* Standard scientific Python stack (`pandas`, `numpy`, `matplotlib`)
* Importing key modules from `pyMultiOmics`

### 2. Data Acquisition and Loading

* Automatic download of processed COVID-19 dual-omics data
* Extraction and loading of proteomics and metabolomics matrices
* Inspection of data frames and metadata tables

### 3. Constructing Omics Data Containers

* Creation of `SingleOmicsData` objects for both modalities
* Integration into a unified `MultiOmicsData` container
* Embedding publication metadata

### 4. Reactome-Based Mapping

A `Mapper` object is used to generate a multi-layer biological network by linking:

* Gene → Protein
* Protein → Reaction
* Compound → Reaction
* Reaction → Pathway

Final network:

* **19,645 nodes**
* **80,442 edges**
* Node types include genes, proteins, compounds, reactions, and pathways

### 5. Network Querying

The notebook demonstrates example queries such as:

* Listing reactions connected to observed proteins and compounds
* Retrieving all entities linked to a specific reaction (e.g., `R-HSA-194153`)
* Querying proteins connected to specific compounds
* Exploring cross-modality relationships mediated through shared reactions

---

## Repository Structure

```
covid19_multiomics_mapping/
│
├── Covid_19_Mapping.ipynb        # Main multi-omics mapping notebook
├── README.md                     # Project documentation
└── requirements.txt              # Python dependencies
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/<your-username>/covid19_multiomics_mapping.git
cd covid19_multiomics_mapping
```

Install dependencies:

```bash
pip install -r requirements.txt
```

(Optional) For full Reactome mapping functionality, ensure a local Neo4j instance is running:

```
bolt://localhost:7687
```

---

## Usage

Open the notebook:

```bash
jupyter notebook Covid_19_Mapping.ipynb
```

Run all cells sequentially to:

* Load and inspect omics data
* Build an integrated multi-omics container
* Construct the Reactome mapping
* Query cross-omics interactions

---

## Key Insights

This notebook highlights several important principles in multi-omics analysis:

* **Multi-layer mapping improves biological interpretation** by connecting isolated omics features through known pathways.
* **Reactome knowledge graphs enable cross-modality relationships**, such as protein–metabolite links through shared reactions.
* **Large-scale network construction** provides a foundation for downstream tasks such as enrichment analysis, subnetwork extraction, and hypothesis generation.

This workflow can be adapted to other biological or clinical datasets beyond COVID-19.

---

## Requirements

```
pandas
numpy
matplotlib
pyMultiOmics
```

---

## Citation

If you use or extend this work, please cite:

Shen, Bo, et al. *Proteomic and metabolomic characterization of COVID-19 patient sera.*
Cell 182.1 (2020): 59–72.

---

## About This Project

This repository serves as a structured and transparent example of multi-omics network construction using `pyMultiOmics`. It is intended for:

* Students learning systems biology
* Researchers working with multi-omics datasets
* Developers constructing reproducible computational biology pipelines
* Applicants showcasing advanced data science + bioinformatics skills


