# Tracing and Monitoring RAG Systems

This project focuses on **Observability**. It teaches you how to look "under the hood" of an AI system to see exactly how data moves from a user's question to the final AI answer. It uses **Phoenix** (by Arize) to visualize the invisible steps of a RAG pipeline.

## ## What is this project?

When a RAG system fails, it can be hard to tell why. Was the search bad? Did the AI hallucinate? This lab shows you how to use **Tracing** to solve these mysteries.

### Key Learning Objectives:

* **Tracing & Spans:** Learn how to record every single step of a process (like a database query or an LLM call).
* **Troubleshooting:** Use a visual dashboard to find exactly where a system is slow or incorrect.
* **Phoenix UI:** Explore an industry-standard tool for monitoring AI performance.
* **Full Pipeline View:** See how Weaviate (the database) and Llama (the AI) interact in real-time.

## ## Core Concepts Explained

### 1. Traces and Spans

* **Trace:** The "whole story." It represents the entire journey of a single request from start to finish.
* **Span:** A "chapter" in that story. It represents one specific action, like "Search Database" or "Generate Text."
* By looking at spans, you can see exactly how many seconds the database took versus how many seconds the AI took.

### 2. Telemetry

This is the process of automatically collecting data about your code. In this lab, we use `openinference` to automatically "wrap" our AI calls so they send data to the Phoenix dashboard without us having to write extra code for every step.
\
## ## Project Components

* **`C1M5_Ungraded_Lab_1.ipynb`:** The main lab where you build a FAQ-answering bot and watch its traces.
* **`weaviate_server.py`:** Starts an "Embedded Weaviate" instance, which is a database that runs right inside your lab environment.
* **`faq.joblib`:** A pre-made dataset of "Fashion Forward Hub" customer service questions and answers.
* **`flask_app.py` & `utils.py`:** These handle the background math and the connection to the Phoenix visualization dashboard.

## ## The RAG Pipeline in this Lab

1. **Question:** The user asks, "What are your working hours?"
2. **Retrieve:** Weaviate searches the `faq.joblib` data for the most relevant answer.
3. **Trace:** Phoenix records how long the search took and what it found.
4. **Generate:** The AI takes the search results and writes a friendly response.
5. **Trace:** Phoenix records the AI's "thought process" and final output.

## ## How to Use

1. **Open the Lab:** Start `C1M5_Ungraded_Lab_1.ipynb`.
2. **Start the UI:** Run the cell containing `utils.make_url()`. This will give you a special link.
3. **Watch the Traces:** Open that link in a new tab. It will be empty at first.
4. **Run a Query:** Go back to the notebook and ask the bot a question.
5. **Analyze:** Switch back to the Phoenix tab to see the "tree" of actions that just happened!