# Fake News Classifier
---
## Introduction
The problem of fake news has been ever increasing with the booming age of internet where thoughts, and information can be conveyed to the whole world with a single press of a button. Fake news are spread everywhere, by everyone, knowingly or unknowingly, from whatsapp messages of our uncles to even large media houses. False information is shared with intentions of political gain or for spreading propaganda against particular casts, creed, race or religion, hence this is a very critical issue in today’s world. <br\>
We present the solution to the task of differentiating the fake news from authentic ones by using Deep Learning architectures. Automated detection of fake news is a hard task to accomplish as it requires the model to not only understand nuances in natural language, but also understand how related or unrelated the reported news is when compared to real news, instead of a binary classification task. To address these gaps, we present a Neural Network architecture combined with Natural Language Processing techniques to accurately predict the stance for a given news article.
---
## Dataset
To train our Neural Network for this task, we have used two datasets which comprise of news articles from the time of US Presidential election of 2016 from various media houses and sources.
1. [Fake News from Kaggle](https://www.kaggle.com/c/fake-news/data)
2. [Fake real news_dataset from GitHub](https://github.com/joolsa/fake_real_news_dataset)
These two datasets have been merged together to create a larger dataset for training and validation with a random shuffle and a test split ratio of 0.35 (this is relatively high to counter overfitting). You can find the merged dataset [here](https://drive.google.com/file/d/1SiM34MdY4U_Yj0L8kMdhuffykkJvu-0F/view?usp=sharing).

### Exploratory Data Analysis
1.
- Train Dataset:  0(Real) - 10333(49.24%)   1(Fake) - 10654(50.76%)
- Test Dataset: 0(Real) - 5564(49.23%)   1(Fake) - 5738(50.769%)   
- Overall: 0(Real) - 15897(49.16 %)  1(Fake) - 16428(50.84 %)
2. Sentiment Analysis of Dataset -

---
##
