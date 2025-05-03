# Context-Aware Bias Detection and Controlled Text Rewriting for Fairer News Media

##  Project Overview
This project proposes a transformer-based system for detecting and mitigating **political bias** in news media. The aim is to classify articles as **left**, **center**, or **right** and **rewrite biased content** into more neutral versions, while preserving the **factual integrity** of the original information.

The methodology integrates:
1. **Bias Detection** – Using fine-tuned transformer models (BERT).
2. **Model Explainability** – With SHAP and LIME for transparency.
3. **Bias Mitigation** – Using T5-based rewriting models to neutralize ideologically biased content.

---

##  Models Used

###  Bias Detection
- **BERT-base-uncased** (fine-tuned)
- (Attempted) **RoBERTa-base** – Dropped due to convergence issues

###  Explainability
- **LIME** – Interprets token-level feature importance via perturbation
- **SHAP** – Provides global token attributions using transformer-compatible pipelines

###  Bias Mitigation
- **T5-Base and T5-Large** – Trained to rewrite biased sentences into neutral ones
- Evaluation Metrics:
  - **ROUGE-1, ROUGE-2, ROUGE-L**
  - **Content Preservation Score**

---

##  Project Flow

1. **Input**: Raw news article (title + content)
2. **Preprocessing**: Clean, tokenize, concatenate text
3. **Bias Detection**: Fine-tuned BERT classifies as left/center/right
4. **Explainability**: SHAP/LIME visualize important tokens
5. **Bias Mitigation**: T5 rewrites biased content into neutral form
6. **Evaluation**: Metrics (ROUGE, Content Score), qualitative comparison

---

##  Datasets

-  **[Article-Bias-Prediction Dataset](https://github.com/ramybaly/Article-Bias-Prediction)**  
  - 37,554 articles labeled as `left`, `center`, or `right`
  - Used for BERT classification
-  **[Bias-Detection-Combined Dataset](https://huggingface.co/datasets/newsmediabias/news-bias-full-data)**  
  - ~16,000 biased-neutral sentence pairs  
  - Used to train T5 for rewriting

---

##  Results Summary

| Component        | Model          | Accuracy / Score |
|------------------|----------------|------------------|
| Bias Detection   | BERT-Base      | **92.78%** accuracy |
| Explainability   | SHAP + LIME    | Token-level rationale aligns with ideological cues |
| Bias Mitigation  | T5-Base        | ROUGE-1: 0.6053, Content Score: 0.6022 |
| Bias Mitigation  | T5-Large       | More fluent, but lower ROUGE & content retention |

---

## Limitations & Future Work
- T5 outputs showed limited success in altering ideological framing
- Reclassification of rewritten text using BERT yielded minimal label changes
- Future plans:
  - Fine-tune T5 on politically annotated datasets
  - Human-in-the-loop evaluation
  - Use of larger models like T5-XL or GPT-4 for better rewriting quality

---

##  Paper & Code
- Final Paper: [`News_Media_Bias_FinalPaper.pdf`](./News_Media_Bias_FinalPaper.pdf)
- Output Files: Includes plots, visualizations, and rewritten examples
- GitHub Repo: [EAI_News_Media_Bias](https://github.com/Jayasri2021/EAI_News_Media_Bias)

---

## Citation

```

@inproceedings{baly2020we,
author      = {Baly, Ramy and Da San Martino, Giovanni and Glass, James and Nakov, Preslav},
title       = {We Can Detect Your Bias: Predicting the Political Ideology of News Articles},
booktitle   = {EMNLP 2020},
pages       = {4982--4991},
publisher   = {Association for Computational Linguistics},
year        = {2020}
}

```

---

## Contributors

- **Amrutha Kollu**
- **Jayasri Suresh Vani**
- **Mohamed Aarif Mohamed Sulaiman**
