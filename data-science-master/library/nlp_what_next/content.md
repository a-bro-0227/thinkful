---
title: What's next?
author: Thinkful
team: grading
time: 20 minutes
uuid: 5107e531-22a8-4979-afa1-ce7c33fc1ce9
timeHours: 0.3333333333333333
---

Throughout this module, you learned about the basics of natural language processing and developed some applications to explore how you might use NLP in the real world. More precisely, you did the following:

* Learned how to preprocess and clean text data.
* Learned some language modeling techniques, like bag of words, n-grams, TF-IDF, and word2vec. These are crucial in converting text into numerical form so that you can apply machine-learning methods on text data.
* Explored how you can conduct text classification using numerical representations of text data.
* Developed a simple chatbot.
* Used Markov chains to generate human-like texts.

Although you touched upon a wide range of topics, understanding the ins and outs of how they work will require you to dig deeper into the NLP realm. In this checkpoint, you'll learn about the next steps that you can follow to enhance your understanding and practical expertise in the NLP domain.

## The current state of the art in NLP

The current research and cutting-edge applications of NLP largely rest upon advances in deep learning. Deep learning is a special field in machine learning where the models are *deep* in the sense that inputs pass through several layers before outputs are returned. As a result of this structure, deep-learning models can address problems with millions or even billions of parameters. This means that they can tackle mathematically complex phenomenons like image recognition and natural language understanding, which have too many parameters to simply estimate.

The state of the art for all of the applications that you made throughout the module is based on deep-learning models. *Recurrent neural networks* (RNNs) especially are great for dealing with sequential data like text.

###### To enhance your NLP capabilities, start by mastering deep learning and deep-learning frameworks.

If you want to go further than the content covered here, you can take the following next steps:

1. **Learn a deep-learning framework.** Currently, the two most popular deep-learning libraries out there are *TensorFlow* and *PyTorch*. Although they are both great and quite capable, you should start with learning just one of them. Thinkful recommends learning TensorFlow, starting with *Keras*. Keras is a high-level framework that handles most of the boilerplate code that you need to write on TensorFlow. So, go ahead and start with Keras.

2. **Learn the basics of neural networks.** After you learn about vanilla artificial neural networks, you should have a look at *convolutional neural networks* (CNNs) and *recurrent neural networks* (RNNs). RNNs are especially important in NLP. Specific RNN architectures, like *long short-term memory networks* (LSTMs), are great at learning from sequential data. Since language is sequential data, all types of RNNs and especially LSTMs are considered very important in NLP research and applications.

After you get familiar with deep-learning frameworks and concepts, you can try to replicate all the examples and applications presented in this module using deep-learning models.

## Popular NLP tasks

Natural language processing is a vast field that covers many tasks and problems to solve. However, in recent years some tasks became increasingly important; familiarity with these tasks would be a great asset for any data scientist. 

Here, you'll focus especially on one area of NLP: *language modeling*. As you may recall, language modeling is the task of representing words (or sentences, or even large documents) in a numerical form. Word embeddings that capture the semantics of the words are great recent innovations in NLP, and they paved the way for many of today's astonishing achievements in NLP. In this module, you learned about word2vec and similar word-embedding methods.

In 2018, there were several major achievements related to language modeling. The ELMo, GPT-2, and BERT language models were all proposed in that year, and they attracted significant attention from both academia and industry.

![elmo_and_bert](elmo_bert.png)

You already learned about OpenAI's GPT-2 model in the introduction to this module. The BERT model was proposed by researchers at Google. Currently, it's regarded as the state-of-the-art model in language modeling. Because language models convert text into numerical vectors, their successes hugely affect almost all types of NLP tasks. That's because the numerical vectors (or word embeddings) that they produce are used as inputs for almost all types of NLP tasks. This is why these innovative models are welcomed in the industry.

###### If you can become familiar with at least the basic ideas of these models, it would be a great asset in your portfolio as a data scientist with NLP knowledge. They are all deep-learning models that are trained in an unsupervised manner on very large text corpora.

If you're interested in learning more about these modules, check out this article: [The Illustrated BERT, ELMo, and co. (How NLP Cracked Transfer Learning)](https://jalammar.github.io/illustrated-bert/).

For now, that's all that's important to be aware of. You're now familiar with the fundamentals of NLP and ready to jump into the challenge!
