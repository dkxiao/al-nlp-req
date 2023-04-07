# al-nlp-req
Active Learning for finetuning transformer-based language models for NER within requirements engineering.

## abstract
Automating requirements analysis with natural language processing is critical for handling the ever-increasing number of textual requirements driven by increasing product complexity. Pre-trained language models such as BERT have proven useful for requirements analysis. However, to deploy pre-trained language models, a fully labeled dataset must be created first to finetune language models towards the requirements domain. The creation of a fully labeled dataset, especially for named entity recognition applications, poses a major challenge for industry as it entails high manual labeling effort by requirements engineers. Recent advances of pre-trained language models combined with active learning can significantly reduce the necessary manual labeling effort. To this end, we present a novel approach for integrating active learning with pre-trained language models for named entity recognition on textual requirements. Our approach employs active learning with uncertainty-based query strategies within the model finetuning process to extract requirements entities. We demonstrate the efficacy of this approach on an aerospace requirements dataset, where we reduce the manual requirements labeling effort to 36% while even improving comparable model performance by 3%. By reducing the manual effort, we argue that active learning can shorten the ramp-up time of language model deployment for requirements engineering and enable industrial adoption.

## install
- [pytorch](https://pytorch.org)
- [numpy](https://numpy.org/install/)
- [pandas](https://pandas.pydata.org/)
- [matplotlib](https://matplotlib.org/)
- `pip install transformers` for huggingface transformers 
- `pip install datasets` for huggingface datasets 
- `pip install evaluate` for huggingface evaluate
- `pip install seqeval` for NER evaluation scheme
- `pip install numba` for speeding up code
- `pip install spacy` for NLP processing
- `pip install prodigy` for manual labeling interface

## overview
Overview of repo structure
### 00_main
- `AL-consolidated_evalrun.ipynb` contains main script to perform finetuning with active learning on top of a base BERT model 
### 10_manual labeling
- `labeling_setup.ipynb` open prodigy interface for manual NER labeling
- `display_inference.ipynb` leverages final finetuned model from huggingface hub to label previously unseen requirements sentences
- `postprocess.ipynb` transformation from prodigy labeling format into huggingface datasets format
### 20_visualization
- `final_curve.ipynb` final plotting of learning curves
- `temp_curve.ipynb` temporary plots

### 30_experimental runs
- process documentation of all performed experimental runs

### 40_analyses
- dataset analyses

## acknowledgements
This work is the results of research performed at MIT in cooperation with the RWTH Laboratory of Machine Tools and Production Technology (WZL).