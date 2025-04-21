# CORDIS + UKRI Project Search & Topic Modeling

This project enables keyword-based exploration and topic modeling of publicly funded research projects from the CORDIS (EU) and UKRI (UK) databases. It combines interactive data analysis, visualization, and LDA-based NLP techniques to uncover trends in innovation, funding distribution, and thematic clusters across thousands of records.

---

## Features

- Keyword Search Engine
  - Query UKRI and CORDIS databases using keywords with OR/AND logic
  - Optional date filtering
  - Handles multilingual and domain-specific input

- Data Integration & Preprocessing
  - Harmonizes formats across datasets
  - Converts UKRI funding data to Euro using exchange rates
  - Cleans organization and project metadata

- Interactive Reports
  - Outputs `keywordResults.xlsx` with multiple sheets (projects, organizations, top coordinators)
  - Generates `html_report.html` with charts for project cost, contribution breakdowns, and organization metrics

- LDA Topic Modeling
  - Text preprocessing with tokenization, lemmatization, and domain-specific stopword removal
  - Model tuning for number of topics, passes, alpha, and eta
  - pyLDAvis-based interactive visualizations

- Topical Insights
  - Exports project-topic assignments and top words
  - Provides Excel + HTML summaries by funding, country involvement, and topic relevancy

---

## Output Files

- `keywordResults.xlsx` – Results from keyword search across UKRI and CORDIS
- `html_report.html` – Interactive summary report (funding breakdowns, top organizations, etc.)
- `topicModelingResults.xlsx` – Topic modeling outputs (top projects per topic, country breakdowns)
- `topicModelingGraphs.html` – Full topic modeling visualizations with Plotly and pyLDAvis

---

## Topic Modeling Pipeline

1. Preprocessing
   - Tokenization and lemmatization of project titles and abstracts
   - Removal of standard, domain-specific, and most frequent stopwords
   - Bigram creation and rejoining for downstream modeling

2. LDA Training
   - Coherence-based grid search for optimal number of topics and passes
   - Fine-tuning alpha and eta hyperparameters
   - Visualization with pyLDAvis and Plotly

---

## Installation

```bash
git clone https://github.com/yourusername/tier2022.git
cd tier2022

# Install dependencies
pip install -r requirements.txt

# OR manually:
pip install xlsxwriter pyLDAvis==2.1.2 nltk gensim plotly openpyxl
