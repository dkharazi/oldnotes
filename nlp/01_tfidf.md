## General Description
- Tf-idf stands for term frequency-inverse document frequency
- Tf-idf is a measurement of how important a given word is in a given document, either in a collection of documents or corpus
- Generally, the importance increases as the frequency of the words in its given document increases, but if offset by the frequency of the word in the corpus

## The Algorithm
- The tf-idf weight is composed of two terms:
	1. TF: A weight representing the number of times a word appears in a document, divided by the total number of words in that document
	2. IDF: A weight representing the logarithm of the total number of documents in the corpus divided by the number of documents where the specific term appears
- tf-idf(t) = tf(t) * idf(t)

## More on Term Frequency
- In words, term frequency measures how frequenty a term occurs in a document
- TF(t) = (Number of times term t appears in a document)/(Total number of terms in the document)

## More on Inverse Document Frequency
- In words, inverse document frequency measures how important a term is
- IDF(t) = log_e(Total number of documents/Number of documents with term t in it)

## Example
- We want to know how important the term cat appears in a document, relative to the entire collection of documents
- Therefore, we want to know the td-idf weight
- The importance of the term "cat" in our document, or the term frequency, is (3 / 100) = 0.03, since 3 of the 100 words in our document is the term "cat"
- The importance of the term "cat" relative to the entire collection of our documents, or the inverse document frequency, is log(10,000,000 / 1,000) = 4, since 1,000 of the 10,000,000 documents from our collection of documents contains the term "cat"
- Thus, the tf-idf weight is the product of these quantities: 0.03 * 4 = 0.12

## References
- http://www.tfidf.com/
