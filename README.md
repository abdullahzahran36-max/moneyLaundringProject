# Anti-Money Laundering (AML) Transaction Classifier

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Framework: Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.3+-orange.svg)](https://scikit-learn.org/)
[![Code Style: Black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

## Project Overview & Objectives

Financial institutions process millions of high-throughput payments daily, where illicit actors disguise illegitimate capital flows through layered, complex payment rails. This project develops a high-performance machine learning classification system tailored to flag suspicious money laundering transactions across multi-currency settlement channels. The primary objective is to resolve severe class imbalance ($0.104\%$ positive prevalence) to maximize true-positive recall on critical illicit typologies while enforcing low false-positive alert volumes to sustain compliance operational efficiency.

## Contributors

| Name | major | Contact |
| :--- | :--- | :--- |
| [Ala'a Yahia Almousa ] | Data Science and Artificial Intelligence | [https://github.com/Alaa-20040521 / alaayahia693@gmail.com] |
| [Abdellrahman Abdallah Alhanaqtah] | Intelligent Systems Engineering | [hanaqtahabdellrahman@gmail.com / https://github.com/abdellrahmanHq] |
| [Rana Kamel Khaleel Jumah] | Computer Science | [https://github.com/rana03jumah  / rana03jumah@gmail.com] |
| [abdullah anas zahran ] | computer information system | [ abdullahzahran36@gmail.com / https://github.com/abdullahzahran36 ] |
| [ ليث سامي اسماعيل الحواجرة ] |  ذكاء اصطناعي وعلم بيانات (AI & DS) | [ laith.alhawjreh@gmail.com / https://github.com/Laith-Alhawajreh ] |
| [ Obaeda Majde Abu Baker ] | [ Computer Science ] | [ https://github.com/Obaedamjde ] |
| [ Oula Saleem Hanandeh ] | Data science & Artificial intelligence | [ olasaleemhanandeh@gmail.com / https://github.com/olasaleemhanandeh-ux]
## Dataset Specifications

* **Source:** [Kaggle — Anti Money Laundering Transaction Data (SAML-D)](https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml)
* **Citation:** Oztas et al., *"Enhancing Anti-Money Laundering: Development of a Synthetic Transaction Monitoring Dataset,"* IEEE ICEBE 2023.
* **Dimensions:** $9,504,852$ rows $\times$ $12$ columns (~203 MB compressed / ~890 MB uncompressed CSV)
* **Target Variable:** `Is_laundering`
* Class 0 (Legitimate): 75,000 transactions (75.0000%)
* Class 1 (Illicit): 25,000 transactions (25.0000%)
* Imbalance Ratio: ≈ 1:3

* Typological Patterns: 28 distinct behavioral transaction archetypes (11 benign commercial patterns and 17 financial crime structures including Fan-In, Fan-Out, Cycling, and Cross-Border structuring).

### Feature Schema

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `Date` | `date` (`YYYY-MM-DD`) | Transaction settlement date. |
| `Time` | `time` (`HH:MM:SS`) | Precise timestamp of transaction settlement. |
| `Sender_account` | `int64` | Unique originating entity account identifier. |
| `Receiver_account` | `int64` | Unique beneficiary entity account identifier. |
| `Amount` | `float64` | Transacted nominal volume in source payment currency. |
| `Payment_currency` | `category` / `string` | Currency initiated by the sender (e.g., `UK pounds`, `USD`). |
| `Received_currency` | `category` / `string` | Currency settled at the beneficiary (flags FX conversion disparities). |
| `Sender_bank_location` | `category` / `string` | Domicile jurisdiction of sender entity. |
| `Receiver_bank_location` | `category` / `string` | Domicile jurisdiction of recipient institution. |
| `Payment_type` | `category` / `string` | Settlement rail (`ACH`, `Cross-border`, `Cheque`, `Cash Deposit`, `Debit card`). |
| `Is_laundering` | `int64` | **Target Variable**: Ground-truth label (`0` = Normal, `1` = Laundering). |
| `Laundering_type` | `category` / `string` | Latent typological category (*withheld during training to prevent target leakage*). |
