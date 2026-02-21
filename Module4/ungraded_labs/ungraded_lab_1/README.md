# Exploring LLM Capabilities

This project is an interactive playground designed to show how different "knobs and dials" (parameters) change the way an Artificial Intelligence (LLM) thinks and speaks. It also demonstrates how to turn a simple AI into a chatbot that remembers what you said previously.

## ## What is this project?

While previous labs focused on finding information, this lab focuses on the **Generation** part of RAG. You will learn how to control the "creativity" of the AI and how to manage a conversation history.

### Key Learning Objectives:

* **LLM Parameters:** Master settings like `Temperature` and `Top-p` to control how random or predictable the AI is.
* **Chat Memory:** Learn how to use a "Context" list to keep track of the conversation so the AI can remember your name or previous questions.
* **System Prompts:** Understand how to give the AI a "personality" (e.g., making it a funny assistant or a serious tutor).

## ## Core Parameters Explained

To get the best results from an AI, you need to understand these two main settings:

### 1. Temperature

Think of this as the "Creativity Dial."

* **Low Temperature (e.g., 0.1):** The AI is very focused and predictable. It will likely give the same answer every time. Great for facts or coding.
* **High Temperature (e.g., 0.8+):** The AI becomes more creative and takes risks. It might use more diverse words but can also become nonsensical.

### 2. Top-p (Nucleus Sampling)

This tells the AI to only consider a "pool" of the most likely next words whose total probability adds up to .

* If , the AI only looks at the very top, most obvious words.
* If , the AI considers a much wider variety of words.

## ## How Chat Context Works

An LLM is naturally "forgetful"—it treats every message as a brand-new encounter. To create a chatbot, we use a **Context List**:

1. **System Message:** Sets the rules (e.g., "You are a helpful assistant").
2. **User Message:** Your question.
3. **Assistant Message:** The AI's previous answer.
4. **The Loop:** Every time you send a new message, the *entire* list is sent back to the AI so it has the full "history" of the chat.

## ## Technical Stack

* **Model:** `Llama-3.2-3B-Instruct` (via Together AI).
* **Language:** Python.
* **Tools:** `utils.py` provides a custom `chat()` function that handles the message loop and parameter adjustments.

## ## How to Use

1. Open `C1M4_Ungraded_Lab_1.ipynb`.
2. **Experiment with Parameters:** Run the cells to see how the same prompt (like "Write a poem about coffee") changes when you move the temperature from 0.0 to 1.0.
3. **Chat:** Use the interactive chat cell to talk to the AI. Try telling it your name in one message, and ask "What is my name?" in the next to see if the context is working.
