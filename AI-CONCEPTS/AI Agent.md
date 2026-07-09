The **Perception-Reasoning-Action** loop is the engine that drives an agent. It consists of three primary stages that repeat until the agent's goal is achieved.
Core pattern for any Agentic system built.

## The Role of Feedback

The loop does not end after an action is taken. The outcome of that action provides **feedback**, which is essential for the agent's process. The agent observes the result of its action: Did the API call succeed? What information was returned from the database query?

This feedback becomes the new **perception** for the next cycle of the loop. The agent learns from the outcome and uses this new information to inform its next reasoning phase and subsequent action.


### Common components of an AI Agent:

1. **Large Language Model (LLM):** The "brain" for understanding, reasoning, acting.
2. **Tools:** External functions, APIs for interaction and enhanced capabilities.
3. **Instructions:** Guidelines (system prompts) defining behavior and goals.
4. **Memory:** Short-term (context) & Long-term (history) for learning and consistency.
5. **Runtime/Orchestration Layer:** Manages execution flow, tool usage, observation processing

### The human collaborator

A critical component is the **human collaborator**. Agents are designed for collaboration, not full autonomy. The human partner defines goals, provides tools, and supervises the process. This partnership relies on _transparent reasoning_, which allows for trust and verification of the agent's conclusions..

To achieve complex goals, agents break tasks down and execute them step-by-step, assessing progress. Let's explore a technique to accomplish this called: [[Prompt Chaining]].

[[Agentic Design Patterns]]
[[Agent Development Kit(ADK)]]



