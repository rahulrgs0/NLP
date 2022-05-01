# NLP
Basic NLP codes
TOKENIZATION
WORD TOKENIZATION

text = "I am Rahul"
text.split()

text = "Natural language processing is the driving force behind machine intelligence . NLP refers to the branch of artificial intelligence."
text.split(' . ') 

TOKENIZATION USING REGULAR EXPRESSION (re)

import re

text = "Natural language processing is the driving force behind machine intelligence . NLP refers to the branch of artificial intelligence."
text= re.compile('[.?!]').split(text)
text

import nltk

from nltk.tokenize import word_tokenize

nltk.download("punkt")

text = "Natural language processing is the driving force behind machine intelligence . NLP refers to the branch of artificial intelligence."
word_tokenize(text)

from nltk.tokenize import sent_tokenize
text = "Natural language processing is the driving force behind machine intelligence . NLP refers to the branch of artificial intelligence."
sent_tokenize(text)

TOKENIZATION USING KERAS

import keras

from keras.preprocessing.text import text_to_word_sequence
text = "Natural language processing is the driving force behind machine intelligence . NLP refers to the branch of artificial intelligence."
text1 = text_to_word_sequence(text)
text1

TOKENIZATION USING GENSIM

import gensim

from gensim.utils import tokenize

text = "Natural language processing is the driving force behind machine intelligence . NLP refers to the branch of artificial intelligence."
list(tokenize(text))

STEMMING

from nltk.stem import PorterStemmer
porter = PorterStemmer()
words = ['Connects','Connecting','Connected','Connections']
for word in words:
    print(word,"--->",porter.stem(word))
    
SNOWBALL STEMMER()

from nltk.stem import SnowballStemmer
snowball = SnowballStemmer(language='english')
words = ['generous','generate','generously','generation']
for word in words:
    print(word,"--->",snowball.stem(word))
    
    from nltk.stem import LancasterStemmer
lancaster = LancasterStemmer()
words = ['eating','eats','eaten','puts','putting']
for word in words:
    print(word,"--->",lancaster.stem(word))
    
    LEMMATIZATION
    
    from textblob import TextBlob,Word
    
    nltk.download('wordnet')
    
    listofwords = ['Connecting' , 'Puts' , 'Generation' , 'Refers']
    
    for word in listofwords:
  w = Word(word)
  print(word + '--->' + w.lemmatize())
  
  from nltk.stem import WordNetLemmatizer
  
  wn1=WordNetLemmatizer()
  
  for words in listofwords:
  print(words + '--->' + wn1.lemmatize(words))
  
  import en_core_web_sm
  
  nlp = en_core_web_sm.load()
  
  sent1 = nlp("I like to open my mind, but my mouth in a general discussion.")
sent2 = nlp("I like to open my mind, but not my mouth in a general discussion.")
print(sent2.similarity(sent1))

nltk.download('stopwords')

import nltk
from nltk.corpus import stopwords

print(stopwords.words('english'))

stop_words = set(stopwords.words('english'))
from nltk.tokenize import word_tokenize
word_tokens_1= word_tokenize("I like to open my mind, but my mouth in a general discussion.")
word_tokens_1

new_sent_1=[w for w in word_tokens_1 if w.lower() not in stop_words]
new_sent_1 = ' '.join(str(elem) for elem in new_sent_1)
print(new_sent_1)

word_tokens_2= word_tokenize("I like to open my mind, but not my mouth in a general discussion.")
new_sent_2=[w for w in word_tokens_1 if w.lower() not in stop_words]
new_sent_2 = ' '.join(str(elem) for elem in new_sent_2)
print(new_sent_2)

new_sent_1 = nlp(new_sent_1)
new_sent_2 = nlp(new_sent_2)
print(new_sent_2.similarity(new_sent_1))



    
    
