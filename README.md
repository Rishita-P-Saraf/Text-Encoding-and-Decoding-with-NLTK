# Text Encoding and Decoding with NLTK

This project demonstrates how to preprocess text, build vocabularies, encode sentences into numeric form, and decode them back into text using **NLTK**.  
It shows two approaches:
1. **Encoding without stopwords**  
2. **Encoding with all words (including stopwords and single-character words)**  

---

## 📌 Requirements
Install the required libraries before running the code:
```python
pip install nltk
```

Additionally, download NLTK resources:
```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
```
---

## 🚀 Approach 1: Encoding Without Stopwords

Steps:

1. Preprocess Text
   - Remove references like [25], [f], and extra symbols.
   - Tokenize into sentences and words.
   - Remove stopwords and keep words of length ≥ 2.

2. Build Vocabulary
   ```python
    vocab = list(set(words))
    word_to_num = {word: i+1 for i, word in enumerate(vocab)}
    num_to_word = {i+1: word for i, word in enumerate(vocab)}

   ```
3. Encoding Sentences
   ```python
    data = []
    for sent in sent_tokenize(corpus):
        temp = []
        for word in word_tokenize(sent):
            if (word.lower() not in stopwords.words("english")) and (len(word) >= 2):
                temp.append(word_to_num[word.lower()])
        data.append(temp)

   ```
4. Decoding Sentences
   ```python
    for sent in data:
    print(" ".join(num_to_word[idx] for idx in sent))

   ```
✅ Output Example
```css
india officially republic india hindi bhārat gaṇarājya country south asia
seventh-largest country area second-most populous country populous democracy world
bounded indian ocean south arabian sea southwest bay bengal southeast shares land borders pakistan west china nepal bhutan north bangladesh myanmar east
indian ocean india vicinity sri lanka maldives andaman nicobar islands share maritime border thailand myanmar indonesia
 ```

---

## 🚀 Approach 2: Encoding With All Words (No Stopword Removal)

Steps:

1. Preprocess Text
   - Retain all words (including stopwords and single-character words).
   - Convert everything to lowercase.

2. Build Vocabulary
   ```python
    vocab = list(set(words))
    word_to_num = {word: i+1 for i, word in enumerate(vocab)}
    num_to_word = {i+1: word for i, word in enumerate(vocab)}

   ```
3. Encoding Sentences
   ```python
    data = []
    for sent in sent_tokenize(corpus):
        temp = []
        for word in word_tokenize(sent):
            temp.append(word_to_num[word.lower()])
        data.append(temp)
    print(data)

   ```
4. Decoding Sentences
   ```python
    for sent in data:
    print(" ".join(num_to_word[idx] for idx in sent))

   ```
✅ Output Example
```css

india officially republic india hindi bhārat gaṇarājya country south asia
seventh-largest country area second-most populous country populous democracy world
bounded indian ocean south arabian sea southwest bay bengal southeast shares land borders pakistan west china nepal bhutan north bangladesh myanmar east
indian ocean india vicinity sri lanka maldives andaman nicobar islands share maritime border thailand myanmar indonesia
 ```

---

## 📂 Repository Structure
```bash
├── WordCloud.ipynb         # Jupyter Notebook with full implementation
├── README.md               # Project documentation
```
---

## 📖 References
- https://www.nltk.org/
- https://machinelearningmastery.com/clean-text-machine-learning-python/
---

## ✨ Author

Rishita Priyadarshini Saraf

mail: rishitasarafp@gmail.com
