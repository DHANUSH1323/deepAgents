# 🧠 deepAgents

**deepAgents** is a from-scratch exploration of **stateful, graph-based AI agents** built using **LangGraph + LangChain**, with a strong focus on how agents actually work internally.

Instead of hiding complexity behind abstractions, this repo makes agent **state**, **planning**, **memory**, and **execution** explicit and inspectable.

If you want to understand what really happens inside an agent loop, this repo is for you.

---

## 🚀 Why this repo exists

Most “agent” examples online:

- Hide state mutations  
- Blur steps into a single black-box loop  
- Rely on magic wrappers  

deepAgents takes the opposite approach.

This repo is about:

- Explicit agent state  
- Graph nodes as execution steps  
- Reducers for safe state merging  
- Task planning via TODOs  
- Virtual file systems inside agent memory  
- Tool-driven state updates  
- Sub-agents and composition  

In short: **agents as engineered systems, not demos.**

---

## 🧩 What you’ll learn from this repo

### 1️⃣ Agent state, done properly
You’ll see how to extend **LangGraph’s AgentState** to include:

- Structured TODO lists  
- Long-lived virtual files  
- Safe merging via reducers  

This enables long-running, recoverable agents.

---

### 2️⃣ Task planning with TODOs
Agents don’t just “respond.” They:

- Create tasks  
- Track progress  
- Update status *(pending, in_progress, completed)*  
- Reason about what’s left  

This mirrors how humans work and makes agent behavior **debuggable**.

---

### 3️⃣ Virtual file system inside agent memory
Instead of bloating prompts:

- Agents write intermediate results to files  
- Files persist across steps  
- State stays compact and cheap  

This is **context offloading**, not prompt stuffing.

---

### 4️⃣ Tool-driven state mutation
Tools are first-class citizens:

- Tools can read/write TODOs  
- Tools can read/write files  
- Tools can return Commands to mutate state  

State changes are **explicit and auditable**.

---

### 5️⃣ Sub-agents and composition
Agents can:

- Delegate work  
- Call other agents  
- Merge results back into shared state  

This sets the foundation for **multi-agent systems**.

---

## 📁 Repository structure

deepAgents/ ├── src/deepAgents/ │   ├── state.py           # Extended agent state + reducers │   ├── todo_tools.py      # Tools for TODO read/write │   ├── task_tool.py       # Task orchestration helpers │   ├── file_tools.py      # Virtual file system tools │   ├── research_tools.py  # Mock / research tools │   ├── prompts.py         # System + tool usage instructions │   └── init.py │ ├── notebooks/ │   ├── 0_create_agent.ipynb   # Build and visualize the agent graph │   ├── 1_todo.ipynb           # Task planning with TODOs │   ├── 2_files.ipynb          # Virtual file system in state │   ├── 3_subagents.ipynb      # Sub-agents and delegation │   └── 4_full_agent.ipynb     # End-to-end agent composition │ ├── utils.py └── README.md



---

## 📓 Notebook walkthrough

Each notebook builds on the previous one.

**0_create_agent.ipynb**
- Create a basic LangGraph agent  
- Define nodes, tools, and state  
- Visualize the execution graph  

**1_todo.ipynb**
- Introduce structured TODO planning  
- Read/write TODOs via tools  
- Track agent progress explicitly  

**2_files.ipynb**
- Add a virtual file system to agent state  
- Store intermediate reasoning artifacts  
- Demonstrate reducer-based merging  

**3_subagents.ipynb**
- Introduce sub-agents  
- Delegate tasks  
- Merge results back into parent state  

**4_full_agent.ipynb**
- Compose everything together  
- A realistic, stateful, multi-step agent  
- Clear separation of planning, execution, and memory  

---

## 🧠 Design philosophy

Agents are not magic.  
They are **state machines powered by language models**.

This repo treats agents as:

- Deterministic systems with explicit transitions  
- Inspectable graphs, not loops  
- Evolving state, not stateless chats  

---

## 👀 Who this repo is for

This repo is ideal if you are:

- Learning **LangGraph** deeply  
- Building custom agent frameworks  
- Experimenting with agent memory and planning  
- Preparing for AI / LLM / agent interviews  
- Tired of black-box “agent wrappers”  

This is **not** a beginner chatbot tutorial.

---

## 🚧 Status

This is an **active learning and experimentation repo.**

Planned explorations:

- Persistent state with checkpointers  
- Human-in-the-loop nodes  
- Failure recovery and retries  
- Parallel node execution  
- Richer multi-agent coordination  

Breaking changes are expected.

---

## ⭐ If this repo helps you

If this repo helped you:

- Understand agents better  
- Debug LangGraph concepts  
- Think more clearly about agent design  

Give it a ⭐ and build something weird with it.  
That’s the goal.
