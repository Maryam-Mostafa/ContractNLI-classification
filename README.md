# ContractNLI-classification
This repository uses transformers for classifying contracts nli problem

![ContractNLI Classification](https://stanfordnlp.github.io/contract-nli/resources/task_overview.png)

## Overview

ContractNLI is a dataset for document-level natural language inference (NLI) on contracts whose goal is to automate/support a time-consuming procedure of contract review. In this task, a system is given a set of hypotheses (such as “Some obligations of Agreement may survive termination.”) and a contract, and it is asked to classify whether each hypothesis is entailed by, contradicting to or not mentioned by (neutral to) the contract.

## Data

The core information in the dataset is:

text: The full document text
spans: List of spans as pairs of the start and end character indices.
annotation_sets: It is provided as a list to accommodate multiple annotations per document. Since we only have a single annotation for each document, you may safely access the appropriate annotation by document['annotation_sets'][0]['annotations'].
annotations: Each key represents a hypothesis key. choice is either Entailment, Contradiction or NotMentioned. spans is given as indices of spans above. spans is empty when choice is NotMentioned.
labels: Each key represents a hypothesis key. hypothesis is the hypothesis text that should be used in NLI.

## Model

I explored the capabilities of two powerful transformer-based models:

DeBERTa: A deep pre-trained transformer model with attention mechanisms to capture intricate relationships between words in the input text.
DiSITBERT: A distilled version of the pre-trained BERT model, which is lighter and faster while maintaining competitive performance.

