# 📦 PII-synthetic\_dataset

A synthetic dataset designed for training and evaluating models in **PII (Personally Identifiable Information) detection** and **Named Entity Recognition (NER)** tasks. All data is **synthetically generated or anonymized**, making it safe for public distribution and experimentation.

---

## 📄 Dataset Description

Each record in the dataset is a JSON object with the following fields:

| Field     | Type    | Description                                                                  |
| --------- | ------- | ---------------------------------------------------------------------------- |
| `text`    | string  | The input sentence containing (or not containing) synthetic PII.             |
| `NER`     | list    | A list of dictionaries, each with an `entity` string and its `label` (type). |
| `has_pii` | boolean | Indicates whether the sample contains any PII entities.                      |

### Example Record

```json
{
  "text": "UPI login from rahul.upi@mail.com with password 'UPIsecure2024#'.",
  "NER": [
    {"entity": "rahul.upi@mail.com", "label": "EMAIL"},
    {"entity": "UPIsecure2024#", "label": "PASSWORD"}
  ],
  "has_pii": true
}
```

---

## 🧾 Entity Labels

The dataset includes the following PII entity types:

| Label            | Description                          |
| ---------------- | ------------------------------------ |
| `EMAIL`          | Email addresses                      |
| `PASSWORD`       | Plaintext passwords                  |
| `PERSON`         | Names of individuals                 |
| `AADHAR`         | Aadhar numbers (India)               |
| `PAN`            | PAN numbers (India)                  |
| `IBAN`           | Bank account numbers (international) |
| `ACCOUNT_NUMBER` | General account numbers              |
| `VOTER_ID`       | Voter ID numbers                     |
| `PHONE`          | Mobile or landline phone numbers     |
| *(extendable)*   | Add your own custom PII labels       |

---

## 📂 File Format

* **Filename**: `PII-synthetic_dataset.json`
* **Format**: JSON list of records
* **Encoding**: UTF-8

---

## 🚀 Intended Use

* Training and testing **PII detection systems**
* Evaluating NER pipelines for sensitive data
* Simulating redaction and compliance tools
* Safe experimentation with anonymized PII examples

---

## ⚠️ Disclaimer

This dataset contains only **synthetic or anonymized data**. Any resemblance to real individuals or data is purely coincidental. Use responsibly in research or development environments.

---

## ✅ How to Load

```python
import json

with open('PII-synthetic_dataset.json', 'r', encoding='utf-8') as f:
    data = json.load(f)

print(data[0])
```

---

## 📜 License

This dataset is released under the **MIT License**. You may use, modify, and distribute it with attribution.

---

## 🙋‍♀️ Contributions

If you'd like to expand this dataset (e.g., add new PII types, languages, or formats), feel free to open a pull request or suggest changes.
