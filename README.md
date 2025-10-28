# GE1556 PROJECT

This project compares the attention mechanisms of three popular Transformer architectures: **BERT**, **DistilBERT**, and **RoBERTa**. The goal is to analyze and visualize how these models process textual information differently through their attention patterns.

## Dataset
[Hugging Face](https://huggingface.co/datasets/fancyzhx/ag_news)

The project uses the **AG News** dataset containing news articles classified into 4 categories **World**, **Sports**, **Business**, **Sci/Tech**

## Models

### 1. BERT (bert-base-uncased)
[Hugging Face](https://huggingface.co/google-bert/bert-base-uncased)
- **Description**: Original model from Google
- **Architecture**: 12 layers, 12 attention heads, 110M parameters
- **Use case**: Baseline reference, general purpose

### 2. DistilBERT (distilbert-base-uncased)
[Hugging Face](https://huggingface.co/distilbert/distilbert-base-uncased)
- **Description**: Compressed version of BERT (by Hugging Face)
- **Architecture**: 6 layers, 12 attention heads, 66M parameters
- **Use case**: Deployment under resource constraints

### 3. RoBERTa (roberta-base)
[Hugging Face](https://huggingface.co/FacebookAI/roberta-base)
- **Description**: Optimized BERT (by Facebook AI)
- **Architecture**: 12 layers, 12 attention heads, 125M parameters
- **Use case**: High performance on NLP tasks

## Attention Metrics

The notebook analyzes 4 main metrics:

### 1. **CLS Attention Max**
Measures the maximum attention given to the [CLS] token, which aggregates information from the entire sentence.
- *High value* → strong global aggregation

### 2. **Self-Attention Mean**
Average of self-attention (a token attending to itself).
- *High value* → strong local information retention

### 3. **Content/Function Ratio**
Ratio of attention given to content words vs function words.
- *High value* → focus on meaning rather than syntax

### 4. **Attention Entropy**
Measures the dispersion of attention.
- *High entropy* → diffuse attention (distributed)
- *Low entropy* → focused attention (targeted)

## What is Attention?

**Attention** is a mechanism that allows a model to focus on relevant parts of a sequence. In a Transformer:

- Each token "looks at" other tokens to understand context
- **Attention heads** capture different linguistic aspects
- **Layers** progressively refine understanding:
  - Lower layers → syntax, grammar
  - Middle layers → semantic relations
  - Upper layers → aggregation for final task

## Installation 

1. **Clone the repository**
```bash
git clone https://github.com/yaaks7/GE1356_SDSC1001_project.git
cd GE1356_SDSC1001_project
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Launch the notebook**
```bash
jupyter notebook attention-comparison.ipynb
```


## References

- [BERT Paper](https://arxiv.org/abs/1810.04805)
- [RoBERTa Paper](https://arxiv.org/abs/1907.11692)
- [DistilBERT Paper](https://arxiv.org/abs/1910.01108)
- [BertViz Documentation](https://github.com/jessevig/bertviz)
- [AG News Dataset](https://huggingface.co/datasets/ag_news)
- [Attention is all you need](https://arxiv.org/abs/1706.03762)

