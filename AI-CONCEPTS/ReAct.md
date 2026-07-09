### Introducing ReAct (Reason + Act) Prompting

CoT is great for internal reasoning, but what if the task requires getting new information or interacting with the outside world? That's where ReAct comes in. ReAct stands for **Reason + Act**. It's a prompting technique that synergizes reasoning and acting in LLMs by interleaving thought steps with action steps.

The core of ReAct is its iterative loop: **Thought, Action, Observation.**

1. **Thought:** The model internally reasons and plans the next specific step required to progress towards the overall task goal. It analyzes the situation, figures out necessary steps, and decides on an action.
2. **Action:** Based on its plan, the model specifies using an external tool (like web search, calculator, API) with provided parameters. An orchestrator program then executes this tool. Tools are functions or services the agent can invoke.
3. **Observation:** The model receives the results or feedback from the executed action (e.g., search results, calculator answer, confirmation of an email sent). This new information feeds into the next Thought. This observation, sometimes referred to as information from the "environment" if it's from the outside world like a weather report, then feeds back into the model's next Thought, allowing it to refine its plan or take subsequent actions.

This cycle repeats until the agent specifies an action to return the final result. Each step is normally recorded in the message history of the chat.

1. **Example Interaction:**
    - **System Prompt:** "You are a helpful assistant **with access to the tool get_weather and final_answer**. Respond with Thought:
    - **User Prompt:** "What is the weather today?"
    - **Assistant:** Thought: I need to get the weather Action: get_weather
    - **User (from the tool call):** Observation: Sunny and 30 degrees
    - **Assistant:** Thought: I will return the final weather of Sunny and 30 Action: final_answer("sunny and 30")

In this case, the ReAct agent goes through the loop twice. The first time it calls get_weather. The second time it returns the result using final_answer, signaling loop termination. Getting the LLM to respond in exactly this order and format is about prompt engineering, namely clear instructions and examples in the system prompt.