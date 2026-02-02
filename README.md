**DEEPAGENTS**

deepAgents is a from scratch exploration of stateful, graph-based AI agents built using LangGraph + LangChain, with a strong focus on how agents actually work internally.

Instead of hiding complexity behind abstractions, this repo makes agent state, planning, memory, and execution explicit and inspectable.

If you want to understand what really happens inside an agent loop, this repo is for you.


Why this repo exists

Most “agent” examples online:
	•	hide state mutations
	•	blur steps into a single black box loop
	•	rely on magic wrappers

deepAgents takes the opposite approach.

This repo is about:
	•	explicit agent state
	•	graph nodes as execution steps
	•	reducers for safe state merging
	•	task planning via TODOs
	•	virtual file systems inside agent memory
	•	tool driven state updates
	•	sub agents and composition

In short: agents as engineered systems, not demos.

What you’ll learn from this repo

Agent state, done properly

You’ll see how to extend LangGraph’s AgentState to include:
	•	structured TODO lists
	•	long lived virtual files
	•	safe merging via reducers

This enables long running, recoverable agents.


**Task planning with TODOs**

Agents don’t just “respond”. They:
	•	create tasks
	•	track progress
	•	update status (pending, in_progress, completed)
	•	reason about what’s left

This mirrors how humans work and makes agent behavior debuggable.


**Virtual file system inside agent memory**

Instead of bloating prompts:
	•	agents write intermediate results to files
	•	files persist across steps
	•	state stays compact and cheap

This is context offloading, not prompt stuffing.


**Tool driven state mutation**

Tools are first class citizens:
	•	tools can read/write TODOs
	•	tools can read/write files
	•	tools can return Commands to mutate state

State changes are explicit and auditable.


**Sub agents and composition**

Agents can:
	•	delegate work
	•	call other agents
	•	merge results back into shared state

This sets the foundation for multi agent systems.


Repository structure

deepAgents/
├── src/deepAgents/
│   ├── state.py           # Extended agent state + reducers
│   ├── todo_tools.py      # Tools for TODO read/write
│   ├── task_tool.py       # Task orchestration helpers
│   ├── file_tools.py      # Virtual file system tools
│   ├── research_tools.py  # Mock / research tools
│   ├── prompts.py         # System + tool usage instructions
│   └── __init__.py
│
├── notebooks/
│   ├── 0_create_agent.ipynb   # Build and visualize the agent graph
│   ├── 1_todo.ipynb           # Task planning with TODOs
│   ├── 2_files.ipynb          # Virtual file system in state
│   ├── 3_subagents.ipynb      # Sub-agents and delegation
│   └── 4_full_agent.ipynb     # End-to-end agent composition
│
├── utils.py
└── README.md


Notebook walkthrough

Each notebook builds on the previous one:

0_create_agent.ipynb
	•	Create a basic LangGraph agent
	•	Define nodes, tools, and state
	•	Visualize the execution graph

1_todo.ipynb
	•	Introduce structured TODO planning
	•	Read/write TODOs via tools
	•	Track agent progress explicitly

2_files.ipynb
	•	Add a virtual file system to agent state
	•	Store intermediate reasoning artifacts
	•	Demonstrate reducer-based merging

3_subagents.ipynb
	•	Introduce sub agents
	•	Delegate tasks
	•	Merge results back into parent state

4_full_agent.ipynb
	•	Compose everything together
	•	A realistic, stateful, multi step agent
	•	Clear separation of planning, execution, and memory

Design philosophy

Agents are not magic.
They are state machines powered by language models.

This repo treats agents as:
	•	deterministic systems with explicit transitions
	•	inspectable graphs, not loops
	•	evolving state, not stateless chats

Who this repo is for

This repo is ideal if you are:
	•	learning LangGraph deeply
	•	building custom agent frameworks
	•	experimenting with agent memory and planning
	•	preparing for AI / LLM / agent interviews
	•	tired of black box “agent wrappers”

This is not a beginner chatbot tutorial.


Status

This is an active learning and experimentation repo.

Planned explorations:
	•	persistent state with checkpointers
	•	human-in-the-loop nodes
	•	failure recovery and retries
	•	parallel node execution
	•	richer multi-agent coordination

Breaking changes are expected.


If this repo helps you

If this repo helped you:
	•	understand agents better
	•	debug LangGraph concepts
	•	think more clearly about agent design

Give it a star and build something weird with it.

That’s the goal.
