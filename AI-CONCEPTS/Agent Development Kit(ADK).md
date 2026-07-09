#### **What is Google ADK?**

Think of ADK as the "React" or "Django" for AI agents. It is an open-source, code-first framework that provides the architectural primitives—the pre-built blocks—you need to construct complex agentic workflows without reinventing the wheel.

While you _could_ write raw API calls to Vertex AI yourself, ADK handles the heavy lifting of state management, concurrency (running agents in parallel), and conversation history so you can focus on the _logic_ of your agents.

#### **Why We Use It**

1. **Standardized Primitives:** Instead of writing custom loops and state trackers, you use robust classes like `SequentialAgent` (for chains) and `ParallelAgent` (for swarms).
2. **Vertex AI Integration:** It is optimized for the Google ecosystem, making it seamless to connect your code to Gemini models on Vertex AI.
3. **Production Readiness:** It includes patterns for error handling, retries, and observability that are essential when moving from a prototype to a real product.