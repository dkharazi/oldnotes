## General Notation
- A topic refers to some artificial group or category that the words could belong to
- A token refers to individual words
- A document refers to some individual text
- A corpus refers to a collection of texts

## Model Description
- In natural language processing, latent Dirichlet allocation (LDA) is a probabilistic model involving bayesian statistics
- The model typically takes in a hyperparameter representing our desired number of topics
- The model uses documents (or any individual pieces of text) as input
- The model outputs matrices representing:
	1. The probability that a document belongs to a topic
	2. The probability that a word belongs to a topic
- The idea of the model goes like this:
	- We collect a bunch of observations, which are words (collected into documents) 
	- Documents are thought to belong to some underlying topic to a certain degree
	- Topics are formed by grouping similar words from the collection of documents
	- We measure a document's degree of belonging to a topic by examining its words and determining which topic those words most closely align to

## Model Approach
- The goal of LDA is to compute the 2 hidden parameters often commonly denoted as θ and φ, where θ represents topic-document distribution and φ represents the word-topic distribution
- The posterior distribution for these parameters is intractable, since we cannot compute the integrals analytically in a high dimensional space
- Therefore, most advocate one of the two methods:
	1. Variational Inference
		-
		- This seems to be the preferred method for getting fast and accurate results in most software implementations
	2. MCMC Methods
		- These have the benefit of being unbiased and easy understand
		- However, it seems MCMCs are handicapped by being computationally inefficient when working with large corpora

## LDA Steps
1. Create a list of lists, where each list represents some document (or individual text entry) and each entry within that list represents an individual word from that document
	- Example:
		[[“Eat”, “turkey”, “on”, “holidays”, “always”],
		 [“I”, “eat”, “cake”, “on”, “holidays”],
		 [“Turkey”, “eat”, “chickens”]]
2. Preprocess by removing stop words, removing punctuation, and lemmatizing words
	- Example:
		[[“eat”, “turkey”, “holiday”, “always”],
		 [“eat”, “cake”, “holiday”],
		 [“turkey”, “eat”, “chicken”]]
3. One hot encoding
	- Example:
		[[1,2,3,4], [1,5,3], [2,1,6]]
4. Randomly assign a topic to each word to initialize a word-topic matrix
	- Example:
		[[1,1,2,2], [1,2,1], [2,2,1]] where the number of topics is 2
5. Generate a word-topic count matrix
	- Word-topic matrices represent an n by m dimensional matrix, where n is the number of distinct topics, m is the number of distinct words, and each entry contains a count of the words assigned to each topic
	- In other words, each row represents a conditional frequency distribution of words given a topic
	- If we sum up some column, we should receive the frequency of a word across all documents
	- If we sum up some row, we should receive the frequency of a topic
	- Example:
		[2,1,1,0,0,1] where the number of topics is 2 (2 rows)
		[1,1,1,1,1,0] and the number of distinct words is 6 (6 columns)
6. Generate a document-topic count matrix
	- Document-topic matrices represent an n by m dimensional matrix, where n is the number of distinct documents, m is the number of distinct topics, and each entry contains a count of the topics assigned to each document
	- In other words, each row represents a conditional frequency distribution of topics given a document
	- If we sum up some column, we should receive the frequency of a topic
	- If we sum of some row, we should receive the frequency of words in a specific document
	- Example:
		[2,2] where the number of documents is 3 (3 rows)
		[2,1] and the number of topics is 2 (2 columns)
		[1,2]
7. Assign better topics to words (instead of our initial, randomly-assigned topics)
	- We do this by simulating the probability that a word belongs to a topic using Gibbs sampling and by determining if tokens belong to a topic at the start of an iteration and comparing if those tokens belong to the same topic in other documents
	- Example:
		[[2,1,1,2], [2,1,1], [1,2,2]]
8. Recompute the word-topic matrix
	- Example:
		[0,2,2,0,1,0]
		[2,0,0,1,0,1]
9. Recompute the document-topic matrix
	- Example:
		[2,2]
		[2,1]
		[1,2]
10. We can now calculate the probability that a document belongs to each topic by summing the number of words in a certain topic and dividing that quantity by the total number of words within the document
	- Example:
		[0.5,0.5]
		[0.66,0.33]
		[0.33,0.66]
10. We can also calculate the probability of a word belonging to each topic by summing the number of words in a certain topic and dividing that quantity by the total number number of words in that topic
	- Example:
		[0,0.4,0.4,0,0.2,0]
		[0.5,0,0,0.25,0,0.25]

## References
- https://en.wikipedia.org/wiki/Latent_Dirichlet_allocation
- https://shuaiw.github.io/2016/12/22/topic-modeling-and-tsne-visualzation.html
- https://www.analyticsvidhya.com/blog/2016/08/beginners-guide-to-topic-modeling-in-python/
- http://brooksandrew.github.io/simpleblog/articles/latent-dirichlet-allocation-under-the-hood/
- https://www.kaggle.com/ktattan/lda-and-document-similarity
- https://stats.stackexchange.com/questions/244917/what-exactly-is-the-alpha-in-the-dirichlet-distribution
- https://towardsdatascience.com/bayesian-inference-problem-mcmc-and-variational-inference-25a8aa9bce29
