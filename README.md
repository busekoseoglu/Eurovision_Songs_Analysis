# Eurovision Songs Analysis

In this project, the songs competing in Eurovision were examined. The aim of the project is to identify the differences between the winning and losing songs and to offer suggestions accordingly.

Project steps:
1. Data Preprocessing
2. Topic Modelling
3. Post-Processing
4. Sentiment Analysis
5. Named Entitiy Recognition
6. Visualization

## Data Preprocessing
### Data Cleaning
Undesirable situations such as special characters, extra spaces, numbers, etc. in the lyrics have been cleaned.

The initial state of the data is as follows.
<img width="1322" alt="image" src="https://github.com/busekoseoglu/Eurovision_Songs_Analysis/assets/44964158/b91a72cc-3953-4e91-a320-e2e2bbc78869">

### Lemmatization
Lemmatization of words in texts provides semantic consolidation by combining word variations. These steps are used to capture semantic similarity at the word level and are often based on grammar rules.

### Removing Stop Words
Stop words are frequently used words such as grammatical conjunctions, prepositions, and pronouns. As these words often do not have semantic significance, they can create noise in the analysis and modeling processes. Stop words removal aims to obtain more focused and meaningful texts by filtering these words.

![image](https://github.com/busekoseoglu/Eurovision_Songs_Analysis/assets/44964158/4e0b380b-4a78-4a20-bf67-b4f65f412801)

## Topic Modelling
### TF-IDF
TfidfVectorizer is a vectorization tool used to perform the "Term Frequency-Inverse Document Frequency" (TF-IDF) conversion. It is a component frequently used in text analysis studies such as topic modeling.

TfidfVectorizer is used to represent text data with a numeric vector. This vectorization process uses TF-IDF scores to determine the importance of words in each document.

TF (Term Frequency) refers to how often a word occurs in a document. The higher the frequency of a word in the document, the more important that word is for that document.

IDF (Inverse Document Frequency) refers to how rare a word is in all documents. Rare words usually carry more information and have more distinctive features.

TfidfVectorizer is a tool for representing text data with a numerical vector and calculating the significance of each word among documents. It is frequently used in text analysis studies such as topic modeling to determine word importance and to make texts comparable.

### LDA
LDA (Latent Dirichlet Allocation) is a probability model used in text datasets and is a widely used method for topic analysis. Topic analysis is a technique used to understand the content of documents and to discover the main themes that represent the documents.

LDA assumes that each document belongs to one or more topics and aims to find the distribution of these topics in the documents. Based on the probability distribution of the documents in the text dataset, LDA tries to find the hidden topics and the distribution of the words they contain.

![image](https://github.com/busekoseoglu/Eurovision_Songs_Analysis/assets/44964158/78a5cc6b-7281-4b71-9ad9-85eacd04c1c0)

## Post-Processing Data
In post-processing, the results from LDA are combined with the main dataframe. While examining the LDA probability results, those below 40% were allocated to a different dataframe. Since this probability ratio was considered low, a different procedure was applied. In this process, if the probability rate of all topics is 20%, the dominant topic of the relevant song is replaced with "mix". If not all of them are 20%, the 2 biggest topics with probability value less than 40% were selected and the dominant topic of the relevant song was created by combining these two topics.

## Sentiment Analysis
Sentiment analysis is a method for understanding and classifying emotional content in data types such as text, audio, or images. Sentiment analysis uses linguistic and statistical methods to determine the emotional state expressed by a text or a user.

Sentiment analysis aims to identify the emotional tone, emotional reactions or emotional states of users in texts. It is often used to describe the three basic categories of emotions, positive, negative, and neutral.

![image](https://github.com/busekoseoglu/Eurovision_Songs_Analysis/assets/44964158/d80133a1-29a5-4c0b-8a84-47597e7e289c)

## NER (Named Entity Recognition)
Named Entity Recognition (NER) is a technique used in natural language processing. NER is used to recognize and label proper names, personal names, organizations, places, dates, currencies and other important entities in texts.

NER uses linguistic and statistical methods to recognize proper nouns or entities that belong to a particular category in a text. These entities are often expressed with words such as nouns, adjectives, verbs, or place names.

## Visualization
![image](https://github.com/busekoseoglu/Eurovision_Songs_Analysis/assets/44964158/4f67b03f-8a2c-4613-a16e-52f877d55cfa)

The two charts above show the analysis of Country/Nationality names from named entity recognition results by winning and losing songs. These charts show that songs with Country/Nationality-related words are more likely to be among the losing songs. For this reason, care should be taken not to mention the name of any nation or country while writing the songs.














