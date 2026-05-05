#ai-concepts 

**Prompt Engineering**

- **Definition:** The practice of crafting and optimizing input text to guide a foundation model (FM) without modifying its weights.
- **Best For:** General tasks like summarization, translation, or creative writing 
- **Pros:** The fastest and least resource-intensive starting point; requires no external data storage or training.
- **Cons:** Limited by the model's internal "parametric knowledge" and the maximum context window size**Prompt Engineering**

METHODS

| Technique | What it does |
| --- | --- |
| Chain of Thought (CoT) | Ask model to reason step by step before answering |
| Few-shot prompting | Provide examples of input/output in the prompt |
| Zero-shot prompting | No examples — rely on instruction clarity alone |
| ReAct | Combine reasoning and action in a loop |
| Self-consistency | Run multiple reasoning paths, pick most common answer |
| Tree of Thought | Explore multiple reasoning branches simultaneously |
| Role prompting | Assign the model a persona — You are a senior lawyer |
| Prompt chaining | Break complex tasks into sequential prompt steps |