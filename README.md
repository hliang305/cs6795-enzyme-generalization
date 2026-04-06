## cs6795-enzyme-generalization
Computational study of generalization in cognitive systems using methyltransferase sequence classification (CS6795 project)
## Overview
This project investigates how the structure of training experience affects generalization in a computational learning system. Using methyltransferase protein sequences as a testbed, the project compares a **narrow training condition** and a **diverse training condition** to examine how different experience distributions shape classification performance.

From a cognitive science perspective:
- training data = **experience**
- sequence features = **representations**
- model design = **inductive bias**
- test performance = **generalization**

The system uses protein sequence fragments, k-mer frequency features, and a Random Forest classifier to predict enzyme family labels.

## What the code does
The code:
1. Loads a FASTA-like text file containing methyltransferase protein sequences
2. Converts sequence names into enzyme family labels
3. Splits each protein sequence into overlapping fragments
4. Extracts k-mer frequency features from sequence fragments
5. Trains and evaluates two models:
   - **Diverse condition**: trained on all enzyme families
   - **Narrow condition**: trained on a subset of enzyme families
6. Reports classification accuracy and per-class precision, recall, F1-score, and support
7. Generates a bar plot comparing narrow vs. diverse training performance

## Files
- `CS6795_DB.txt` — input dataset of methyltransferase protein sequences
- `CS6795_code.ipynb` — Colab/Jupyter notebook containing the full workflow
- `CS6795_code.py` — Python script version of the workflow
- `CS6795_P2.pdf` — final report
- `README.md` — project description and running instructions

## Input format
The dataset should be a FASTA-like text file where:
- each sequence name starts with `>`
- the following lines contain the amino acid sequence

Example:
>Example_001
MTEYKLVVVGAGGVGKSALTIQLIQNHFV...

## Output
The program outputs:
- number of sequences and fragments
- family label counts
- diverse condition accuracy
- narrow condition accuracy
- classification reports for both conditions
- a bar chart comparing narrow vs. diverse accuracy

## Cognitive Science Relevance
This project treats biological sequence learning as a computational model of category learning and generalization. It examines how broader or narrower experience affects the flexibility of learned representations, connecting the experiment to core cognitive science concepts such as representation, learning, inductive bias, and transfer.

## How to run

### Option 1: Google Colab
1. Open `cs6795_model.ipynb` in Google Colab
2. Upload the dataset file when prompted, or manually upload `CS6795_DB.txt`
3. Update the `file_path` variable if needed
4. Run all cells in order
5. Review the printed metrics and generated figure

### Option 2: Local Python
1. Install Python 3.10+ or later
2. Place CS6795_DB.txt in the same folder as the script
3. Run: python cs6795_model.py
