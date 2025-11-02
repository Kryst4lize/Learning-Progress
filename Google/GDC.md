# ADK (Agent development kit)
Concept in ADK: 
- Workflow agents:
	Sequential Agents
	Parallel Agents
Reasoning models (Google):
- Pro 2.5
- Flash 2.5
- Flash lite 2.5
# Tooling and MCP
Model Context Protocol (Launched by Anthropic)
## Advantages
Part of "Compound AI system"
- Composability 
- Grounding: give model access to retrieve information
- Agentic Behaviour: let the model decided what to do and when to do 
Same behavior with [[Apache Kafka]] (Create a intermediate layer to control between database and AI agent/ source and database)
## MCP toolbox for Databases 
- Uses case: Automatic building a resume
First Draft : Using monolith agent with local LLM. Database access through MCP 