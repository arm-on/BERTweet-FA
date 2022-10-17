BERTweet-FA: A pre-trained language model for Persian (a.k.a Farsi) Tweets
---

BERTweet-FA is a transformer-based model trained on 20665964 Persian tweets. The model has been trained on the data only for 1 epoch (322906 steps), and yet it has the ability to recognize the meaning of most of the conversational sentences used in Farsi. Note that the architecture of this model follows the original BERT [[Devlin et al.](https://arxiv.org/abs/1810.04805)].

How to use the Model
---
```python
from transformers import BertForMaskedLM, BertTokenizer, pipeline
model = BertForMaskedLM.from_pretrained('arm-on/BERTweet-FA')
tokenizer = BertTokenizer.from_pretrained('arm-on/BERTweet-FA')
fill_sentence = pipeline('fill-mask', model=model, tokenizer=tokenizer)
fill_sentence('اینجا جمله مورد نظر خود را بنویسید و کلمه موردنظر را [MASK] کنید')
```

The Training Data
---
The first version of the model was trained on the "[Large Scale Colloquial Persian Dataset](https://iasbs.ac.ir/~ansari/lscp/)" containing more than 20 million tweets in Farsi, gathered by Khojasteh et al., and published on 2020.

Evaluation
---

| Training Loss | Epoch | Step  |
|:-------------:|:-----:|:-----:|
| 0.0036        | 1.0   | 322906 |

Contributors
---
- Arman Malekzadeh [[Linkedin](https://www.linkedin.com/in/arman-malekzadeh/)] [[Github](https://github.com/arm-on)]
