# Cambridge Bank of England Team Project Assignment   
[![View in nbviewer](https://img.shields.io/badge/View%20Notebook%20in-nbviewer-orange)](https://nbviewer.org/github/sian-davies/cam_ds_bank_of_england/blob/main/notebook/Cambridge_Bank_of_England_Project_Assignment_notebook.ipynb)     [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sian-davies/cam_ds_bank_of_england/blob/main/notebook/Cambridge_Bank_of_England_Project_Assignment_notebook.ipynb)   

## Collaborative Earnings Call Transcript Analysis

This repository contains a collaborative piece of work on leveraging Natural Language Processing (NLP) techniques to extract actionable insights from earnings call transcripts, specifically to support the Prudential Regulation Authority’s oversight of G-SIBs. The project evaluates various NLP models for tasks such as sentiment analysis, topic discovery, and question evasion detection.

> **Note:** This repository includes work from multiple project team members. This README highlights the sections where I contributed directly: using the open-source large language model **Phi-3.5**, synthetic dataset creation, and comparative model evaluation.


## Project Overview

The overall project sought to integrate earnings call transcript analysis into a regulatory framework to facilitate better risk identification and financial oversight. Our primary objectives included:
- Data preparation and extraction of key financial and transcript attributes.
- Evaluation of multiple NLP models (e.g., BERTopic, FinBERT, RoBERTa) alongside Phi-3.5 for:
  - Summarisation
  - Sentiment Analysis
  - Topic Classification
  - Question Evasion Detection
- Regulatory Keyword Identification
- Comparative analysis using both synthetic and ground truth datasets.


## Key Contributions
My contributions focussed on:
- Creating and utilising synthetic datasets.
- Integrating and deploying the Phi-3.5 model for multiple tasks.
- Conducting comparative performance evaluations with accuracy plots.
- Implementing regulatory keyword detection and full-scale analysis from selected financial quarters.


<details>
<summary><strong>📘 Click to expand notebook outline</strong></summary>

## 📘 Notebook Outline

- Business Context and Project Scenario
- Setup: Libraries & Packages
- 0 Exploration of Financial Metrics Data
- 1 Data Collection and Pre-Processing of Transcripts
  - 1.1 Extract information from transcripts
    - 1.1.0 Helper functions
    - 1.1.1 Unzip files
    - 1.1.2 PDF-to-table converter
    - 1.1.3 Batch-process PDF files
    - 1.1.4 Convert PDFs to CSV
    - 1.1.5 Output
    - 1.1.6 Checking the data
  - 1.2 Data Cleaning
  - 1.3 Initial Exploratory Data Analysis
    - 1.3.1 Transcripts overview
    - 1.3.2 1Q22 and 2Q24
    - 1.3.3 Emerging risks
- 2 Selecting Models and Scalability Assessment
  - 🟠 **2.0 Evaluation dataset creation**
    - 2.0.1 Selecting ground truth
  - 🟠 **2.1 Phi 3.5 for summarisation**
    - 🟠 **2.1.0 Phi-3.5 Initialisation**
    - 🟠 **2.1.1 Summarisation function**
    - 🟠 **2.1.2 Generate summarised text**
  - 2.2 Sentiment Analysis
    - 2.2.0 Load ground truth dataset
    - 2.2.1 Sentiment model analyses
    - 2.2.2 Model comparison
    - 2.2.3 Run full dataset
  - 2.3 Topic Modelling
    - 2.3.1 FinBERT classification
      - 2.3.1.0 Model setup
      - 2.3.1.1 Helper functions
      - 2.3.1.2 Optimising chunking options
      - 2.3.1.3 Using summarised text
      - 2.3.1.4 Comparison
    - 2.3.2 BERTopic
      - 2.3.2.1 Preprocessing function
      - 2.3.2.2 Run on summarised text
  - 2.4 QA Evasion & Generalisability
    - 2.4.0 FinBERT classification for evasion 
    - 🟠 **2.4.1 Phi-3.5 Pipeline Initialisation**
      - 🟠 **2.4.1.0 Preparing datasets for Phi 3.5**
      - 🟠 **2.4.1.1 Prompts**
      - 🟠 **2.4.1.2 Functions to run analyses with Phi-3.5**
      - 🟠 **2.4.1.3 Functions for accuracy plots**
    - 2.4.2 Synthetic dataset
      - 🟠 **2.4.2.0 Prepare synthetic data table**
        - Run RoBERTa
        - Run FinBERT
        - Create combined synthetic data table
      - 🟠 **2.4.2.1 Run Phi-3.5 on synthetic dataset**
      - 🟠 **2.4.2.2 Compare results with other models**
    - 🟠 **2.4.3 Ground Truth dataset**
      - 🟠 **2.4.3.0 Prepare ground truth data tables**
      - 🟠 **2.4.3.1 Run Phi-3.5 on ground truth**
      - 🟠 **2.4.3.2 Model comparisons**
- 3 Analysis
  - 3.0 Full dataset analysis
    - 3.0.1 RoBERTa seniment analysis
    - 🟠 **3.0.2 Phi-3.5 by quarter**
  - 3.1 22Q1
    - 3.1.1 Sentiment
    - 3.1.2 Topic modelling (negative-sentiment texts)
      - 3.1.2.1 BERTopic
      - 3.1.2.2 FinBERT
    - 3.1.3 Evasion
      - 3.1.3.1 Topic modelling (evasive texts) - BERTopic
    - 3.1.4 Evasion and Negativity
  - 3.2 Recent Two Quarters (2Q24, 3Q24)
    - 3.2.0 Data exploration
    - 3.2.1 Sentiment
    - 3.2.2 Topic modelling (negative-sentiment texts)
      - 3.2.2.1 BERTopic
      - 3.2.2.2 FinBERT
    - 3.2.3 Evasion
      - 3.2.3.1 Topic modelling (evasive texts) - BERTopic
    - 3.2.4 Evasion and Negativity
    - 🟠 **3.2.5 Regulatory keywords detection**
- 4 Conclusions

</details>


- ### Synthetic Dataset Creation 
  *Sections 2.0 and 2.4.2.0*
  - Developed a synthetic dataset with predefined labels for sentiment, topic, and question evasion. This dataset provided a controlled benchmark for evaluating model performance. 
  - Run results from RoBERTa sentiment analysis and finBERT topic classification were sequentially added to a minimal QA version of this dataset for later comparison with Phi-3.5.

- ### Phi-3.5 Summarisation
  *Section 2.1, all subsections*
  - Deployed Phi-3.5 to generate concise summaries of transcript segments. 
  - Summarisation improved downstream input quality and performance for various NLP tasks, particularly topic classification and question evasion analysis.
  - Evaluation of summarised vs original data helped identify trade-offs such as loss of context and sentiment information due to over-summarisation, against the limitations of direct transcript processing including resource usage and reduced accuracy of topic classification.

- ### Phi-3.5 for Synthetic Data Analysis
  *Sections 2.4.1, all subsections; 2.4.2.1*
  - Applied Phi-3.5 to process the synthetic dataset for topic discovery, sentiment analysis and question evasion analysis.

- ### Comparative Analysis on Synthetic Data
  *Section 2.4.2.2*
  - Generated accuracy plots to compare Phi-3.5 with other models on the synthetic dataset across topic classification, sentiment, and question evasion tasks. 
  - Phi-3.5 performed well for sentiment accuracy but was outperformed by specialised NLP models. However, Phi-3.5 showed improved detection of question evasion in transcript segments.

- ### Phi-3.5 for Ground Truth Analysis
  *Section 2.4.3.1*
  - Processed ground truth data using Phi-3.5 to assess real-world performance. This dataset provided a benchmark for evaluating real-world data performance.

- ### Comparative Analysis on Ground Truth Data
  *Section 2.4.3.2*
  - Generated accuracy plots to compare Phi-3.5 with other models on the ground truth dataset across topic classification, sentiment, and question evasion tasks.
  - Real-world data gave lower accuracy results across all models compared to the synthetic dataset, highlighting the difficulty inherent in this task from linguistic nuance.
  - Phi-3.5 gave improved performance for question evasion detection and comparable performance for topic classification compared to task-specific models.

- ### Phi-3.5 on Full Financial Quarter Data
  *Section 3.0.2*
  - Applied Phi-3.5 to all identified transcript data from key financial quarters (as determined by Exploratory Data Analysis).
  - This analysis focused on extracting topics and question evasion insights reflective of financial health and risk indicators.

- ### Regulatory Keyword Detection
  *Section 3.2.5*
  - Implemented detection and analysis for regulatory keywords to flag discussions with potential regulatory impact (e.g., Basel III).
  - This analysis supported identifying discussions with potential regulatory implications.



## Insights for Future Pipeline Refinement
- **Summarisation Trade-Offs:**  
    Summarisation with Phi-3.5 tends to neutralise sentiment, leading to instances of misclassification. However, it improves performance of task-specific models for topic classification.
  
- **Scalability and Automation:**  
  The versatility of Phi-3.5 indicates its potential to automate preprocessing tasks (e.g., merging interruptions, filtering greetings), thereby enhancing pipeline scalability across varied transcript formats.


## Repository Structure

```
/notebook
  ├── Cambridge_Bank_of_England_Project_Assignment_notebook.ipynb
/data
  ├── Raw_Data/       # Raw PDF transcripts and financial metrics used for analysis
  ├── Processed_Data/ # Evaluation datasets (critical files saved here during run)
/docs                 # HTML version of Colab for Github Pages
/reports
  ├── findings/       # Summarised findings and insights
  └── presentation/   # Slide deck for stakeholder presentation
- README.md           # Describes project and my direct code contributions
```

Note: an HTML version was created with [jupyter nbconvert](https://github.com/jupyter/nbconvert) to showcase this project in Github Pages.

The project notebook is too large to preview in GitHub:
  👉 [Click here to view the notebook in nbviewer](https://nbviewer.org/github/sian-davies/cam_ds_bank_of_england/blob/main/notebook/Cambridge_Bank_of_England_Project_Assignment_notebook.ipynb)


## Acknowledgements

This README exclusively reflects my work on Phi-3.5 implementation, synthetic dataset creation, and comparative model evaluations. However, this collaborative project involved contributions from multiple team members participating in the University of Cambridge 'Data Science with Machine Learning and AI' Career Accelerator. So I would like to thank the whole team for our work together, as well as the Bank of England for the opportunity to undertake this project, and the Cambridge academic tutors for their guidance and support throughout.
