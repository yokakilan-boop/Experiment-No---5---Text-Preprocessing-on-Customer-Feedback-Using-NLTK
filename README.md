# DSWP-Experiment-5-Text-Preprocessing-on-Customer-Feedback-Using-NLTK

## Aim
To perform fundamental Natural Language Processing (NLP) text preprocessing steps—including tokenization, punctuation filtering, stopword removal, and lemmatization—on customer feedback text using Python's `nltk` library.

## Algorithm

1. **Start** the program.
2. **Import Libraries**: Import `nltk` along with `word_tokenize` (from `nltk.tokenize`), `stopwords` (from `nltk.corpus`), and `WordNetLemmatizer` (from `nltk.stem`).
3. **Download NLTK Resources**: Download the required tokenizer models and lexical corpora (`punkt`, `punkt_tab`, `stopwords`, and `wordnet`) using `nltk.download()`.
4. **Define Input Text**: Store the sample customer feedback paragraph in a string variable `text` and display the original text.
5. **Tokenize Text**: Split `text` into individual word and punctuation tokens using `word_tokenize(text)`.
6. **Filter Punctuation & Remove Stopwords**:
   * Load the English stopword set via `set(stopwords.words('english'))`.
   * Retain only alphabetic tokens (`word.isalpha()`) whose lowercase forms are not present in `stop_words`.
7. **Lemmatize Tokens**:
   * Initialize `WordNetLemmatizer()`.
   * Convert each filtered token to lowercase and reduce it to its base dictionary form using `lemmatizer.lemmatize(word.lower())`.
8. **Display Preprocessed Outputs**: Print the tokenized list, stopword-filtered tokens, and final lemmatized words.
9. **Stop** the program.

## Functions and Methods Used

| Category | Function / Class | Purpose / Description |
| :--- | :--- | :--- |
| **Resource Management** | `nltk.download()` | Downloads required NLTK tokenizers (`punkt`, `punkt_tab`) and corpora (`stopwords`, `wordnet`) |
| **Tokenization** | `word_tokenize()` | Splits raw text into individual word and punctuation tokens |
| **Text Filtering** | `stopwords.words('english')` | Retrieves standard English stopwords for noise reduction |
| | `str.isalpha()` & `str.lower()` | Filters out punctuation/numeric tokens and standardizes text casing |
| **Lemmatization** | `WordNetLemmatizer()` | Initializes the WordNet morphological analyzer |
| | `lemmatizer.lemmatize()` | Converts inflected words into their canonical base dictionary forms |

## Program
## Input 1
```
# Text Preprocessing: Tokenization, Stopword Removal, and Lemmatization using NLTK
import nltk
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize
from nltk.stem import WordNetLemmatizer

# Step 1: Download NLTK resources
nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('stopwords')
nltk.download('wordnet')
```
## Output 1
```
[nltk_data] Downloading package punkt to /root/nltk_data...
[nltk_data]   Unzipping tokenizers/punkt.zip.
[nltk_data] Downloading package punkt_tab to /root/nltk_data...
[nltk_data]   Unzipping tokenizers/punkt_tab.zip.
[nltk_data] Downloading package stopwords to /root/nltk_data...
[nltk_data]   Unzipping corpora/stopwords.zip.
[nltk_data] Downloading package wordnet to /root/nltk_data...
```
## Input 2
```
# Step 2: Sample customer feedback text
text = """The product quality is excellent and the delivery service was very fast.
However, the packaging could have been better."""

print("---- Original Text ----")
print(text)
```
## Output 2
```
---- Original Text ----
The product quality is excellent and the delivery service was very fast.
However, the packaging could have been better.

```
## Input 3
```
# Step 3: Tokenization
tokens = word_tokenize(text)
print("\nTokenized Words:")
print(tokens)
```

## Output 3
```
Tokenized Words:
['The', 'product', 'quality', 'is', 'excellent', 'and', 'the', 'delivery', 'service', 'was', 'very', 'fast', '.', 'However', ',', 'the', 'packaging', 'could', 'have', 'been', 'better', '.']
```
## Input 4
```
# Step 4: Stopword Removal & Punctuation Filtering
stop_words = set(stopwords.words('english'))
filtered_tokens = [
    word for word in tokens
    if word.lower() not in stop_words and word.isalpha()
]
print("\nAfter Stopword Removal:")
print(filtered_tokens)
```
## Output 4
```
After Stopword Removal:
['product', 'quality', 'excellent', 'delivery', 'service', 'fast', 'However', 'packaging', 'could', 'better']

```
## Input 5
```
# Step 5: Lemmatization
lemmatizer = WordNetLemmatizer()
lemmatized_words = [lemmatizer.lemmatize(word.lower()) for word in filtered_tokens]
print("\nAfter Lemmatization:")
print(lemmatized_words)
```
## Output 5
```
After Lemmatization:
['product', 'quality', 'excellent', 'delivery', 'service', 'fast', 'however', 'packaging', 'could', 'better']
```


## Result
The program successfully performed tokenization, punctuation filtering, stopword removal, and lemmatization on the customer feedback text using the NLTK library.
