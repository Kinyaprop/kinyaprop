## KinyaProp: Fine-grained Propaganda Analysis in Kinyarwanda  
**License:** ![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)

This repository contains **KinyaProp**, a fine-grained propaganda dataset
annotated on Kinyarwanda news articles.

---

## File Structure

```text
KinyaProp/
├── README.md
├── dataset/
│   ├── annotations_raw.json
│   └── gold_majority_vote.json
````

---

## File Description

### 1) `annotations_raw.json`

This file contains **raw annotations** independently produced by **three annotators**.

Each entry has the following structure:

```json
[
  {
    "article_num": "article ID",
    "article_text": "article title\n\n article content",
    "category": "article category ID",
    "kin_label": "category name in Kinyarwanda",
    "annotators": {
      "annotator_id": [
        {
          "text": "propagandistic span text",
          "label": "propaganda technique label",
          "start": span_start,
          "end": span_end
        }
      ]
    }
  }
]
```

**Category mapping:**

* 1 → politics
* 2 → sport
* 3 → economy
* 4 → health
* 5 → entertainment
* 6 → history
* 7 → technology
* 8 → tourism
* 9 → culture
* 10 → fashion
* 11 → religion
* 12 → environment
* 13 → education
* 14 → relationship

---

### 2) `gold_majority_vote.json`

This file contains **final (gold) annotations** produced using a **majority agreement strategy**.

**Majority agreement:**
A span is assigned a label when at least **two annotators agree**.

Each entry has the following structure:

```json
[
  {
    "article_num": "article ID",
    "article_text": "article title\n\narticle content",
    "category": "article category ID",
    "kin_label": "category name in Kinyarwanda",
    "gold_spans": [
      {
        "text": "propagandistic span text",
        "label": "propaganda technique label",
        "start": span_start,
        "end": span_end
      }
    ]
  }
]
```
