### **Prompt Chaining**

Once we have good individual prompts, we need to programmatically call an LLM with them in succession. **Prompt chaining** connects the inputs and outputs of prompts programmatically. The output of one LLM call becomes input for the next, running in code or via an orchestrator. This builds sophisticated, scalable workflows.

For our LinkedIn post:

1. API call 1 `(Research): Prompt: "Research key concepts of AI agents."` **->** `RESPONSE_1`
2. API call 2 `(Summarize): Prompt: "Summarize the following key concepts: {RESPONSE_1}"` **->** `RESPONSE_2`
3. API call 3 `(Draft Post): Prompt: "Draft a LinkedIn post based on this summary: {RESPONSE_2}"` **->** `FINAL_RESPONSE`

### Chaining Tasks Is Essential for Agents

Consider asking: "What time is my dental appointment tomorrow?"

- **Hard-coded workflow:**
    1. LLM determines if calendar data is needed: Prompt: "Will this query require fetching calendar data? QUERY: What time is my dental appointment tomorrow?" -> Output: "Yes."
    2. If "Yes," orchestrator calls get_calendar().
    3. LLM uses calendar data to respond: Prompt: "{get_calendar_output}" -> Output: "Your dental appointment is at 9am."
- **AI Agent (ReAct framework):** The LLM itself is the decision-maker.
    1. User: "What time is my dental appointment tomorrow?"
    2. LLM: THOUGHT: I need to call get_calendar. ACTION: get_calendar(“tomorrow”)
    3. Orchestrator runs get_calendar(), gets "9am".
    4. LLM: OBSERVATION: {“9am”}
    5. LLM: THOUGHT: It is at 9am. Return the final answer. ACTION: final_answer("9am") Prompt chaining links these actions.

However, prompt chaining by itself is not reliable enough. LLMs can hallucinate, produce incorrect formats, or fail instructions. An error in an early step can derail the entire process (domino effect). Simply chaining prompts isn't enough for reliable systems. **We need intermediate validation.**

## Output Validation: Gate Checks

**Gate checks** are programmatic validations placed between steps in a prompt chain. They act as quality control points, ensuring an output meets criteria before being passed on.

- If checks pass: Continue.
- If a check fails: The system can trigger an error and halt, retry the step, or retry the step including the reason for failure in the prompt (to make errors less likely on retry).

**Example**

For a research task, check output formatting and verify quoted text exists in source documents.

- `output = call_llm(prompt_step1, "{SOURCES}")`
- Gate checks for: Formatting, Quoted text exists in source document
    - If YES: Continue to next step...
    - If NO: Raise error, Retry, OR Retry with failed gate check results

Gate checks ensure each "brick" of your LLM workflow is solid. They can be implemented using standard programming code (e.g., Python) or even other LLM-powered checks (for harmful/biased text). They rein in the stochastic and unpredictable behavior of LLMs. A failed check might cause the program to fail (useful for sensitive data) or trigger a retry.

**Types of Gate Checks:**

1. **Format Checks:** Structure (JSON, XML), length, required fields. Libraries like Pydantic or LLM offerings with structured outputs can help.
2. **Content Checks:** Keywords, phrases, topics, relevancy. Regex, semantic embeddings, or other LLMs can be used.
3. **Logic Checks:** Numerical/logical sense. If generating code: does it compile? Does it import restricted libraries? Are extracted numeric values reasonable?