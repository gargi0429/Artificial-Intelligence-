1. What is RAG?

RAG = Retrieval + Generation

Instead of relying only on what the LLM learned during training, we first retrieve relevant information from external documents and then give it to the LLM to generate an answer.

Traditional LLM
User Question
      ↓
     LLM
      ↓
   Answer

Problem:

Knowledge can be outdated
Can hallucinate
Doesn't know your company documents
RAG
User Question
      ↓
 Retrieve Relevant Documents
      ↓
 Add Context
      ↓
     LLM
      ↓
   Answer

Now the answer is based on actual documents.

2. Why RAG is Used?
Problem 1: Hallucinations

Question:

What is our company's leave policy?

A normal LLM doesn't know.

It may invent an answer.

Problem 2: Private Data

Examples:

Company documents
Legal documents
Medical records
Research papers

These are not part of LLM training.

RAG solves this.

3. Real-World Examples
Chat with PDFs

Upload:

Resume
Research Paper
Company Policy

Ask:

Summarize this PDF

What is page 5 about?

Uses RAG.

Customer Support Bots

Company knowledge base → Retrieved → Sent to LLM

Legal AI

Your Jurisynth project uses RAG.

Legal Query
     ↓
Retrieve Relevant Cases
     ↓
Legal-BERT / Vector DB
     ↓
LLM Generates Answer
4. Components of RAG
A. Documents

Examples:

PDF
Word files
Websites
Databases
B. Chunking

Large documents are split into small pieces.

Example:

100 Page PDF
      ↓
500 Chunks

Why?

LLMs cannot process huge documents efficiently.

C. Embeddings

Convert text into vectors.

Example:

"The cat is sleeping"

↓

[0.12, 0.89, 0.45, ...]

These numerical vectors capture meaning.

D. Vector Database

Stores embeddings.

Popular vector DBs:

FAISS
Pinecone
ChromaDB
Weaviate
E. Retriever

When a user asks a question:

Question
     ↓
Convert to Embedding
     ↓
Similarity Search
     ↓
Top Relevant Chunks
F. Generator

Retrieved chunks are passed to the LLM.

The LLM generates the final answer.

5. Complete RAG Flow
Documents
    ↓
Chunking
    ↓
Embeddings
    ↓
Vector Database
    ↓
User Question
    ↓
Embedding
    ↓
Similarity Search
    ↓
Relevant Chunks
    ↓
LLM
    ↓
Final Answer
6. Advantages
✅ More Accurate

Uses actual documents.

✅ Less Hallucination

Answers grounded in data.

✅ Up-to-Date

Add new documents anytime.

✅ Works on Private Data

Company files, PDFs, contracts.

7. Disadvantages
❌ Retrieval Errors

Wrong chunks = wrong answer.

❌ More Complex

Need Vector DB + Embeddings.

❌ Higher Cost

Extra retrieval step.

8. Interview Questions
Q1. What is RAG?

RAG combines information retrieval and text generation. Relevant documents are retrieved first and then provided to the LLM for generating accurate responses.

Q2. Why is RAG better than fine-tuning?
RAG	Fine-Tuning
Easy to update	Retraining required
Cheaper	Expensive
Works on latest documents	Knowledge becomes static
Q3. What is a Vector Database?

A database that stores embeddings and performs similarity search to find semantically related information.

Q4. What are embeddings?

Numerical vector representations of text that capture semantic meaning.

Q5. Name some vector databases.
FAISS
Pinecone
ChromaDB
Weaviate
9. GitHub Notes (Short Version)
# Retrieval-Augmented Generation (RAG)

## What is RAG?
RAG combines Retrieval and Generation to improve LLM responses using external knowledge.

## Workflow
Documents → Chunking → Embeddings → Vector Database → Retrieval → LLM → Answer

## Benefits
- Reduces hallucinations
- Uses private data
- Provides up-to-date information
- More accurate answers

## Popular Tools
- FAISS
- Pinecone
- ChromaDB
- Weaviate
