# Fake News Classifier

## Introduction

The problem of fake news has been ever increasing with the booming age of internet where thoughts, and information can be conveyed to the whole world with a single press of a button. Fake news are spread everywhere, by everyone, knowingly or unknowingly, from whatsapp messages of our uncles to even large media houses. False information is shared with intentions of political gain or for spreading propaganda against particular casts, creed, race or religion, hence this is a very critical issue in today’s world. <br/>
We present the solution to the task of differentiating the fake news from authentic ones by using Deep Learning architectures. Automated detection of fake news is a hard task to accomplish as it requires the model to not only understand nuances in natural language, but also understand how related or unrelated the reported news is when compared to real news, instead of a binary classification task. To address these gaps, we present a Neural Network architecture combined with Natural Language Processing techniques to accurately predict the stance for a given news article.

## Dataset
To train our Neural Network for this task, we have used two datasets which comprise of news articles from the time of US Presidential election of 2016 from various media houses and sources.
1. [Fake News from Kaggle](https://www.kaggle.com/c/fake-news/data)
2. [Fake real news_dataset from GitHub](https://github.com/joolsa/fake_real_news_dataset)
<br/>
These two datasets have been merged together to create a larger dataset for training and validation with a random shuffle and a test split ratio of 0.35 (this is relatively high to counter overfitting). You can find the merged dataset <a href="https://drive.google.com/file/d/1SiM34MdY4U_Yj0L8kMdhuffykkJvu-0F/view?usp=sharing>here</a>.
### Exploratory Data Analysis
1. Event Rates
- Train Dataset:  0(Real) - 10333(49.24%)   1(Fake) - 10654(50.76%)
- Test Dataset: 0(Real) - 5564(49.23%)   1(Fake) - 5738(50.769%)   
- Overall: 0(Real) - 15897(49.16 %)  1(Fake) - 16428(50.84 %)
2. Sentiment Analysis of Dataset -
- We trained the model with only CNN backbone on IMDB movie rating dataset with labels being 1 and 0 i.e. Positive and Negative.
- On doing the Sentiment classification on the text of our fake news dataset, we find that 65.3% of the news are negative news and 34.7% are positive news.
3. Word Count Boxplot -  
- Mean Word count is 446.307
- Minimum word count is 0
- Maximum word count is 4849
- 25% words have word count less than 163
- 75% words have word count less than 621
- Standard Deviation of the word count is 428.3

## Preprocessing and Text Cleaning

The text from every news article is processed before being fed into the model for training. The following steps were done in sequence. These tasks were performed using Regex and NLTK libraries.
- Removal of null and NAN values
- Removal of website links and URLs
- Removal of email addresses
- Removal of html tags and punctuation marks
- Removal of numerical characters and non ASCII characters
- Lower casing of all the words
- Removal of stopwords
- Removal of extra white-spaces in between all the words
- Tokenization of dataset (breaking the text into lists of words)
<br/>
The notebook GNR652_Fake_News_Detection_DL_preprocessing.ipynb in the [src](https://github.com/laddhashreya2000/Fake_News_Detection/tree/master/src) folder contains the code.

## Model Building

Our Neural Network comprises of 6 different kinds of layers, they are as follows:
- Word Embedding Layer: Responsible for converting words into tensors
- Convolutional layer: Generates patterns and connections between word-vectors
- Max Pooling layer: Picks out significant patterns, feature space is compressed
- LSTM layer: Just like a modified RNN layer, controls flow of information and patterns
- Dense layer: Ensures connection between all the above formed patterns
- Dropout layer: Responsible for regularization
<br/>
The notebook GNR652_Fake_News_Detection_Model_building_ (1).ipynb in the [src](https://github.com/laddhashreya2000/Fake_News_Detection/tree/master/src) folder contains the code.

## Results

The model was trained for 100 epochs. The [imgs](https://github.com/laddhashreya2000/Fake_News_Detection/tree/master/imgs) folder contains the accuracy and loss plots. Prediction accuracy is 89.60 % on test dataset and  93.74 % on train dataset.

## Inferences

- Convolution neural network layer along with the word embedding layer, helps to make and identify features or relations between word embeddings. An analogy of these relations is the features that we provide to a single layer Machine Learning model.
- Word Embedding Layer is pretrained (Transfer learning used) where every word is represented by a tensor which can be fed into the model.
- Introducing learning rate decay as opposed to a steady learning rate reduces overfitting.
- Increasing the dropout layer parameter reduces overfitting
- The dataset we used is biased greatly to the US presidential election related news only, any other forms of news are unlikely to be predicted accurately with this model. This model can be made generic by including a lot more data
