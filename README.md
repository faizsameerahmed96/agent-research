# Research Agent

## Learning
- Playwright toolkit not good for multiple browser invocations
- Agent definition is invoked multiple times until it terminates
  
  ```
    agent = (
        {
            "research_topic": lambda x: x["research_topic"],
            "agent_scratchpad": agent_scratchpad_formatter,
        }
        | research_prompt
        | llm
        | OpenAIToolsAgentOutputParser() # This gets the output from the OpenAI api call and gets the tool invocations from it. This then is executed by the AgentExecutor.
    )
  ```
- 

### With single LLM - GPT-4o
- We get good responses
- Follows commands when asked to search for more sources 
- Lacks nuance on what is important and what is not
- Asking the LLM to refer more sources does make the LLM use the tools more


### Langfuse
- Get idea of how the chain ran and how the agent thinks

### The flow
- We keep reiterating over the agent loop. We might need to make web browsing into it's own agent.

### Human in Loop


### Vector Store
- We need to chunk documents