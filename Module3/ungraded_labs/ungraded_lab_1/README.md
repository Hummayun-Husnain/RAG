# Introduction to Weaviate and Reranking
This project is a practical introduction to using Vector Databases and Rerankers to build better AI search systems. It focuses on Weaviate, a popular database designed specifically for AI and vector search.

## What is this project?
In the previous labs, you learned how to create and measure embeddings. This project takes it to the next level by showing you how to store those embeddings and refine your search results using a "Reranker."

Key Learning Objectives:
The Weaviate API: Learn how to connect to a vector database, create a "Collection" (like a table), and upload data.

Vector Search: Perform a "Near Text" search to find information based on meaning rather than just keywords.

Reranking: Learn how to use a second, more powerful AI model to double-check search results and put the most relevant answer at the very top.

## How It Works
1. The Vector Database (Weaviate)
Instead of searching through a text file, we store our data in Weaviate. When you ask a question, Weaviate looks at the "vector space" to find the closest matches.

Collection: A group of similar objects (e.g., "TravelDestinations").

Properties: The specific details stored for each object (e.g., "city name," "description").

2. The Reranking Step
Standard vector search is fast but sometimes misses the mark. A Reranker acts like a second judge:

Search: Weaviate finds the top 5 matches.

Rerank: The Reranker looks closely at those 5 matches and re-orders them to ensure the best one is #1.

## Technical Stack
Database: Weaviate (Vector Database).

Reranker Model: BAAI/bge-reranker-base.

Backend: A Flask app (flask_app.py) that handles the communication between the database and the reranking model.

Utilities: utils.py contains helper functions to clean up and display the database results clearly.

## Key Features in the Code
client.collections.create: Sets up the database structure.

collection.data.insert: Adds your text and vectors to the database.

query.near_text: The command used to ask the database a question.

Rerank module: Automatically triggers the reranking process during a search.

## How to Use
Start the Backend: Run flask_app.py to get the reranking service ready.

Run the Lab: Open C1M3_Ungraded_Lab_1.ipynb.

Experiment: Try searching for "Fun places to travel in winter" and see how the Reranker changes the order of the results to give you better suggestions.