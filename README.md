# Rale Clothing Co. Customer Query Chatbot
### An Intent Classification Approach
**CS5101 Natural Language Processing** | Semester 2, 2025-2026

---

## Overview

This project develops a customer query chatbot for Rale Clothing Co., a
Cebu-based clothing brand that operates primarily through social media. The
chatbot classifies incoming customer messages written in English, Tagalog,
and Cebuano into one of ten predefined intent categories and returns an
appropriate pre-written response.

The system follows a complete NLP pipeline covering data collection, text
preprocessing, feature extraction, model training, evaluation, error analysis,
and a rule-based response layer. Three machine learning classifiers were trained
and compared across two feature representations, resulting in six model-feature
combinations. The best-performing model was Logistic Regression with TF-IDF,
achieving an accuracy of 72.86% and a macro F1-score of 0.73.

---

## Supported Intents

| Intent | Example Query |
|---|---|
| greeting | "Hi! Just found your store online." |
| product_inquiry | "Do you have oversized tees?" |
| price_inquiry | "How much is the black tee?" |
| size_and_fit | "Do you have 3XL?" |
| order_placement | "How do I place an order?" |
| order_status | "When will my order arrive?" |
| payment_methods | "Do you accept GCash?" |
| store_contact | "Where are you located?" |
| return_exchange | "Can I return a damaged item?" |
| promotions | "Any ongoing sales?" |

---

## Project Structure
rale.cco-chatbot/
├── rale_cco_chatbot.ipynb        # Main Jupyter Notebook (report + code)
├── rale_clothing_intent_dataset.csv  # Manually written multilingual dataset
├── README.md                     # Project overview and setup guide
└── .gitignore                    # Excludes checkpoints and cache files

---

## Setup

### Requirements

- Python 3.8 to 3.12 (Python 3.11 recommended for spaCy compatibility)
- Jupyter Notebook or VS Code with the Jupyter extension

### Installation

1. Clone the repository:

git clone https://github.com/CTRL-JUJU/rale.cco-chatbot.git
cd rale.cco-chatbot

2. Install the required libraries:

pip install pandas numpy matplotlib seaborn scikit-learn nltk

3. Download the required NLTK resources by running the following in
   Python or in the first code cell of the notebook:
```python
import nltk
nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('stopwords')
nltk.download('wordnet')
nltk.download('omw-1.4')
```

---

## Usage

1. Open `rale_cco_chatbot.ipynb` in Jupyter Notebook or VS Code.
2. Make sure `rale_clothing_intent_dataset.csv` is in the same folder
   as the notebook.
3. Run all cells in order from top to bottom using **Run All**.
4. Navigate to **Section 8 (Rule-Based Response System + Live Demo)**
   and interact with the chatbot using the live input cell.
5. Type `exit`, `quit`, or `bye` to end the conversation.

> To switch the active model powering the chatbot, modify the two lines
> in the **Set Active Model** cell before the demo loop:
> ```python
> vectorizer = tfidf_vectorizer   # or bow_vectorizer
> model = lr_tfidf                # or lr_bow, nb_tfidf, nb_bow, svm_tfidf, svm_bow
> ```

---

## Group Members

| Name | Role |
|---|---|
| Abrenica | Dataset, Preprocessing, Rule-Based Response System |
| Ando | Project Management, Integration and Testing, Documentation |
| Montebon | Model Training, Evaluation |
| Ruelan | Feature Extraction, Error Analysis |

