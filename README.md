### EX6 Information Retrieval Using Vector Space Model in Python
### DATE: 21.04.2025
### AIM: To implement Information Retrieval Using Vector Space Model in Python.
### Description: 
<div align = "justify">
Implementing Information Retrieval using the Vector Space Model in Python involves several steps, including preprocessing text data, constructing a term-document matrix, 
calculating TF-IDF scores, and performing similarity calculations between queries and documents. Below is a basic example using Python and libraries like nltk and 
sklearn to demonstrate Information Retrieval using the Vector Space Model.

### Procedure:
1. Define sample documents.
2. Preprocess text data by tokenizing, removing stopwords, and punctuation.
3. Construct a TF-IDF matrix using TfidfVectorizer from sklearn.
4. Define a search function that calculates cosine similarity between a query and documents based on the TF-IDF matrix.
5. Execute a sample query and display the search results along with similarity scores.

### Program:

    import requests
    from bs4 import BeautifulSoup
    from sklearn.feature_extraction.text import TfidfVectorizer
    from sklearn.metrics.pairwise import cosine_similarity
    from nltk.tokenize import word_tokenize
    from nltk.corpus import stopwords
    import string
    import nltk

    nltk.download('punkt')
    nltk.download('stopwords')

###### Sample documents stored in a dictionary
    documents = {
        "doc1": "This is the first document.",
        "doc2": "This document is the second document.",
        "doc3": "And this is the third one.",
        "doc4": "Is this the first document?",
    }

###### Preprocessing function to tokenize and remove stopwords/punctuation
    def preprocess_text(text):
        tokens = word_tokenize(text.lower())
        tokens = [token for token in tokens if token not in stopwords.words("english") and token not in               string.punctuation]
        return " ".join(tokens)

###### Preprocess documents and store them in a dictionary
    preprocessed_docs = {doc_id: preprocess_text(doc) for doc_id, doc in documents.items()}

###### Construct TF-IDF matrix
    tfidf_vectorizer = TfidfVectorizer()
    tfidf_matrix = tfidf_vectorizer.fit_transform(preprocessed_docs.values())

###### Calculate cosine similarity between query and documents
    def search(query, tfidf_matrix, tfidf_vectorizer):
        //TYPE YOUR CODE HERE

###### Get input from user
    query = input("Enter your query: ")

###### Perform search
    search_results = search(query, tfidf_matrix, tfidf_vectorizer)

###### Display search results
    print("Query:", query)
    for i, result in enumerate(search_results, start=1):
        print(f"\nRank: {i}")
        print("Document ID:", result[0])
        print("Document:", result[1])
        print("Similarity Score:", result[2])
        print("----------------------")

###### Get the highest rank cosine score
    highest_rank_score = max(result[2] for result in search_results)
    print("The highest rank cosine score is:", highest_rank_score)

### Output:

![lab 61](https://github.com/user-attachments/assets/4b32efdd-49d3-4f0f-a25b-b2e0a8e6db3c)
![lab 62](https://github.com/user-attachments/assets/3597242f-74d0-46df-8354-1ca57f90ac06)
![lab 63](https://github.com/user-attachments/assets/fb316d25-3a18-488d-984e-ea01bfdaaafb)

### Result:
Thus the implementation Information Retrieval Using Vector Space Model in Python is successfullly executed.
