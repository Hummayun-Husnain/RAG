# LLM Calls & Augmented Prompts (Lab 2)
This lab is all about moving from "general AI" to "context-aware AI" by feeding specific data into your prompts.

## 1. The LLM Connection
To interact with the models, we use two main patterns:

Single-Turn: Use generate_with_single_input for simple, one-off tasks.

Multi-Turn (Conversational): Use generate_with_multiple_input to maintain history. This requires a list of dictionaries where you track who said what (the role: user, assistant, or system).

## 2. Concept: Prompt Augmentation
The heart of Retrieval-Augmented Generation (RAG) is giving the AI facts it wasn't originally trained on.

The Data Bridge: We take structured data (like a list of house dictionaries) and transform it into a natural language "layout" that the AI can understand.

The Enhanced Prompt: Instead of just sending a question, we wrap the question inside a block of data. This forces the AI to use the provided facts as its "source of truth" rather than its own general training.

## 3. Key Functions
house_info_layout: Converts raw JSON-style data into a readable string.

generate_prompt: Merges the user's query with the data layout to create the final "augmented" prompt.