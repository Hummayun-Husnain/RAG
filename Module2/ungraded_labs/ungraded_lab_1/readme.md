# Exploring Vector Embeddings
This project is a beginner-friendly guide to understanding Vector Embeddings, the technology that helps AI understand the meaning behind words. It is designed as an interactive lab to show how computers "map" language into math to find relevant information. 
+1

## What is this project?
In Retrieval-Augmented Generation (RAG), vector embeddings act like a digital map. This project demonstrates:
+1


Capturing Meaning: How words and sentences are turned into numerical positions (vectors) that represent their context.
+1


Smart Search: How AI compares a user's question to a database to find the most similar answers.
+1


Visualizing Data: Using math to turn complex, 768-dimensional data into a simple 2D chart you can actually see.
+1

## Core Concepts
1. Measuring Similarity
The project explains the two main ways AI calculates how "close" two ideas are:


Cosine Similarity: Measures the angle between two vectors. A score near 1 means the meanings are very similar.
+1


Euclidean Distance: Measures the straight-line distance between two points. A smaller distance means the items are more related.
+1

2. The Retrieval Process
To find information, the system follows three simple steps:


Embed: Turn the query and documents into vectors.
+1


Measure: Use a similarity metric to see how close they are.
+1


Sort: Rank them and pick the best matches.
+1

## Tools Used

Model: BAAI/bge-base-en-v1.5 — A transformer model that turns sentences into 768 numbers.
+1


Language: Python.
+1


Key Libraries: numpy for math, matplotlib for charts, and sentence-transformers for the AI model.
+1

## Important Lesson: The Context Window
One of the key experiments in this lab shows that models have a limit on how much text they can read at once.
+1

The model used here has a 512-token limit.
+1

If you give it a massive document, it simply ignores everything past that limit.
+1

The project proves this by showing that a full text and a cut-down version produce the exact same vector.
+1

## How to Use
Open C1M2_Ungraded_Lab_1.ipynb in a Jupyter environment.
+1

Run the cells to load the embedding model.
+1

Use the interactive widget to type in your own words and see them appear on a semantic map.