# CSA × York University — AI, Data Science & Space Materials Workshop

An interdisciplinary workshop developed in collaboration with the **Canadian Space Agency (CSA)** and **York University**, open to undergraduate students across all STEM fields. The program was designed to spark interest in **space engineering**, **materials for space applications**, and **robotics**, while building practical computational skills and fostering cross-disciplinary collaboration.

Led by a computational materials scientist, the workshop brought together students from diverse backgrounds — engineering, physics, chemistry, computer science, and more — to work on real space-relevant problems.

---

## Program Goals

- Ignite student interest in space engineering and materials for extreme space environments
- Introduce computational tools used in modern materials science and engineering research
- Enable cross-disciplinary collaboration on space-relevant design challenges
- Provide grounding in AI and generative design tools with direct application to space hardware
- Connect students to the kind of work done at CSA and affiliated research institutions

---

## Curriculum Overview

The workshop covered four computational tracks alongside hands-on technical activities, all framed around space and robotics applications.

| Track / Activity | Topics | Tools |
|------------------|--------|-------|
| **1 — Python Foundations** | Data types, control flow, OOP, file I/O, debugging | Base Python |
| **2 — Scientific Computing** | Arrays, DataFrames, materials featurization | NumPy, Pandas, Matminer, Pymatgen |
| **3 — Machine Learning** | Regression, classification, model evaluation | Scikit-learn |
| **4 — Generative AI** | Diffusion models, Hugging Face, Gen AI CAD grounding | Hugging Face `diffusers` |
| **CAD Design** | Computer-aided design fundamentals for space components | CAD software |
| **Metallography** | Microstructural analysis, material characterisation basics | Lab / optical microscopy |
| **Capstone Projects** | Student-led research design for space material challenges | All of the above |

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
│   └── MSAI_Day1_Exercises.ipynb          # Integrated Day-1 exercise
│
├── Assignments/
│   └── A1_Python_Basics-1.ipynb           # Assignment 1 (7 tasks)
│
├── generate_presentation.py               # Script to generate the .pptx deck
├── CSA_Workshop_Presentation.pptx         # Generated PowerPoint presentation (local only)
└── environment.yml                        # Conda environment specification
```

> **Note:** Generative AI, CAD design, and metallography materials are not fully uploaded to this repository.

---

## Track Details

### Track 1 — Python Foundations
Core Python from first principles — taught to students with no assumed programming background, across all STEM disciplines:
- Primitive types, strings, lists, tuples, dictionaries
- Control flow: conditionals, for/while loops, `range()`
- Functions with default parameters
- Object-oriented programming: classes, `__init__`, inheritance (`super()`)
- File I/O with the `csv` module
- Debugging: identifying and fixing syntax and semantic errors

> Python fundamentals occupied a significant portion of the program timeline, as many students were encountering programming for the first time.

### Track 2 — Scientific Computing
Bridges general programming and scientific data analysis:
- **NumPy:** array operations, linear algebra (eigenvalues, determinants), reshaping
- **Pandas:** DataFrames, `iloc`/`loc`, `groupby`, missing-value handling, one-hot encoding
- **Matminer / Pymatgen:** converting alloy composition strings into numerical features — electronegativity, oxidation states, band center, Mendeleev numbers

### Track 3 — Machine Learning for Materials
Supervised learning applied to real engineering datasets:
- **Regression:** linear → polynomial (degree 2 & 3) on rotational speed vs. torque data; R², MSE
- **Classification:** Decision Tree on the AI4I2020 industrial machine failure dataset (10,000 samples); confusion matrix, classification report
- Key concept: polynomial regression as linear regression on transformed features

### Track 4 — Generative AI & Diffusion Models
Conceptual grounding for Generative AI CAD Design:
- Generative vs. discriminative models — what it means for a model to *create* rather than predict
- Diffusion model fundamentals: forward diffusion (noise addition) and reverse diffusion (learned denoising)
- **Hugging Face `diffusers`:** running pre-trained diffusion models with minimal code
- Foundation for applying generative AI to engineering design and space component workflows

### CAD Design
Introduction to computer-aided design in the context of space components and materials:
- Design fundamentals for engineering parts
- Connection to generative AI design tools
- Application to the capstone project challenges

### Metallography
Hands-on materials characterisation:
- Microstructural analysis of engineering alloys
- Optical microscopy and sample preparation basics
- Interpreting microstructure in the context of material properties

---

## Capstone Projects

Students worked in interdisciplinary teams on two open-ended, space-relevant design challenges. The projects were framed as research design exercises — students were tasked with defining their own objectives and goals rather than following a prescribed procedure.

### Project 1 — Thermal Protection System (TPS)
**Challenge:** Design a research plan for a material capable of withstanding extreme thermal conditions encountered in space applications (e.g., atmospheric re-entry, proximity to propulsion systems).

Students were asked to:
- Identify target thermal performance requirements
- Propose candidate material classes and justify their selection
- Outline a computational and/or experimental characterisation strategy

### Project 2 — Advanced Materials for Robotics
**Challenge:** Identify and characterise materials for robotic components designed to operate in extreme space environments under high-impact mechanical loading.

Students were asked to:
- Define mechanical performance targets for robotic parts
- Research candidate materials balancing weight, toughness, and environmental resistance
- Connect material selection to computational screening approaches covered in the workshop

> Both projects were not fully completed within the workshop timeline and represent directions for future iterations of the program.

---

## Assignment 1

Seven tasks designed to reinforce every track concept across students from any STEM background:

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

- `CSA_Workshop_Presentation.pptx` — 16-slide PowerPoint deck (regenerate with `python generate_presentation.py`)

The presentation covers the pedagogical rationale behind the curriculum, the two capstone projects, and the relevance of the program to CSA's mission in space materials and engineering.

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
