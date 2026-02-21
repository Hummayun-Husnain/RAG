# Prompt Engineering Techniques

This project explores **Prompt Engineering**, the art of writing better instructions to get exactly what you want from an AI. It focuses on how to guide an LLM to follow specific formats and perform complex tasks more accurately.

## ## What is this project?

While previous labs showed how to talk to an AI, this lab shows how to **program** its behavior using only text. You will learn how to make an AI act as a classifier, a data extractor, or a structured data generator.

### Key Learning Objectives:

1. **Text Classification:** Training the AI to label data (e.g., deciding if a movie review is positive or negative).
2. **Task-Based Parameters:** Learning which settings (like Temperature) work best for creative writing versus factual analysis.
3. **Structured Output (JSON):** Forcing the AI to reply in a specific code-like format so that other software can use its answers.

## ## Key Techniques Explored

### 1. Classification & Labeling

Instead of a long paragraph, you can instruct the AI to provide a single-word label.

* **Example:** "Classify the following message as 'Urgent' or 'Not Urgent'."
* This is useful for sorting emails, reviews, or support tickets automatically.

### 2. Matching Parameters to Tasks

Not all tasks use the same settings:

* **For Classification/Logic:** Use a **low temperature (0.0)** to keep the AI consistent and factual.
* **For Creative Content:** Use a **higher temperature (0.7+)** to allow for varied and interesting vocabulary.

### 3. Pydantic and JSON Schemas

One of the most powerful parts of this lab is teaching the AI to "speak" in **JSON**.

* **The Problem:** Usually, AI adds conversational filler like "Sure! Here is your information:".
* **The Solution:** By using a **JSON Schema**, you force the AI to return *only* a structured object that contains specific fields (like `name`, `date`, and `summary`). This allows you to build real apps on top of the AI.

## ## Project Components

* **`C1M4_Ungraded_Lab_2.ipynb`:** The interactive notebook where you practice different prompting styles.
* **`utils.py`:** A helper file that manages the connection to the LLM and handles the formatting of the JSON responses.

## ## Major Takeaways

* **Be Specific:** The more details you give the AI about the *format* you want, the better it performs.
* **Control the Output:** Using `response_format={"type": "json_schema"}` is the best way to ensure the AI's output can be used by other computer programs.
* **Context is King:** Providing examples of how you want the AI to answer (Few-Shot Prompting) significantly improves its accuracy.

## ## How to Use

1. Open `C1M4_Ungraded_Lab_2.ipynb`.
2. Run the **Text Classification** section to see how an AI can summarize voice note transcripts.
3. Look at the **Structured Output** section to see how a messy paragraph can be turned into a clean, organized JSON object.