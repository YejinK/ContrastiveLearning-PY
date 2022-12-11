# Neural Network Project / Fall 2022

## Our group would like to explore deep learning in the context of language models. Specifically, we aim to:
* Explain the concept of word embeddings and how they can be extended for static sentence embeddings in NLP applications.
* Discuss the architecture of transformer networks and transition to transformers-based pre-trained language models (BERT) model.
* Deal with supervised/unsupervised contrastive learning on BERT and talk about the paper (SimCSE).

## For this project, we would like to demonstrate and show:
* How we can embed sentences using libraries from static word embedding like word2vec to contextualized embedding like BERT.
* Utilize a pre-trained model BERT framework and run an evaluation on various downstream tasks.
* Introduce the SimCSE model and fine-tune the BERT using a SimCSE objective function
* Compare those models on the benchmark evaluation dataset.
    - Since the semantic textual similarity tasks are already reported by the SimCSE paper, our aim is to augment these benchmarks and and obtain performance evaluation in a different aspect using Faiss (not only semantical evaluation but also speed-wise aspect; search time, search quality, memory used per index vector, training time, etc.).
    
## Experimental Process
1. We aim to train an informal text corpus through the simCSE framework using 5M tweets; to make the proposed model robust on casual text.
2. We will then run the model through SentEval(https://github.com/facebookresearch/SentEval) which can provide us an accuracy score through a series of benchmarked tests.
3. We will then load and process our model within Faiss(https://github.com/facebookresearch/faiss) and perform comparative search against Bert and other Bert variants.

## Quick Start
* We added a notebook for quick training and evaluation of our experiment process: [Colab_SimCSE_unsup_bert_uncased_train_tweets.ipynb](https://github.com/YejinK/contrastive-learning-yk-pg/blob/main/Colab_SimCSE_unsup_bert_uncased_train_tweets.ipynb)

## Model trained on Tweet and Tweet + Wikidata
* [SimCSE-BERT(base)-only-tweet](https://drive.google.com/drive/folders/1-0HTc0GdLE3khwJiyYJLPjXtTvT7zUg4?usp=sharing)
* [SimCSE-BERT(base)-wiki-tweet]()

## Dataset
#### Retrain SimCSE (Unsupervised)
* 5M tweets: https://drive.google.com/drive/folders/1OPNicSQnr3kbnCr6ajcehZiCRFY36URe?usp=share_link (original dataset: https://tweetsets.library.gwu.edu/)

## Result
### Semantic Text Similarity tasks

|Model| STS12 | STS13 | STS14 | STS15 | STS16 | STSB | SICKR |  Avg. |
|----|------|---|---|------|---|---|------|---|
|BERT(base)| xx.96 | 80.79 | 71.50 | 79.49 | 76.21 |    75.25     |      67.92      | 74.16|
|SimCSE-BERT(base)-only-wiki| 68.4	| 82.41	|74.38	|80.91	|78.56	|76.85|	72.23	|76.25|
|SimCSE-BERT(base)-only-tweet| 67.96 | 80.79 | 71.50 | 79.49 | 76.21 |    75.25     |      67.92      | 74.16|
|SimCSE-BERT(base)-wiki-tweet| 69.27 | 81.54 | 74.42 | 82.43 | 77.59 |    77.78     |      70.78      | 76.26|

### Transfer tasks
|Model|   MR  |   CR  |  SUBJ |  MPQA |  SST2 |  TREC |  MRPC |  Avg. |
|----|------|---|---|------|---|---|------|---|
|BERT(base)| xx.54 | 84.96 | 94.38 | 88.52 | 83.91 | 87.40 | 72.52 | 84.60 |
|SimCSE-BERT(base)-only-wiki| 81.18	|86.46	|94.45|	88.88	|85.50	|89.80|	74.43	|85.81 |
|SimCSE-BERT(base)-only-tweet| 80.54 | 84.96 | 94.38 | 88.52 | 83.91 | 87.40 | 72.52 | 84.60 |
|SimCSE-BERT(base)-wiki-tweet| 77.85 | 82.54 | 93.04 | 87.72 | 82.26 | 81.00 | 75.54 | 82.85 |

### Search tasks

|Model|Memory|Avg. search time|MRR|
|------|---|---|------|
|BERT(base)|0.25|0.0175|0.52|
|SimCSE-BERT(base)-only-wiki|0.25|0.0164|0.64|
|SimCSE-BERT(base)-only-tweet|0.25|0.0167|0.64|
|SimCSE-BERT(base)-wiki-tweet|0.25|0.0164|0.65|

