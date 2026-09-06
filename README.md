
# Implementation of Text  Summarization
#### NAME : Vedagiri Indu Sree
#### REGISTER NUMBER : 212223230236
## Aim: 
To perform automatic text summarization using Natural Language Processing (NLP) techniques. 

## Algorithm:
Step 1 Import necessary libraries for natural language processing tasks.<BR>
Step 2: Download NLTK resources, including the punkt tokenizer and stopwords.<BR>
Step 3: Define Text Preprocessing Function to tokenize, remove stopwords, and perform stemming.<BR>
Step 4: Define the Text Summarization Function using a simple frequency-based approach.<br>
    - Calculate the frequency of each word in the preprocessed text.<br>
    - Calculate a score for each sentence based on the sum of word frequencies.<br>
    - Select the top N sentences with the highest scores to form the summary.<br>
Step 5: Construct the main program to read the paragraph  and perform text summarization<br>
      - Generate and print the original text.<br>
      - Generate and print the text summary using the  Text Summarization function<br>

      
## Program:
```
import nltk
nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('stopwords')
from nltk.tokenize import sent_tokenize, word_tokenize
from nltk.corpus import stopwords
text = """NLP is a branch of artificial intelligence.
It helps computers understand human language.
NLP is used in chatbots and language translation.
It is also used for sentiment analysis and summarization."""
stop = set(stopwords.words('english'))
words = [w.lower() for w in word_tokenize(text)
         if w.isalnum() and w.lower() not in stop]
freq = nltk.FreqDist(words)
sentences = sent_tokenize(text)
scores = {}
for s in sentences:
    scores[s] = sum(freq[w.lower()] for w in word_tokenize(s)
                    if w.lower() in freq)
summary = sorted(sentences, key=scores.get, reverse=True)[:3]
print("Original Text:")
print(text)
print("\nSummary:")
print(" ".join(summary))
```

## Output

<img width="1162" height="252" alt="image" src="https://github.com/user-attachments/assets/05811bd6-e5b3-4791-a06b-87904b964293" />


## Result:
Thus ,the program to perform the Text summarization is executed sucessfully.


