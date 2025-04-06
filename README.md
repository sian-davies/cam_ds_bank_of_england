# Cambridge Bank of England Team Project Assignment

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

These map to the following notebook sections:

### Synthetic Dataset Creation (Sections 2.0 and 2.4.2.0.3)
- Developed a synthetic dataset with predefined labels for sentiment, topic, and question evasion. This dataset provided a controlled benchmark for evaluating model performance. 
- Run results from RoBERTa sentiment analysis and finBERT topic classification were sequentially added to a minimal QA version of this dataset for later comparison with Phi-3.5.

### Phi-3.5 Summarisation (Section 2.1, all subsections)
- Deployed Phi-3.5 to generate concise summaries of transcript segments. 
- Summarisation improved downstream input quality and performance for various NLP tasks, particularly topic classification and question evasion analysis.
- Evaluation of summarised vs original data helped identify trade-offs such as loss of context and sentiment information due to over-summarisation, against the limitations of direct transcript processing including resource usage and reduced accuracy of topic classification.

### Phi-3.5 for Synthetic Data Analysis (Sections 2.4.1, all subsections; 2.4.2.1)
- Applied Phi-3.5 to process the synthetic dataset for topic discovery, sentiment analysis and question evasion analysis.

### Comparative Analysis on Synthetic Data (Section 2.4.2.2)
- Generated accuracy plots to compare Phi-3.5 with other models on the synthetic dataset across topic classification, sentiment, and question evasion tasks. 
- Phi-3.5 performed well for sentiment accuracy but was outperformed by specialised NLP models. However, Phi-3.5 showed improved detection of question evasion in transcript segments.

### Phi-3.5 for Ground Truth Analysis (Section 2.4.3.1)
- Processed ground truth data using Phi-3.5 to assess real-world performance. This dataset provided a benchmark for evaluating real-world data performance.

### Comparative Analysis on Ground Truth Data (Section 2.4.3.2)
- Generated accuracy plots to compare Phi-3.5 with other models on the ground truth dataset across topic classification, sentiment, and question evasion tasks.
- Real-world data gave lower accuracy results across all models compared to the synthetic dataset, highlighting the difficulty inherent in this task from linguistic nuance.
- Phi-3.5 gave improved performance for question evasion detection and comparable performance for topic classification compared to task-specific models.

### Phi-3.5 on Full Financial Quarter Data (Section 3.0.2)
- Applied Phi-3.5 to all identified transcript data from key financial quarters (as determined by Exploratory Data Analysis).
- This analysis focused on extracting topics and question evasion insights reflective of financial health and risk indicators.

### Regulatory Keyword Detection (Section 3.2.5)
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
  ├── Eval_Data/      # Synthetic evaluation datasets
/reports
  ├── findings/       # Summarised findings and insights
  └── presentation/   # Slide deck for stakeholder presentation

- Cambridge_Bank_of_England_Project_Assignment_notebook.html     # Viewable version of notebook
- README.md           # Describes project and my direct code contributions
```
  Note: The project notebook is too large to preview in GitHub, so an HTML version created with [jupyter nbconvert](https://github.com/jupyter/nbconvert) is provided to showcase this project.

## Acknowledgements

This README exclusively reflects my work on Phi-3.5 implementation, synthetic dataset creation, and comparative model evaluations. However, this collaborative project involved contributions from multiple team members participating in the University of Cambridge 'Data Science with Machine Learning and AI' Career Accelerator. So I would like to thank the whole team for our work together on this project, as well as the Bank of England for the opportunity to undertake this project, and the Cambridge academic tutors for their guidance and support throughout.
