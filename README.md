# Polish texts summarization with fine-tuned mT5
The goal of this project is to efficiently fine-tune multilingual transformer T5 to create accurate summaries of Polish texts.

## Methods
Fine-tuned was small version of [mT5](https://huggingface.co/google/mt5-small) which was downloaded from [huggingface](https://huggingface.co/) website. Training was conducted on GPU with cuDNN module. The quality of summaries was assessed based on rouge score.

## Dataset
The dataset, [summarization-polish-summaries-corpus](https://huggingface.co/datasets/allegro/summarization-polish-summaries-corpus), was used for fine-tuning. It consists of 21,666 news articles on various topics such as politics, sports or economics and their summaries. Each text has about 1,000 words, however summaries have few hundred words. All summaries were abstractive. Dataset was pre-divided into training set (15,598), validation set (1,734) i test set (4,334). 

## Description
Pretrained model and dataset were loaded into Jupyter Notebook. First, vanilla model was evaluated on example entry in dataset. Initial results were **unsatisfactory** as most of the generated summary was masked what suggested that fine-tuning is needed. Text data was tokenized and texts' lenghts were levelled out by truncation or padding. Next, collator was initilized to enable **teach forcing** in decoder section.  
