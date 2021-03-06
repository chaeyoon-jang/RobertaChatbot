# Korean Language Consultation Chatbot
Consultation chatbot training by ```pytorch```,```huggingface transformers```,```klue-roberta-base```, [AIHub sentiment conversation dataset](https://aihub.or.kr/aidata/7978) and [Songys's chatbot data](https://github.com/songys/Chatbot_data)

# Background
In 20 May 2021, [KLUE(Korean Language Understanding Evaluation)](https://arxiv.org/pdf/2105.09680.pdf) paper is published. KLUE released the pretrained language models (PLM), KLUE-BERT and KLUE-RoBERTa. 

I want to fine-tuned KLUE-RoBERTa model, masked language model(MLM) to auto regressive task like languge generation task. I know that bert embedding is more effective understanding context than any other models like GPT-2 ect. I want to make conversation chatbot model using bert embedding but, I had hardship in training that model. because bert doesn't have decoder architecture so, it is hard to directly using Generation task. however, I found breakthrough in this paper [Leveraging Pre-trained Checkpoints for Sequence Generation Tasks](https://arxiv.org/pdf/1907.12461.pdf) moreover, this paper providing experiment API in ```huggingface transformers``` 

* KLUE-Roberta-base : using for pre-trained model, tokenizer
* Encoder Decoder Models : used to initialize a sequence-to-sequence model with KLUE-Roberta-base model as the encoder and decoder. 
* Final model is Roberta to Roberta model

# Task
### KLUE-Roberta to Roberta Text Generation 

# How to train
```git clone https://github.com/chaeyoon-jang/RobertaChatbot.git```

```pip install -r requirements.txt```

```python train.py --batch_size=32 --n_epoch=20 --lr=5e-5```

# How to chat
```python print_result.py  --chat=CHAT```
### example
![image](https://user-images.githubusercontent.com/67726968/130641935-5e7b10cd-edef-442a-922f-6732c86a15d3.png)

# How to test
```python print_result.py --test=TEST```

# References
[AIHub sentiment conversation dataset](https://aihub.or.kr/aidata/7978)

[Songys's chatbot data](https://github.com/songys/Chatbot_data)

[Huggingface transformers](https://huggingface.co/transformers/index.html)

[KLUE(Korean Language Understanding Evaluation)](https://arxiv.org/pdf/2105.09680.pdf)

[Leveraging Pre-trained Checkpoints for Sequence Generation Tasks](https://arxiv.org/pdf/1907.12461.pdf) 

