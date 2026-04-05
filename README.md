# *Staphylococcus aureus* CCG-UNAM genome retrieval

A reproducible Python workflow to retrieve *Staphylococcus aureus* genome assemblies
loaded by the Centro de Ciencias Genómicas (CCG-UNAM) from NCBI GenBank.

## Overview

This repository contains a Jupyter notebook that:

- Downloads the NCBI GenBank `assembly_summary.txt` for all bacterial genomes
- Filters records for *S. aureus*
- Identifies assemblies submitted by CCG-UNAM based on institutional keywords
- Downloads and decompresses the matching genome FASTA files
- Saves a filtered metadata table for reproducibility

## Repository structure

```
ncbi-ccg-unam-s-aureus-retrieval/
├── notebooks/
│   └── s_aureus_ccg_unam_retrieval.ipynb
├── output/                        # created automatically at runtime
│   ├── data/
│   │   ├── assembly_summary.txt
│   │   └── ccg_unam_metadata.tsv
│   └── genomes/
│       └── *.fna
├── README.md
└── requirements.txt
```

## Requirements

- Python 3.9 or higher
- Jupyter Notebook or JupyterLab

Install dependencies with:

```bash
pip install -r requirements.txt
```

## Usage

1. Clone this repository:

```bash
git clone https://github.com/<your-username>/ncbi-ccg-unam-s-aureus-retrieval.git
cd ncbi-ccg-unam-s-aureus-retrieval
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open and run the notebook:

```bash
jupyter notebook notebooks/s_aureus_ccg_unam_retrieval.ipynb
```

Run all cells from top to bottom. No additional configuration is required.

## Runtime and storage estimates

| Step | Estimated time | Disk space |
|---|---|---|
| Download `assembly_summary.txt` | 5–15 min | ~1 GB |
| Filter metadata | < 1 min | negligible |
| Download 108 genomes | 20–60 min | ~300 MB |

Times will vary depending on your internet connection and NCBI server load.

## Output files

- `output/data/assembly_summary.txt` — full NCBI GenBank bacterial assembly summary (not committed to the repository due to size)
- `output/data/ccg_unam_metadata.tsv` — filtered metadata for the 108 CCG-UNAM assemblies
- `output/genomes/*.fna` — decompressed genome FASTA files (not committed to the repository due to size)

## Reproducibility notes

- Results reflect the state of NCBI GenBank at the time of download. Re-running the workflow at a later date may return additional assemblies if new records have been deposited.
- The `assembly_summary.txt` file is only downloaded once. Delete it manually if you want to force a fresh download.
- The notebook uses `requests` for all downloads, so no FTP client is needed.

## Author

Hayde Saracho
