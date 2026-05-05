#ai-concepts 

**Model Customization (Fine-Tuning)**

- **Definition:** Adapting an FM's weights using labeled training data (input/output pairs) to learn new behaviors or styles.
- **Best For:** Teaching a model a very specific persona, specialized formatting (like complex JSON), or a unique industry style.
- **Pros:** Reduces the need for long prompts or few-shot examples, potentially saving tokens in high-volume workloads.
- **Cons:** Expensive and slow; the model suffers from a "knowledge cutoff" and won't know about information updated after training 

METHODS
[[PEFT]]







