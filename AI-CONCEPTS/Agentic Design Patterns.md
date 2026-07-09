

Agentic systems can be structured using three main patterns:

- **Single-agent**: One agent handles a task sequentially.
- **Multi-agent**: Multiple specialized agents work in parallel.
- **Hierarchical**: A manager agent orchestrates and delegates tasks to sub-agents for complex workflows.

### The 4 Design Patterns for AI Agents

To address challenges like low reliability and unpredictability, AI agents can follow structured design patterns. These patterns enhance performance and improve outcomes.

- **Reflection:** The model generates output, evaluates its quality, and refines it in cycles. Useful for improving software documentation or debugging code.
- **Tool Use:** The model interacts with external systems like APIs or databases. Helps fetch real-time data, perform calculations, or run code.
- **Planning:** The model breaks down tasks into steps, creating a structured approach to problem-solving. Ideal for complex workflows requiring multiple decisions.
- **Multi-agent Collaboration:** Multiple AI agents work together, each specializing in different tasks. Similar to a team of experts handling a project.


### 5 Core Patterns

Architectural patterns that you will see over and over in the industry. Think of these as your building blocks:

1. **Prompt Chaining (The Assembly Line):** Breaking a complex task into a sequence of smaller steps, where the output of one becomes the input of the next.
2. **Routing (The Traffic Cop):** Analyzing an incoming request (is this text, an image, or a video?) and sending it to the specific specialist agent best suited to handle it.
3. **Parallelization (The Swarm):** Running multiple agents at the same time—like a data processor and a validator—and then aggregating their results to speed up high-throughput work.
4. **Evaluator-Optimizer (The QA Loop):** A cycle where one agent generates work and another critiques it against specific criteria, looping until the quality meets your standards.
5. **Orchestrator-Workers (The Project Manager):** A central brain that dynamically plans tasks and delegates them to specialized workers (like a Coder, Researcher, or Data Analyst) based on the specific needs of the request.

