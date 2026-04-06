# *Staphylococcus aureus* CCG-UNAM genome retrieval

A reproducible Python-based workflow to retrieve and filter *Staphylococcus aureus* genome assemblies from NCBI GenBank, focusing on sequences associated with the Centro de Ciencias Genómicas (CCG-UNAM).

## Overview

This repository provides a simple and reproducible pipeline to:

- Download the NCBI `assembly_summary.txt` database.
- Filter genome assemblies by organism (*S. aureus*).
- Select genomes linked to a specific institution (CCG-UNAM).
- Generate direct FTP links for genome download.
- Organize outputs for downstream genomic analysis.

## Why this project?

Efficient genome retrieval is a critical first step in large-scale comparative genomics, plasmid analysis, and antimicrobial resistance studies.

This pipeline ensures:

- Reproducibility.
- Transparency in filtering criteria.
- Scalability for future datasets.
- Easy integration with downstream bioinformatics workflows.

## Repository structure

```
S_aureus_genome_retrieval/
├── notebook/
│   └── s_aureus_ccg_unam_retrieval.ipynb
├── output/                        # created automatically at runtime
│   ├── data/
│   │   ├── assembly_summary.txt
│   │   └── ccg_unam_metadata.tsv
│   └── genomes/
│       └── *.fna
├── README.md
├── LICENSE
└── requirements.txt
```

## Installation

1. Clone this repository:

```bash
git clone https://github.com/HaydeSaracho/S_aureus_genome_retrieval.git
cd S_aureus_genome_retrieval/
```

2. Create environment (recommended):

```bash
conda create -n aureus_retrieval python=3.10
conda activate aureus_retrieval
pip install -r requirements.txt
```

## Usage

Run the notebook:

```bash
jupyter notebook notebooks/s_aureus_ccg_unam_retrieval.ipynb
```

The workflow will:

- Download `assembly_summary.txt`.
- Filter for *S. aureus*.
- Filter by institution (CCG-UNAM).
- Generate genome download links.

## Outputs

The pipeline generates:

- Filtered genome metadata tables.
- FTP download links.
- Structured dataset.

## Reproducibility notes

- Data source: NCBI GenBank Assembly database.
- Filtering criteria are fully documented in the notebook.
- The workflow can be adapted to other organisms or institutions.

## Author

👩‍🔬 Hayde Saracho
