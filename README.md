#  TF-IDF Document Search

A Python-based project for processing and searching text documents from the ACL dataset using TF-IDF (Term Frequency-Inverse Document Frequency) techniques.

##  Features
- Reads and processes `.txt` files from the ACL dataset
- Converts documents to word lists with `wordList(doc)`
- Removes punctuation, newlines, stopwords, and converts to lowercase with `removePuncs(wordList)`
- Computes term frequency (TF) with `termFrequencyInDoc(wordList)`
- Calculates document frequency (DF) with `wordDocFre(dicList)`
- Computes inverse document frequency (IDF) with `inverseDocFre(dicList, base)`
- Generates TF-IDF scores with `tfidf(docList)`
- Ranks top 5 documents for queries with `DocumentSearch(query)`
- Supported queries:
  - LDA
  - Topic modelling
  - Generative models
  - Semantic relationships between terms
  - Natural Language Processing
  - Text Mining
  - Translation model
  - Learning procedures for the lexicon
  - Semantic evaluations
  - System results and combination

##  Dataset
- The full ACL dataset (`ACL txt.zip`) is available online at the [ACL website](https://www.aclweb.org/).
- Due to its large size, a smaller dataset (`small_dataset`) is included in `./small_dataset/`.


##  Code Flow

The project follows a sequential process to compute TF-IDF scores and perform document search:

1. **Read and Preprocess Documents**:
   - Iterate through `.txt` files in the dataset using `wordList(doc)` to create a list of words.
   - Clean the word list with `removePuncs(wordList)` by removing punctuation, newlines, stopwords, and converting to lowercase.

2. **Compute Term Frequency (TF)**:
   - Use `termFrequencyInDoc(wordList)` to calculate the frequency of each word in a document.
   - Formula (centered):
     ```
     TF(t, d) = (Number of times term t appears in document d) / (Total number of terms in document d)
     ```

3. **Compute Document Frequency (DF)**:
   - Use `wordDocFre(dicList)` to count how many documents contain each word.
   - Formula (centered):
     ```
     DF(t) = Number of documents containing term t
     ```

4. **Compute Inverse Document Frequency (IDF)**:
   - Use `inverseDocFre(dicList, base)` to measure the importance of each word across the corpus.
   - Formula (centered):
     ```
     IDF(t) = log(Total number of documents / Number of documents containing term t)
     ```

5. **Compute TF-IDF Scores**:
   - Use `tfidf(docList)` to combine TF and IDF scores for each word in each document.
   - Formula (centered):
     ```
     TF-IDF(t, d) = TF(t, d) * IDF(t)
     ```

6. **Perform Document Search**:
   - Use `DocumentSearch(query)` to rank and return the top 5 documents based on TF-IDF scores for the query.


##  Technologies
- Python 3.x
- Libraries: `os`, `string`, `math`, `collections`

##  Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/https://github.com/afsahurrehman11/NLP-TF-IDF-Search-Pipeline.git
   cd yourrepo
   ```
2. Extract `small_dataset` or download the full ACL dataset from the [ACL website](https://www.aclweb.org/).
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Run the script:
   ```bash
   python main.py
   ```

##  Usage
- Place the dataset (`small_dataset` or full ACL dataset) in the project directory.
- Run the script to process documents and compute TF-IDF scores.
- Search with `DocumentSearch(query)`, e.g.:
  ```python
  DocumentSearch("Natural Language Processing")
  ```
- Outputs top 5 documents ranked by TF-IDF scores.

## Note
- Code is clear and well-commented for readability.
- A predefined stopwords list is required for `removePuncs(wordList)`.
- Refer to the [ACL documentation](https://www.aclweb.org/) for full dataset details.
