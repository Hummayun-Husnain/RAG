# Chunking Strategies for RAG

This project explores **Chunking**, which is the process of breaking down long documents into smaller pieces. This is a vital step in building AI systems because models have a "limit" on how much text they can process at once.

## ## What is this project?

When you give an AI a 50-page book, it can't "read" it all in one go. You have to break it into chunks. This lab teaches you how to do that effectively so the AI doesn't lose important context.

### Key Learning Objectives:

* **Fixed-size Chunking:** Splitting text by a set number of characters or words.
* **Overlap:** Why keeping a bit of the previous chunk in the next one helps the AI understand the "flow" of information.
* **Recursive Splitting:** A smarter way to split text that tries to keep related sentences or paragraphs together.
* **Strategy Comparison:** See how different chunking methods change the quality of the AI's final answer.

## ## Chunking Methods Explained

### 1. Fixed-Size Chunking

You split the text every  characters.

* **Pros:** Very fast and simple.
* **Cons:** It often cuts sentences in half, making the text hard for the AI to understand.

### 2. Chunking with Overlap

You split the text into chunks, but make sure the end of Chunk 1 is the same as the start of Chunk 2.

* **Why it matters:** It provides "contextual glue." If a sentence is split, the overlap ensures the meaning is preserved in at least one of the chunks.

### 3. Recursive Character Splitting

Instead of a blind cut, this method looks for natural breaks like:

1. Double newlines (Paragraphs)
2. Single newlines (Lines)
3. Spaces (Words)

* **Goal:** To keep related information together in the same "bucket."

## ## Project Components

* **`C1M3_Ungraded_Lab_2.ipynb`:** The main interactive notebook where you test different splitting sizes.
* **`data.joblib`:** A pre-processed dataset of travel destinations used for testing.
* **`flask_app.py` & `utils.py`:** Backend tools that help generate vectors and manage the database connections for the lab.

## ## Major Takeaways

* **Chunk size matters:** If chunks are too small, the AI loses the "big picture." If they are too big, they might not fit in the model's memory.
* **The "Golden Rule":** Always use some overlap (usually 10-20%) to prevent the AI from losing context at the edges of a split.
* **Recursive is better:** Smart splitting (by paragraphs/sentences) almost always leads to better search results than simple character counting.

## ## How to Use

1. Open the notebook and load the travel dataset.
2. Experiment with the **Sliding Window** tool to change chunk sizes.
3. Ask a question like "What are some fun things to do in the Grand Canyon?" and see which chunking strategy helps the AI find the best answer.
