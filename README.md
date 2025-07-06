#  ICD-10 Code Mapping AI System

This project builds an AI-based system that **automatically maps patient diagnosis terms to their appropriate ICD-10 codes and descriptions** using NLP and semantic similarity techniques.

---

##  Objective

To automate the mapping of unstructured patient diagnoses to standardized ICD-10 codes and descriptions using AI/ML tools such as Sentence Transformers, Python, and publicly available ICD metadata.

---

##  Dataset Overview

### 1. **Diagnoses_list.xlsx**
- Contains free-text diagnosis terms (one per row).
- Column: `Diagnosis`

### 2. **ICD10codes**
- Contains standardized ICD-10 codes and their medical descriptions.
- Columns: `code`, `desc`

---

##  Tools & Technologies

| Tool/Library             | Purpose                                  |
|--------------------------|------------------------------------------|
| Python                   | Core language                            |
| Pandas, NumPy            | Data handling and preprocessing          |
| SentenceTransformers     | Sentence embeddings for semantic search  |
| Matplotlib, Seaborn      | Data visualization                       |
| OpenPyXL                 | Reading/writing Excel files              |

---

##  Methodology

###  Step-by-Step Workflow

1. **Load and Clean Datasets**  
   - Standardize both diagnosis terms and ICD descriptions.

2. **Text Embedding**  
   - Convert both diagnosis terms and ICD descriptions to vector form using `paraphrase-MiniLM-L3-v2` for fast, lightweight inference.

3. **Semantic Matching**  
   - For each diagnosis, compute cosine similarity with all ICD-10 descriptions.
   - Pick the highest-matching code and description.

4. **Output Generation**  
   - Save final mapped dataset with:
     - `Original diagnosis`
     - `Mapped ICD-10 code`
     - `Diagnosis description`

5. **Visualization**  
   - Top 10 most frequent ICD codes.
   - Category distribution based on first character of ICD code.
   - Heatmap of diagnosis vs ICD mappings.

---

##  Output File

- `Final_ICD10_Mapped.xlsx`  
  A spreadsheet that contains the final diagnosis-to-code mappings with their descriptions.

---

##  Example Output (Excel)

| Original diagnosis   | Mapped ICD-10 code | Diagnosis description                          |
|----------------------|--------------------|-------------------------------------------------|
| Type 2 Diabetes       | E11.9              | Type 2 diabetes mellitus without complications |
| Asthma                | J45.909            | Unspecified asthma, uncomplicated              |
| High Blood Pressure   | I10                | Essential (primary) hypertension               |

---


