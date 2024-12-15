# FAMSDC

This repository contains the code for the paper "A few-shot learning framework with multi-type attention 
mechanisms predicts synergistic drug combinations" by Yuxun Luo, Pingjian Ding, Lingyun Luo, Cong Shen, 
Wei Liang, and Li Peng.

## Overview

This project implements the FAMSDC model, a few-shot learning framework equipped with multi-type attention 
mechanisms for discovering drug combinations, which can identify therapeutic options even for diseases 
with limited treatment options. Given a few-shot learning set, FAMSDC seeks to develop a metric function 
that predicts synergistic drug combinations by evaluating the input query against the reference data. 

## Requirements

* environment.yaml

## Installation

```angular2html
conda env create -f environment.yml
conda activate FAMSDC
python main.py
```

## Model Architecture

Given a few-shot learning set, the primary objective of FAMSDC is to develop a metric function that enables 
prediction by contrasting the input query with the provided reference. To accomplish this, FAMSDC consist 
of four key components: (1) An embedding pretrained model is trained on large datasets, including 20 
high-quality resources, and can obtain the pretrained representations of drugs and diseases. (2) 
A module with an attention mechanism learns drug combination-relevant representations for individual drugs. 
(3) The enhanced embeddings of individual drugs were input into the multi-head self-attention module to 
obtain the embeddings of triples. (4) The triple in the query set was adaptively compared with the given 
support triples.

## Usage

To train and evaluate the FAMSDC model with 100 diseases under 1-shot scenario, use the following command:

```angular2html
python main.py
```

To train and evaluate the FAMSDC model with 100 diseases under 2-shot scenario, use the following command:

```angular2html
python main.py --train_few 2 --few 2
```


## Results

FAMSDC achieves the best MRR of 0.630 and Hits@1 of 0.492 under the stringent 1-shot scenario.