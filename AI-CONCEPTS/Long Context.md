#ai-concepts 

Long Context + Prompt Caching

Instead of building a vector database to search for "chunks," you place the entire dataset (like the handbook) into the system prompt.

- **Best for:** Documents that fit within the model's context window (e.g., 50–200 pages).
- **Pro:** Higher accuracy because the model sees every word, not just retrieved snippets.
- **Con:** Requires **Prompt Caching** to avoid massive per-query costs.
**Long Context (with Prompt Caching)**


Addtional
- **Definition:** Bypassing retrieval by feeding an entire medium-sized document (e.g., a 100-page manual) directly into the prompt [
- **Best For:** High-accuracy tasks on single, static documents that fit within a model's context window (like Amazon Nova’s long-context window) 
- **Pros:** Higher accuracy than RAG because the model sees the entire context rather than just retrieved chunks 
- **Cons:** Extremely expensive unless paired with **Amazon Bedrock Prompt Caching**, which reduces input token costs for the static portion by up to 90% 

METHODS 

|Technique|What it does|
|---|---|
|**Full document injection**|Pass entire document into context window|
|**Map-reduce**|Split doc into chunks, summarise each, combine summaries|
|**Sliding window**|Process overlapping chunks sequentially|
|**Lost in the middle mitigation**|Place most important content at start and end of context|
|**Contextual compression**|Trim irrelevant passages before passing to LLM|
|**LLMLingua**|Token-level compression to fit more into context window|
|**Position interpolation**|Extend model's effective context beyond training limit|