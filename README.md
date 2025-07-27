# stemming

Here’s a README file (in Markdown format) for your code. You can name it README.md.

Text Preprocessing using NLTK
This project demonstrates basic Natural Language Processing (NLP) steps using the NLTK library in Python.
 The code performs the following tasks on a given paragraph:
Sentence Tokenization


Word Tokenization


Stopword Removal


Stemming using PorterStemmer



What the Code Does
Imports necessary NLTK modules:


sent_tokenize to split text into sentences.


word_tokenize to split sentences into words.


PorterStemmer for stemming.


stopwords for removing common English words like the, is, of.


Defines a sample paragraph containing multiple sentences.


Processes each sentence:


Tokenizes the sentence into words.


Removes stopwords.


Applies stemming to reduce words to their root form (e.g., running → run).


Joins the processed words back into a string.


Prints the final processed list of sentences.



Code Structure
import nltk
from nltk.tokenize import word_tokenize, sent_tokenize
from nltk.stem import PorterStemmer
from nltk.corpus import stopwords

# Sample paragraph
paragraph = """...text here..."""

# Sentence Tokenization
tokens = sent_tokenize(paragraph)

# Initialize stemmer
stemer = PorterStemmer()

# Process each sentence
for i in range(len(tokens)):
    words = word_tokenize(tokens[i])  # Word Tokenization
    words = [stemer.stem(word) for word in words if word not in set(stopwords.words('english'))]
    tokens[i] = ''.join(words)        # Join back into a single string

print(list(tokens))

Key Concepts
1. Tokenization
Sentence Tokenization: Splits text into sentences.


Word Tokenization: Splits sentences into words or tokens.


2. Stopwords
Words like "the", "is", "and" which don't add meaning to analysis are removed.


3. Stemming
Reduces a word to its base/root form using PorterStemmer.
 Example:
 running → run, studies → studi.



Dependencies
Python 3.x


NLTK library
 Install using:

 pip install nltk


Download required datasets (once):

 import nltk
nltk.download('punkt')
nltk.download('stopwords')



Sample Output
For the given paragraph, the output will be a list of processed sentences with stopwords removed and words stemmed:
['IhavethreevisionforIndia.', 'In3000yearofourhistori,peoplfromallover...', ...]


Possible Improvements
Add lemmatization instead of stemming for better word forms.


Remove punctuation before joining words.


Maintain sentence spacing by using ' '.join(words) instead of ''.join(words).



