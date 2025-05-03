
# Context-Aware Bias Detection and Controlled Text Rewriting

## Project Overview
This project aims to build an AI-driven system for detecting and mitigating political bias in news media. The objective is to identify **left**, **center**, and **right** bias in articles and eventually **rewrite biased content** to make it more neutral while **preserving factual integrity**.

The project is divided into two main phases:
1. **Bias Detection** – Classifying news articles based on their political bias using transformer models.
2. **Bias Mitigation** – Rewriting the detected biased content using controlled text generation methods.

The system emphasizes **explainability**, **accuracy**, and **responsible AI usage**, especially in journalism and media.

---

## Models Used
### Bias Detection
- **BERT-base-uncased**  
  Used as the primary model for classification of news bias into three categories.
- **RoBERTa-base** *(planned)*  
  Will be used for performance comparison and possible model enhancement.

### Explainability
- **LIME (Local Interpretable Model-agnostic Explanations)**
- **SHAP (SHapley Additive exPlanations)**  
  These tools will be used to interpret model predictions and identify bias-inducing language.

### Bias Mitigation *(upcoming)*
- **BART** – For controlled text rewriting while preserving meaning.
- **GPT-based models** – For generating neutralized versions of biased content.
- **Evaluation Metrics**: BERTScore, ROUGE, BLEU for semantic similarity and factual retention.

---

## Project Flow

1. **Start**: Input news articles from dataset  
2. **Preprocessing**: Clean and combine title + content  
3. **Tokenization**: Use BERT tokenizer for input formatting  
4. **Bias Detection**: Classify bias using BERT / RoBERTa  
5. **Evaluation**: Generate classification report and confusion matrix  
6. **Explainability**: Use SHAP & LIME to interpret model predictions  
7. **Bias Mitigation**: Rewrite biased content with BART / GPT  
8. **Output**: Neutralized version of original article  
9. **Evaluation**: Use BLEU, ROUGE, BERTScore to verify neutrality


### Datasets
- **Old Dataset (unusable due to size)**: [News Media Bias Dataset](https://huggingface.co/datasets/newsmediabias/news-bias-full-data)  
- **Current Dataset**: [Article-Bias-Prediction](https://github.com/ramybaly/Article-Bias-Prediction)

---

## Current Status
- Data preprocessing and BERT model training completed  
- Achieved ~81% accuracy on bias classification  
- RoBERTa fine-tuning and explainability integration in progress  
- Bias mitigation (controlled rewriting) to be implemented

---
## Citation

@inproceedings{baly2020we,
  author      = {Baly, Ramy and Da San Martino, Giovanni and Glass, James and Nakov, Preslav},
  title       = {We Can Detect Your Bias: Predicting the Political Ideology of News Articles},
  booktitle   = {Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP)},
  series      = {EMNLP~'20},
  NOmonth     = {November},
  year        = {2020}
  pages       = {4982--4991},
  NOpublisher = {Association for Computational Linguistics}
}

---
## Links
- [GitHub Repository](https://github.com/Jayasri2021/EAI_News_Media_Bias)  
- Dataset: [Article-Bias-Prediction](https://github.com/ramybaly/Article-Bias-Prediction)

---

## Contributors
- Amrutha Kollu  
- Jayasri Suresh Vani  
- Mohamed Aarif Mohamed Sulaiman  
