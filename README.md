# Neural Network Project / Fall 2023

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