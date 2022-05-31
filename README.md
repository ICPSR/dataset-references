# dataset-references

The code in this repository is used to train and apply a Named Entity Recognition (NER) model to detect informal references to datasets in academic literature. The labeled data are derived from the [ICPSR Bibliography of Data-Related Literature](https://www.icpsr.umich.edu/web/pages/ICPSR/citations/) and the [Semantic Scholar Open Research Corpus](https://github.com/allenai/s2orc). This analysis supports the paper, [A Natural Language Processing Pipeline for Detecting Informal Data References in Academic Literature](https://arxiv.org/abs/2205.11651).

## code/ner-demo.ipynb
Demonstration notebook of NER model applied to a paper

## code/spacy-ner.ipynb
Training workflow for spaCy NER model using labeled data

## config.cfg
NER model training parameters

## data/
Datasets are sentences from academic articles named for sources from which they are derived. Training data were labeled, merged, and exported from [Prodigy](https://prodi.gy/docs/named-entity-recognition) as of May 10, 2022 for use in [spaCy](https://spacy.io/usage/training) with the following recipes:
* prodigy db-in dataset_name /path/to/_data.jsonl
* prodigy ner.manual dataset_name --label DATASET
* prodigy data-to-spacy train --ner bibliography, paperpile, s2orc
