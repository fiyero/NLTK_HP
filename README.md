# Apply NLTK analysis on Harry Potter Series :smile:
https://medium.com/@patrickhk/practice-ntlk-word2vec-pca-wordcloud-jieba-on-harry-potter-series-and-chinese-content-ca6f845b3293

I will briefly demonstrate how to apply NLTK (Natural Language Toolkit) and Word2Vec to do some basic analysis on Harry Potter Series, then visualize the relation of word vectors by PCA/wordcloud.

## Data
Prepare Harry Potter corpus in txt, can obtain the txt from google directly or converting from pdf. Notice we may have encoding error therefore I suggest to open with encoding=”utf-8" to avoid potential encoding issue.<br/>
![data](https://cdn-images-1.medium.com/max/800/1*85-OgPVoaHpekPEvF2Xh5w.png)

## Apply NLTLK library for tokenization and data cleansing
Depend on how you read the txt, most commonly the content is just a string. We can choose to tokenize it into a list of words or sentences by using nltk.word_tokenize(content) or nltk.sent_tokenize(content).<br/>
![p2](https://cdn-images-1.medium.com/max/1200/1*qkXt9Jhy50q6GyseHaKf2g.png)<br/>
![p3](https://cdn-images-1.medium.com/max/800/1*3AA7NAwd3AP1saBBaNSgsw.png)<br/>
![p4](https://cdn-images-1.medium.com/max/1200/1*qMzHoua9IlJ8WmJTx13GrQ.png)<br/>
In NLP we have a term “stopwords” to describe commonly used but not semantically meaningful words, such as “and” , “ to”, “this”. We can filter away these words to avoid incorrect interpretation. We can access the list of stopwords by nltk.corpus.stopwords. We can create custom stopwords list. Here are some examples:<br/>
![p5](https://cdn-images-1.medium.com/max/800/1*f7_bS5og7MsvpY7SJqWIvw.png)<br/>
After that we can apply some basic statistic to obtain the following information, such as number words, sentence, lexical diversity, dispersion plot.etc.<br/>
![p6](https://cdn-images-1.medium.com/max/800/1*50IMFOrl6oA6Sge89Ax_kg.png)<br/>

## Dispersion plot
I like the build-in dispersion plot function so much. It can visualize the occurrence of specific words along the whole corpus. From the plot we have a rough idea of the relative importance of characters. (Assume important character occurs more frequently in the corpus). Most of us we have already familiarized with the plot and characters in Harry Potter.

Imagine for a person who have never read Harry Potter, he can still guess Harry is the most important character while Ron, Hermione and Hagrid are likely important as well.<br/>
![p7](https://cdn-images-1.medium.com/max/800/1*6fGHRFmX9e9FphQtXCjaaw.png)<br/>
Let’s repeat the above basic analysis on all the 7 books of Harry Potter and do some comparisons.

## Total words count after removing punctuation:
![p8](https://cdn-images-1.medium.com/max/800/1*fX-NhyMyi0ahzLu-WKkkNw.png)

## Average sentence length:
The average sentence length have similar shape to the above total word count graph except book 4 Harry Potter and the Goblet of Fire.<br/>
![p9](https://cdn-images-1.medium.com/max/800/1*r3CGbT6KozfkQ9BMfKU9Rw.png)

## Lexical diversity:
Lexical diversity is directly proportional to the diversity of vocab. It is the ratio of number of unique words/ number of words. Surprisingly the first few episodes have higher lexical diversity, this is probably due to the much lower number of words, almost half of the amount to the last few episodes(less repeated words). Therefore if someone wants to learn English by reading Harry Potter, the second book Harry Potter and the Chamber of Secrets maybe the best time-efficient choice.<br/>
![p10](https://cdn-images-1.medium.com/max/800/1*xVZ_G4g4NBKFNAQf6ncx5g.png)

### Discrepancy of the word counts from the official number ?
![p11](https://cdn-images-1.medium.com/max/800/1*Q0LA_gzaxeW_e08gLbN_6g.png)<br/>
This is probably due to NLTK tokenization error. Whenever NLTK encounters words with “n’t”, it tends to tokenize the word into two separate words. As you can see in the below picture “didn’t” is tokenized into “did” and “n’t”, instead of “didn’t”. Different tokenization method has their own pros and cons, use them depend on your situation. Sometime text.split() with regular expression can perform pretty well.<br/>

-------------------------------------------------------------------------------------------------------------------------------------
### More about me
[[:pencil:My Medium]](https://medium.com/@patrickhk)<br/>
[[:house_with_garden:My Website]](https://www.fiyeroleung.com/)<br/>
[[:space_invader:	My Github]](https://github.com/fiyero)<br/>
