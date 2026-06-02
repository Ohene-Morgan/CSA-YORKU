# CSA × York University — AI & Data Science for Materials Science Workshop

A hands-on undergraduate workshop developed in collaboration with the **Canadian Space Agency (CSA)** and **York University**. The curriculum teaches Python programming, scientific computing, machine learning, and generative AI — all applied to materials science problems.

---

## Curriculum Overview

The workshop is structured as four progressive tracks culminating in an integrated capstone exercise.

| Track | Topics | Tools |
|-------|--------|-------|
| **1 — Python Foundations** | Data types, control flow, OOP, file I/O, debugging | Base Python |
| **2 — Scientific Computing** | Arrays, DataFrames, materials featurization | NumPy, Pandas, Matminer, Pymatgen |
| **3 — Machine Learning** | Regression, classification, model evaluation | Scikit-learn |
| **4 — Generative AI** | Diffusion models, Hugging Face, Gen AI CAD grounding | Hugging Face `diffusers` |
| **Capstone** | End-to-end materials featurization pipeline | All of the above |

**Platform:** Jupyter Notebooks
**Environments:** Google Colab · Syzygy · Local Conda (see `environment.yml`)

---

## Repository Structure

```
CSA-YORKU/
├── Lab1_Python_BasicsI-1-1.ipynb          # Track 1 — Python fundamentals
├── Lab2_Python_BasicsII.ipynb             # Track 2 — NumPy, Pandas, Matminer
│
├── Linear Regression/
│   └── MECH4403_LR_2026_SV.ipynb         # Track 3 — Linear & polynomial regression
│
├── Decision Tree/
│   └── macine_failure.ipynb               # Track 3 — Decision tree classifier
│
├── Post_installation trial/
│   └── MSAI_Day1_Exercises.ipynb          # Capstone — integrated Day-1 exercise
│
├── Assignments/
│   └── A1_Python_Basics-1.ipynb           # Assignment 1 (7 tasks)
│
├── CSA_Presentation_Outline.md            # Full slide-by-slide presentation outline
├── generate_presentation.py               # Script to generate the .pptx deck
├── CSA_Workshop_Presentation.pptx         # Generated PowerPoint presentation
└── environment.yml                        # Conda environment specification
```

> **Note:** Generative AI / diffusion model materials are not fully uploaded yet.

---

## Track Details

### Track 1 — Python Foundations
Core Python for students with no assumed programming background:
- Primitive types, strings, lists, tuples, dictionaries
- Control flow: conditionals, for/while loops, `range()`
- Functions with default parameters
- Object-oriented programming: classes, `__init__`, inheritance (`super()`)
- File I/O with the `csv` module
- Debugging: identifying and fixing syntax and semantic errors

### Track 2 — Scientific Computing
The bridge between Python and materials science:
- **NumPy:** array operations, linear algebra (eigenvalues, determinants), reshaping
- **Pandas:** DataFrames, `iloc`/`loc`, `groupby`, missing-value handling, one-hot encoding
- **Matminer / Pymatgen:** converting alloy composition strings into numerical features — electronegativity, oxidation states, band center, Mendeleev numbers

### Track 3 — Machine Learning
Supervised learning on real engineering datasets:
- **Regression:** linear → polynomial (degree 2 & 3) on rotational speed vs. torque data; R², MSE
- **Classification:** Decision Tree on the AI4I2020 industrial machine failure dataset (10,000 samples); confusion matrix, classification report
- Key concept: polynomial regression as linear regression on transformed features

### Track 4 — Generative AI & Diffusion Models
Conceptual grounding for Generative AI CAD Design:
- Generative vs. discriminative models — what it means for a model to *create* rather than predict
- Diffusion model fundamentals: forward diffusion (noise addition) and reverse diffusion (learned denoising)
- **Hugging Face `diffusers`:** running pre-trained diffusion models with minimal code
- Hands-on exploration of model outputs; critical evaluation of generated results
- Foundation for applying generative AI to engineering design workflows

### Capstone — Day-1 Integrated Exercise
Students build a materials informatics pipeline from scratch:
1. Parse alloy composition strings (e.g., `Al50Cu50`, `Fe40Ni40Cr20`)
2. Compute physics-grounded features: weighted mean electronegativity, weighted variance, weighted atomic mass, Mendeleev number
3. Visualise the feature space of binary and ternary alloys
4. Train a linear regression model on hand-crafted features
5. (Stretch) Extend with Matminer's production-grade featurizers

---

## Assignment 1

Seven tasks designed to reinforce every track concept and test genuine understanding:

| Task | Concept |
|------|---------|
| 1 | CSV reading + for-loop iteration |
| 2 | Implement custom `max()` without built-ins |
| 3 | `Alloys` class + `HEAs` subclass (OOP) |
| 4 | Composition string parser — regex + element validation |
| 5 | Debug broken code |
| 6 | NHL Stanley Cup Excel analysis (cross-domain generalisation) |
| 7 | Matminer EDA + correlation-based feature pruning |

---

## Environment Setup

**Option A — Conda (recommended for local)**
```bash
conda env create -f environment.yml
conda activate msai
jupyter notebook
```

**Option B — Google Colab**
Open any notebook in Colab and run the setup cell at the top.

**Option C — Syzygy**
Log in at [syzygy.ca](https://syzygy.ca) and upload the notebook.

---

## Presentation

A CSA-facing curriculum design report is included:

- `CSA_Presentation_Outline.md` — full slide-by-slide content and speaker notes
- `CSA_Workshop_Presentation.pptx` — 16-slide PowerPoint deck (regenerate with `python generate_presentation.py`)

The presentation covers not just *what* was taught but the pedagogical rationale behind each design decision.

---

## Dependencies

Key libraries (see `environment.yml` for full pinned versions):

```
python >= 3.11
numpy
pandas
matplotlib
scikit-learn
matminer
pymatgen
diffusers        # Track 4 — Generative AI
transformers
jupyter
```
