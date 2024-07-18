# Semantic-search-engine
Semantic search transcends the limitations of traditional keyword searches by understanding the context and nuances of language in user queries. At its core, semantic search:

- Enhances the search experience by interpreting the intent and contextual meaning behind search queries.
- Delivers more accurate and relevant search results by analyzing the relationships between words and phrases within the search context.
- Adapts to user behavior and preferences, refining search results for better user satisfaction.

## A. Installing Required Libraries

Before we start, you need to install the following libraries if you haven't already:

- `tensorflow`: The core library for TensorFlow, required for working with the Universal Sentence Encoder.
- `tensorflow-hub`: A library that makes it easy to download and deploy pre-trained TensorFlow models, including the Universal Sentence Encoder.
- `faiss-cpu`: A library for efficient similarity search and clustering of dense vectors.
- `numpy`: A library for numerical computing, which we will use to handle arrays and matrices.
- `scikit-learn`: A machine learning library that provides various tools for data mining and data analysis, useful for additional tasks like data splitting and evaluation metrics.
The Technical Side of Semantic Search

After understanding the basics, let's peek under the hood at the technical engine powering semantic search. This part is a bit like math class, where we learn about vectors — no, not the ones you learned in physics, but something similar that we use in search engines.

#### Vectors: The Language of Semantic Search

In the world of semantic search, a vector is a list of numbers that a computer uses to represent the meaning of words or sentences. Imagine each word or sentence as a point in space. The closer two points are, the more similar their meanings.

- **Creating Vectors**: We start by turning words or sentences into vectors using models like the Universal Sentence Encoder. It's like giving each piece of text its unique numerical fingerprint.
- **Calculating Similarity**: To find out how similar two pieces of text are, we measure how close their vectors are in space. This is done using mathematical formulas, such as cosine similarity, which tells us how similar or different two text fingerprints are.
- **Using Vectors for Search**: When you search for something, the search engine looks for the vectors closest to the vector of your query. The closest vectors represent the most relevant results to what you're asking.

#### How Vectors Power Our Search

Vectors are powerful because they can capture the subtle meanings of language that go beyond the surface of words. Here's what happens in a semantic search engine:

1. **Vectorization**: When we type in a search query, the engine immediately turns our words into a vector.
2. **Indexing**: It then quickly scans through a massive index of other vectors, each representing different pieces of information.
3. **Retrieval**: By finding the closest matching vectors, the engine retrieves information that's not just textually similar but semantically related.

By the end of this project, you'll understand how to create a search engine that does all of this and more. We'll start simple and build up step by step. Ready? Let's get started!

#### Understanding Vectorization and Indexing
Vectorization and indexing are key components of building a semantic search engine. Let's explore how they work using the Universal Sentence Encoder (USE) and FAISS.

#### What does the Universal Sentence Encoder do?
The Universal Sentence Encoder (USE) takes sentences, no matter how complex, and turns them into vectors. These vectors are arrays of numbers that capture the essence of sentences. Here's why it's amazing:

Language Comprehension: USE understands the meaning of sentences by considering the context in which each word is used.
Versatility: It's trained on a variety of data sources, enabling it to handle a wide range of topics and sentence structures.
Speed: Once trained, USE can quickly convert sentences to vectors, making it highly efficient.
How does the Universal Sentence Encoder work?
The magic of USE lies in its training. It uses deep learning models to digest vast amounts of text. Here’s what it does:

Analyzes Words: It looks at each word in a sentence and the words around it to get a full picture of their meaning.
Understands Context: It pays attention to the order of words and how they're used together to grasp the sentence's intent.
Creates Vectors: It converts all this understanding into a numeric vector that represents the sentence.

#### What is FAISS and what does it do?
FAISS, developed by Facebook AI, is a library for efficient similarity search. After we have vectors from USE, we need a way to search through them quickly to find the most relevant ones to a query. FAISS does just that:

Efficient Searching: It uses optimized algorithms to rapidly search through large collections of vectors.
Scalability: It can handle databases of vectors that are too large to fit in memory, making it suitable for big data applications.
Accuracy: It provides highly accurate search results, thanks to its advanced indexing strategies.

#### How does FAISS work?
FAISS creates an index of all the vectors, which allows it to search through them efficiently. Here's a simplified version of its process:

Index Building: It organizes vectors in a way that similar ones are near each other, making it faster to find matches.
Searching: When you search with a new vector, FAISS quickly identifies which part of the index to look at for the closest matches.
Retrieving Results: It then retrieves the most similar vectors, which correspond to the most relevant search results.
Putting it all together:

With USE and FAISS, we have a powerful duo. USE helps us understand language in numerical terms, and FAISS lets us search through these numbers to find meaningful connections. Combining them, we create a semantic search engine that's both smart and swift.

#### The 20 Newsgroups Dataset
In this project, we'll be using the 20 Newsgroups dataset, a collection of approximately 20,000 newsgroup documents, partitioned across 20 different newsgroups. It's a go-to dataset in the NLP community because it presents real-world challenges:

#### What is the 20 Newsgroups Dataset?
Diverse Topics: The dataset spans 20 different topics, from sports and science to politics and religion, reflecting the diverse interests of newsgroup members.
Natural Language: It contains actual discussions, with all the nuances of human language, making it ideal for semantic search.
Prevalence of Context: The conversations within it require understanding of context to differentiate between the topics effectively.

#### How are we using the 20 Newsgroups Dataset?
Exploring Data: We'll start by loading the dataset and exploring its structure to understand the kind of information it holds.
Preprocessing: We'll clean the text data, removing any unwanted noise that could affect our semantic analysis.
Vectorization: We'll then use the Universal Sentence Encoder to transform this text into numerical vectors that capture the essence of each document.
Semantic Search Implementation: Finally, we'll use FAISS to index these vectors, allowing us to perform fast and efficient semantic searches across the dataset.
By working with the 20 Newsgroups dataset, you'll gain hands-on experience with real-world data and the end-to-end process of building a semantic search engine.

#### Output:
The actual text of the document. We display both the preprocessed and original versions of each document for comparison.
This functionality showcases the practical application of semantic search: retrieving information that is contextually relevant to the query, not just based on keyword matching. The displayed results will give a clear idea of how our semantic search engine interprets and responds to natural language queries.
