# Measuring Retrieval Performance
This project is a practical guide to evaluating how well a Retrieval-Augmented Generation (RAG) system finds the right information. It focuses on the mathematical metrics used to test if a search system is actually "smart" or just guessing.

## What is this project?
While the previous lab focused on creating embeddings, this project focuses on evaluation. You will learn how to measure if your retrieval system is picking the best documents from a large dataset.

Key Learning Objectives:

Precision and Recall: Learn the two most important math formulas for search quality.


Context Evaluation: Understand "Context Precision" and "Context Recall" to see if the retrieved data is useful for an AI to answer a question.


Dataset Testing: Use a real-world dataset (20 Newsgroups) to see how search performs in the real world.

## Core Metrics Explained
1. Precision vs. Recall

Precision: Out of all the documents the system found, how many were actually relevant? 


Recall: Out of all the relevant documents that exist, how many did the system manage to find? 


Shutterstock
Explore
2. The Trade-off (Top-K)
The project explores how choosing the number of results (K) changes your scores:


Small K (e.g., 5 results): High Precision (most results are good), but Low Recall (you missed a lot of other relevant info).


Large K (e.g., 50 results): Higher Recall (you found more info), but lower Precision (you included a lot of "junk" or irrelevant data).

## Technical Tools

Dataset: 20 Newsgroups (a collection of thousands of posts across different categories like politics, science, and sports).


Embeddings: sentence-transformers to turn these posts into searchable vectors.


Analysis: Python and numpy to calculate the success rates of the searches.

## Major Takeaways

K=5 to K=20 is often the "Sweet Spot": For most AI systems, retrieving 5 to 20 documents gives the best balance of high-quality info without overwhelming the AI.


Topic Difficulty: Some topics (like "politics") are harder for AI to distinguish than others (like "space exploration") because the language used is more similar to other categories.


Precision matters more for RAG: In RAG systems, it is usually better to have a few highly relevant documents than many documents where most are irrelevant.

## How to Use
Open C1M2_Ungraded_Lab_2.ipynb.

Run the code to download the newsgroups dataset.

Compare different "Top-K" values to see how the Precision and Recall charts change.