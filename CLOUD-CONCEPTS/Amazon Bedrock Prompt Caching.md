To configure **Amazon Bedrock Prompt Caching** for system prompts, you define your static instructions as a **cacheable prefix** followed by a **cache checkpoint** to signal where the static content ends and the dynamic content begins

Configuration Steps

1. **Verify Model Support & Thresholds:** Ensure you are using a supported model, such as **Amazon Nova** or **Anthropic Claude 3.7 Sonnet**. Your static prefix (system prompt) must meet minimum token requirements—typically between **1,024 and 4,096 tokens**, depending on the model.
2. **API Implementation:** In your `Converse` or `InvokeModel` API request, structure your payload so the system prompt is at the very beginning.
3. **Insert Checkpoints:** Place a cache checkpoint at the **end of your static system prompt**. You can use up to **4 checkpoints** per request to cache additional static elements, like few-shot examples.
4. **Manage Dynamic Content:** Place all unique user queries _after_ the final checkpoint. Bedrock will then use the cached tokens for the prefix, reducing latency and cutting costs by up to **90%** for that portion of the request.

How does prompt caching affect overall application latency?
Prompt caching significantly reduces overall application latency by avoiding the re-tokenization and recomputation of static prompt components.

**Impact on Latency**

- **Faster Response Times:** By reusing cached prompt segments—such as system instructions, few-shot examples, or large documents—the model skips processing the redundant prefix, leading to faster inference.
- **Reduced Time to First Token (TTFT):** It specifically improves the **Time to First Token**, as the foundation model can immediately begin generating a response rather than recalculating the static context.
- **Consistency:** For applications with long and repeated contexts (like a chatbot referencing a specific manual), caching ensures that latency remains low across frequent user queries.

**Operational Note The cache has a **5-minute TTL** that resets with each hit, and it requires a minimum number of tokens (typically 1,024 to 4,096 depending on the model) to be effective.

**Operational Note:** The cache has a **5-minute TTL** that resets with each successful hit, making it ideal for high-frequency applications with consistent system instructions