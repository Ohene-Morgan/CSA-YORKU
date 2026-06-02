# CSA Presentation Outline
## "Teaching AI & Data Science to the Next Generation of Materials Scientists"
### A Curriculum Design Report for the Canadian Space Agency

---

## Slide 1 — Title Slide

**Title:** Teaching AI & Data Science to the Next Generation of Materials Scientists

**Subtitle:** A curriculum design report for the Canadian Space Agency

**Presenter:** [Your Name]
**Date:** [Presentation Date]

**[PLACEHOLDER: CSA logo — top-right corner]**
**[PLACEHOLDER: York University logo — top-left corner]**

---

## Slide 2 — The Problem We Were Solving

**Heading:** The Skill Gap in Materials Science Education

- Undergraduate materials science programs teach domain knowledge — not data science
- Modern materials research is increasingly data-driven: ML for property prediction, high-throughput screening, autonomous experimentation
- Students entering research labs often lack the coding fluency to use these tools
- **Goal:** give students a working foundation, not a survey — code they can actually run and extend

> *Speaker note: This workshop was a direct response to a real gap — students who understand crystallography and thermodynamics but freeze when handed a CSV file.*

---

## Slide 3 — Workshop at a Glance

**Heading:** The Workshop — Structure at a Glance

| Track | Content | Tools |
|-------|---------|-------|
| **Track 1** — Python Foundations | Variables, OOP, file I/O | Base Python |
| **Track 2** — Scientific Computing | Arrays, DataFrames, materials features | NumPy, Pandas, Matminer |
| **Track 3** — Machine Learning | Regression, classification, evaluation | Scikit-learn |
| **Track 4** — Generative AI | Diffusion models, Hugging Face, Gen AI CAD grounding | Hugging Face diffusers |
| **Capstone** | Materials featurization pipeline | All of the above |

**Platform:** Jupyter Notebooks
**Environments supported:** Google Colab · Syzygy · Local Conda

**[PLACEHOLDER: flow diagram — 3 tracks converging into capstone exercise]**

---

## Slide 4 — Pedagogical Philosophy

**Heading:** How I Thought About This

### Three design principles:

1. **Progressive Complexity**
   Each concept builds on the last. No tool is introduced before its prerequisites are in place.

2. **Learn by Doing**
   Every idea is immediately exercised in runnable code. Students write real Python, not pseudocode.

3. **Real Data, Real Problems**
   Industrial machine failure data, materials composition databases — not toy examples designed to be easy.

> *"An undergraduate who can read and modify a real notebook leaves more capable than one who watched a demo."*

---

## Slide 5 — Track 1: Python Foundations

**Heading:** Track 1 — Building the Language Scaffold

**What was taught:**
- Data types (strings, integers, floats, lists, tuples, dictionaries)
- Control flow (if/elif/else, for loops, while loops)
- Functions with default parameters
- Object-oriented programming: classes, `__init__`, methods, inheritance
- File I/O: reading and writing CSV files

**Why these topics specifically:**
- **OOP first** — materials-science libraries (pymatgen, matminer) use class-based APIs; students need to instantiate objects, not just call functions
- **File I/O early** — scientific data almost always lives in files; this is unavoidable
- **Debugging exercise included deliberately** — error-reading is a teachable skill, not a side effect

**[PLACEHOLDER: screenshot of Lab 1 — Alloys class and HEA subclass exercise]**

---

## Slide 6 — Track 2: Scientific Computing

**Heading:** Track 2 — The Bridge Between Code and Science

**What was taught:**
- **NumPy:** array creation, math, linear algebra (determinants, eigenvalues), reshape/ravel/transpose
- **Pandas:** DataFrames, iloc/loc indexing, groupby, missing value handling, one-hot encoding
- **Matminer:** converting composition strings to numerical features — electronegativity, oxidation states, band center, Mendeleev numbers

**Why:**
- NumPy and Pandas are the lingua franca of scientific Python — they are unavoidable
- Matminer was the connection point: students see their domain knowledge (alloy compositions like Ti-6Al-4V) become ML-ready numbers
- One-hot encoding was introduced here — at the point of need for the ML track, not speculatively

**[PLACEHOLDER: screenshot of Pandas DataFrame showing alloy compositions]**

---

## Slide 7 — Track 3: Machine Learning

**Heading:** Track 3 — Models That Make Predictions

**What was taught:**
- **Linear Regression** → **Polynomial Regression** (degree 2 & 3) on rotational speed vs. torque data
- **Decision Tree Classifier** on the AI4I2020 industrial machine failure dataset (10,000 real samples)
- **Model evaluation:** R², MSE, confusion matrix, classification report

**Key pedagogical choices:**
- Polynomial regression taught as *"linear regression on transformed features"* — dispels the misconception that non-linear = a different algorithm entirely
- Real engineering dataset for decision trees — students see *why* ML is useful before they see *how* to run it
- Confusion matrix visualized as a heatmap, not just printed — builds intuition for false positives vs. false negatives in safety-critical applications

**[PLACEHOLDER: polynomial regression curve fit plot or confusion matrix heatmap]**

---

## Slide 8 — Track 4: Generative AI & Diffusion Models

**Heading:** Track 4 — Generative AI & Diffusion Models

**What was taught:**
- **Generative vs. discriminative AI** — conceptual framing: discriminative models predict, generative models create
- **Diffusion model fundamentals:**
  - Forward diffusion: progressively adding noise to data until it is unrecognisable
  - Reverse diffusion: training a model to denoise step-by-step and reconstruct (or generate) the original
- **Hugging Face `diffusers` library** — accessing production-grade pre-trained models with a few lines of Python
- **Hands-on:** running and querying pre-trained diffusion models; interpreting and evaluating outputs

