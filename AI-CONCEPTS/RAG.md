#ai-concepts 

The architecture for **Retrieval-Augmented Generation (RAG)** is a multi-layered system designed to connect large language models (LLMs) to external, verifiable knowledge sources. In production, a standard RAG system consists of four primary moving parts: **Ingestion and Chunking**, **Embedding and Vector Storage**, **Retrieval and Re-ranking**, and **Generation with Context**.

1. The Ingestion and Chunking Layer

The process begins with the ingestion of raw source documents, such as PDFs, database records, or web pages.

- **Parsing:** Content is extracted from these documents, sometimes requiring OCR for scanned materials.
- **Chunking:** Because models cannot process entire large documents at once, the text is split into smaller, semantically meaningful segments called "**chunks**" (typically 256 to 1,024 tokens).
- **Strategies:** Advanced pipelines use **semantic chunking** to respect sentence boundaries or **hierarchical chunking** to preserve the document’s structure, ensuring ideas aren't cut off mid-concept

2. The Embedding and Vector Storage Layer

This layer transforms unstructured text into a format that a machine can search mathematically.

- **[[Embeddings]]:** Each text chunk is converted into a numerical representation called a **vector embedding** using an embedding model. These vectors capture the semantic meaning; chunks with similar meanings are positioned closer together in a high-dimensional mathematical space.
- [[Vector Database]]:These embeddings are stored in a specialized **vector database** (e.g., Pinecone, Weaviate, Milvus, or Qdrant).
- **Indexing:** The database uses optimized algorithms like **HNSW** (Hierarchical Navigable Small World) to enable sub-millisecond similarity searches across millions of vectors.

3. The Retrieval and Re-ranking Layer

When a user submits a query, the system performs a "**semantic search**" rather than a simple keyword match.

- **Query Embedding:** The user’s question is converted into a vector using the same embedding model used for the chunks.
- **Similarity Search:** The system identifies the "**top-k**" candidates that have the smallest semantic distance to the query embedding, using metrics like **cosine similarity** or Euclidean distance.
- **Hybrid Search:** Many production systems combine vector search with keyword-based search (**BM25**) to handle exact matches like product IDs or proper nouns.
- **Re-ranking:** A second, more expensive model (a **reranker**) can be used to re-score the top candidates for higher precision before passing them to the generator.

4. The Generation, Citation, and Evaluation Layer

The final stage transforms the retrieved information into a natural language response.

- **Augmentation:** The retrieved chunks are appended to the original user query, creating a "richer," **augmented prompt**.
- **Synthesis:** The LLM receives this context and generates a response that is **grounded** in the provided facts, which helps reduce hallucinations.
- **Citations:** A mature RAG architecture includes a mechanism to provide **citations**, pinpointing the exact source chunks used for the answer to enhance trust.
- **Evaluation:** Systems are often evaluated using frameworks like **RAGAS**, which measure faithfulness (accuracy to context) and answer relevancy.

Advanced Evolutions

- [[AgenticRAG]]:** Introduces a reasoning layer where an AI agent acts as a gatekeeper, actively validating the quality and relevance of retrieved sources or performing multi-step reasoning to synthesize complex answers.
- [[GraphRAG]] Navigates explicit relationships between data entities using a **knowledge graph**, which excels at answering queries fragmented across multiple different documents


[[RAGArchitecture]]
[[RAGComponents]]

[[RAG EVALS]]


