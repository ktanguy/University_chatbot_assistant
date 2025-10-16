# University_chatbot_assistant


ALU Chatbot

Author: Tanguy Kwizera


Overview

The ALU Chatbot is a student assistant designed to help African Leadership University students find accurate answers to common questions about admissions, fees, scholarships, accommodation, timetables, and academic services.

Two models were developed and compared:

Fine-tuned T5 Model (TensorFlow)

Ollama RAG Model (Qwen 1.5B with retrieval)

Dataset

Source: ALU FAQ and Student Portal

Size: ~165 question–answer pairs

Split: 80% training, 20% testing

Cleaned by removing duplicates, placeholders, and HTML tags

Models and Results
1. Fine-tuned T5

Framework: TensorFlow + Transformers

Approach: Supervised fine-tuning on ALU data

Best config: Beam search with retrieval

BLEU: 7.46

F1: 0.146

Latency: ≈ 2.2s

Notes: Fast and lightweight but occasionally off-topic.

2. Ollama RAG

Framework: Ollama local LLM runtime

Model: Qwen 2.5 - 1.5B Instruct

Approach: Retrieval-Augmented Generation (TF-IDF + context)

BLEU: 5.17

F1: 0.193

Latency: ≈ 14.5s

Notes: More fluent, better contextual answers, slower runtime.

Deployment

Both models include a Gradio interface for interaction.
Users can ask questions, adjust temperature, and toggle retrieval mode.

Example:

User: How do I apply to ALU?
Bot: Apply via the official ALU portal and submit all required documents before the deadline.



Summary
Aspect	T5 Fine-tuned	Ollama RAG
BLEU	7.46	5.17
F1	0.146	0.193
Latency	2.2s	14.5s
Accuracy	Moderate	High
Fluency	Good	Excellent
Fine-tuning	Required	Not required

Future Work

Expand dataset to >500 entries

Add semantic retrieval with embeddings

Deploy Streamlit version online