**Ultimate goal — grounding for Generative AI CAD Design:**
- Students leave with the conceptual vocabulary to understand how AI can *generate* novel designs, not just analyse existing ones

**Why this module, why now:**
- Generative AI is reshaping engineering design workflows — the next generation of engineers must understand it, not just use it as a black box
- Hugging Face democratises access — students run state-of-the-art models without training them from scratch

**[PLACEHOLDER: screenshot or diagram — forward/reverse diffusion process OR Hugging Face pipeline code cell]**

> *Speaker note: This module served as conceptual grounding, not a deep-dive. The goal was to give students the vocabulary and hands-on familiarity to reason about generative AI tools they will encounter in modern design workflows.*

---

## Slide 9 — Bringing It Together: The Capstone

**Heading:** The Capstone — Materials Featurization from First Principles

**What happened in the Day-1 integrated exercise:**
- Students built feature engineering functions from scratch:
  - Weighted mean electronegativity (Pauling scale)
  - Weighted variance of electronegativity
  - Weighted mean atomic mass
  - Weighted mean Mendeleev number
- Applied those features to sets of binary and ternary alloys (e.g., Al50Cu50, Fe40Ni40Cr20)
- Trained a toy linear regression model on hand-crafted features
- Optionally extended with Matminer's production-grade featurizers

**Why this mattered:**
- Students derived features using real physics — they understood *what* they were computing
- They experienced the full pipeline: raw composition string → numerical features → trained model → prediction
- This is the exact workflow used in real materials informatics research labs

**[PLACEHOLDER: scatter plot of alloy feature space from Day-1 exercise]**

---

## Slide 9 — Assignment Design Philosophy

**Heading:** Assignments — Designed to Force Thinking, Not Copying

**Assignment 1 — 7 progressive tasks:**

| Task | Concept Tested | Design Reason |
|------|----------------|---------------|
| 1 | CSV reading + iteration | File I/O is non-negotiable in any research workflow |
| 2 | Custom `max()` function | Forces re-implementation of built-ins — tests real understanding vs. memorization |
| 3 | `Alloys` class + `HEAs` subclass | OOP in a domain-relevant context students care about |
| 4 | Composition string parser (e.g., `Ti6Al4V`) | Regex + validation — mirrors real data cleaning challenges |
| 5 | Debug broken code | Error-reading as a teachable, explicit skill |
| 6 | NHL Stanley Cup Excel analysis | Cross-domain problem — demonstrates that programming skills generalize |
| 7 | Matminer EDA + feature selection | Mini-project: load data → explore → featurize → prune correlated features |

> *Task 6 (NHL data) was intentional — students who can only apply code to materials data haven't really learned to code.*

---

## Slide 10 — What It Looked Like in Practice

**Heading:** What It Looked Like in Practice

**[PLACEHOLDER: side-by-side screenshot — exercise prompt cell and student-facing fill-in-the-blank code cell]**

**Caption:** Notebooks mixed guided explanation with fill-in-the-blank code cells. Students wrote real Python against real libraries — not pseudocode, not multiple choice.

> *Speaker note: The "fill-in-the-blank" format is deliberate — it scaffolds without removing the cognitive load of actually writing code. Students have to understand the logic, not just copy it.*

---

## Slide 11 — Key Design Decisions

**Heading:** The Choices I Made — and Why

- **Jupyter notebooks over slides**
  Interactivity matters — students can experiment, break things, and fix them in the same environment

- **Multiple environment paths (Colab / Syzygy / local Conda)**
  Setup failures kill momentum; every student needed a path that worked for their machine

- **Domain-specific examples throughout**
  Ti-6Al-4V, CoCrFeMnNi, IrO₂ — materials students stay engaged when examples are from their field

- **Cross-domain assignment (NHL data)**
  Deliberate choice — teaches that data science is a transferable skill, not a materials-specific recipe

- **Correlation pruning in the final task**
  Introduces multicollinearity as a concept — students learn *when* to drop features, not just *how* to call `corr()`

---

## Slide 14 — Relevance to CSA's Mission

**Heading:** Why This Matters for CSA

- Materials science is central to space hardware: lightweight alloys, thermal coatings, radiation-resistant structural composites
- CSA-affiliated researchers increasingly use ML for accelerated materials discovery and property prediction
- Students trained in this curriculum can contribute to CSA-adjacent research from day one — no onboarding ramp for tools
- The matminer/pymatgen stack used in this workshop is the same stack deployed in academic and national-lab materials informatics
- **Generative AI for CAD Design — a direct CSA application:**
  - Diffusion models can generate novel component geometries, lattice structures, and material configurations
  - Students now have the conceptual foundation to work with and critically evaluate these tools in a design context
- Building this pipeline into undergraduate education creates a cohort of research-ready, computationally fluent engineers for CSA-funded projects

---

## Slide 13 — Reflections & Recommendations

**Heading:** What I'd Keep, What I'd Refine

### What worked well:
- Progressive structure — students had the vocabulary they needed at each stage, not before
- Real datasets — engagement was higher than with synthetic examples
- The capstone exercise — it forced genuine integration of all three tracks

### What I'd refine:
- More time on Pandas data cleaning (the step where students most often got stuck)
- A second ML module covering neural networks or random forests
- Student-driven mini-projects as a final deliverable — gives ownership

### Recommendation:
Repeat with a longer timeline or a second workshop iteration; the foundation is solid and the content is modular enough to extend.

---

## Slide 14 — Thank You / Q&A

**Heading:** Thank You

Questions welcome.

**[PLACEHOLDER: CSA logo]**
**[PLACEHOLDER: York University logo]**

**[Your Name]**
**[Email / Contact]**
