# Agentic AI Interview Questions & Answers

A concise interview-preparation guide covering Agentic AI, tool calling,
multi-agent systems, LangChain, and LangGraph.

------------------------------------------------------------------------

## 1. What is Agentic AI?

### Interview Answer

Agentic AI is an AI system where an LLM is not limited to generating a
response. It can **reason about a goal, decide what action to take, call
external tools or APIs, observe results, maintain state, and continue
until the task is completed**.

``` text
User Goal
   ↓
LLM / Agent
   ↓
Reason about next action
   ↓
Select Tool
   ↓
Execute Tool
   ↓
Observe Result
   ↓
Update State
   ↓
Continue or END
```

**LLM → Generates**

**Agent → Reasons + Decides + Acts**

### Memory Trick

**RATO:** Reason → Act → Tools → Observe

------------------------------------------------------------------------

## 2. What is a Multi-Agent System?

### Interview Answer

A multi-agent system contains **multiple specialized agents that
collaborate to achieve an overall goal**. Instead of one agent handling
every responsibility, different agents specialize in different tasks.

``` text
                    Supervisor Agent
                           │
             ┌─────────────┼─────────────┐
             ↓             ↓             ↓
       Product Agent   Review Agent   Inventory Agent
             │             │             │
             ↓             ↓             ↓
       Product API     Review API    Inventory API
             │             │             │
             └─────────────┼─────────────┘
                           ↓
                  Recommendation Agent
                           ↓
                         User
```

-   **Product Agent** → Searches products.
-   **Review Agent** → Analyzes reviews.
-   **Inventory Agent** → Checks availability.
-   **Recommendation Agent** → Combines the results.
-   **Supervisor Agent** → Coordinates the workflow.

### Why use multiple agents?

They can provide separation of concerns, specialization, tool isolation,
modularity, and parallel execution where appropriate.

However, multi-agent architecture should not be used unnecessarily. If
one agent with a few tools can reliably solve the problem, multiple
agents can add unnecessary orchestration complexity.

### Memory Trick

**Single Agent = One worker with many skills**

**Multi-Agent = Team of specialists**

------------------------------------------------------------------------

## 3. How Do You Prevent Multiple Tool Calls from Executing at the Same Time?

### Interview Answer

If I want to prevent multiple tools from executing simultaneously, I
**control concurrency at the orchestration layer instead of relying
entirely on the LLM**.

The LLM may propose multiple tool calls, but the workflow determines
which tool is permitted to execute based on the current state.

``` text
LLM proposes tool calls
        ↓
Orchestrator validates calls
        ↓
Check current workflow state
        ↓
Determine allowed tool
        ↓
Execute ONE permitted tool
        ↓
Update state
        ↓
Invoke agent again
```

Suppose the LLM proposes:

``` text
search_product()
check_inventory()
create_order()
```

We should not blindly execute all three because `check_inventory()` may
require the search result, while `create_order()` requires a selected
and validated product.

The workflow can restrict tools:

``` python
allowed_tools = {
    "SEARCH": ["search_product"],
    "CHECK_INVENTORY": ["check_inventory"],
    "ORDER": ["create_order"]
}
```

If:

``` text
current_step = SEARCH
```

then only `search_product()` is allowed.

Even if the LLM requests `create_order()`, the orchestrator rejects or
postpones it because that action is invalid for the current workflow
state.

### With LangGraph

``` text
START
  ↓
Search Node
  ↓
Inventory Node
  ↓
Validation Node
  ↓
Order Node
  ↓
END
```

The graph explicitly controls the allowed transitions.

For sensitive operations:

``` text
Agent
  ↓
Requests create_order
  ↓
Validation
  ↓
Human Approval
  ↓
Execute create_order
```

### Strong Interview Line

> To avoid simultaneous tool execution, I enforce sequential execution
> through orchestration and workflow state. The LLM can suggest actions,
> but the workflow decides which tool is allowed to execute at the
> current step.

### Memory Trick

**LLM suggests → Orchestrator decides → Tool executes**

------------------------------------------------------------------------

## 4. Sequential vs Parallel Tool Calling

### Sequential

Use sequential execution when one operation depends on another.

``` text
search_product()
      ↓
product_id
      ↓
check_inventory(product_id)
      ↓
create_order(product_id)
```

### Parallel

Parallel execution is appropriate when operations are independent.

``` text
                   Agent
                     │
          ┌──────────┼──────────┐
          ↓          ↓          ↓
 Product Details   Reviews    Competitor Price
          │          │          │
          └──────────┼──────────┘
                     ↓
              Aggregate Results
                     ↓
                    Agent
```

Conceptually:

``` python
results = await asyncio.gather(
    get_product_details(product_id),
    get_reviews(product_id),
    get_competitor_price(product_id)
)
```

Production systems should also consider timeouts, retries, rate limits,
concurrency limits, idempotency, and partial failures.

### Memory Trick

**Independent → Parallel**

**Dependent → Sequential**

------------------------------------------------------------------------

## 5. What is LangChain Used For?

### Interview Answer

LangChain provides abstractions and integrations for building
LLM-powered applications. It helps connect **LLMs with prompts,
structured outputs, tools, retrievers, vector stores, RAG pipelines, and
agent capabilities**.

Common components include:

-   Chat models
-   Prompt templates
-   Structured output
-   Output parsers
-   Tools and tool calling
-   Document loaders
-   Text splitters
-   Embeddings
-   Vector stores
-   Retrievers
-   RAG pipelines
-   Agents

``` text
                    LangChain
                        │
       ┌────────────────┼────────────────┐
       ↓                ↓                ↓
      LLM             Tools             RAG
       │                │                │
Prompt Templates    Tool Calling     Embeddings
Output Parsing      APIs             Vector DB
Structured Output                    Retrievers
```

### Strong Interview Line

> LangChain helps us build and integrate the individual components of an
> LLM application.

### Memory Trick

**Chain = Connect**

------------------------------------------------------------------------

## 6. Why is LangGraph Used in Your Project?

### Interview Answer

We use LangGraph when the agentic workflow is **stateful and contains
multiple steps, conditional routing, loops, tool calls, retries,
persistence, or human approval**.

LangGraph represents the workflow as a graph:

-   **Nodes** → Operations/tasks
-   **Edges** → Transitions
-   **State** → Data shared across workflow steps
-   **Conditional edges** → Dynamic routing
-   **Cycles** → Agent/tool loops
-   **Checkpointing** → Save and resume workflow execution

``` text
START
  ↓
Understand Request
  ↓
Validate
  ↓
Agent
  ↓
Need Tool?
 /       \
YES       NO
 ↓         ↓
Tool     Respond
 ↓
Agent
 ↓
Need Approval?
 /       \
YES       NO
 ↓         ↓
Human     Continue
 ↓
Resume
 ↓
END
```

Example workflow state:

``` python
state = {
    "user_query": "...",
    "intent": "...",
    "tool_results": [],
    "current_step": "...",
    "retry_count": 0,
    "final_response": None
}
```

### Why not just Python if/else?

For a small deterministic workflow, normal Python may be enough.

LangGraph becomes useful when the workflow contains:

``` text
State
+
Conditional Routing
+
Loops
+
Multiple Agents
+
Tool Calls
+
Checkpointing
+
Retries
+
Human Approval
+
Resume After Interruption
```

### Strong Interview Line

> We use LangGraph to orchestrate stateful agent workflows where
> execution can branch, loop, pause, resume, or dynamically route
> depending on intermediate results.

### Memory Trick

**LangChain builds the pieces. LangGraph controls the flow.**

------------------------------------------------------------------------

## 7. LangChain vs LangGraph

  LangChain                           LangGraph
  ----------------------------------- ---------------------------------
  Builds LLM application components   Orchestrates stateful workflows
  Models                              Nodes
  Prompts                             Edges
  Tools                               State
  Retrievers                          Conditional routing
  Vector stores                       Loops/cycles
  Structured output                   Checkpointing
  Agent/tool integrations             Stateful execution

They are commonly used together.

``` text
LangGraph
    │
    │ orchestrates
    ↓
Agent Node
    │
    ├── LangChain Model
    ├── LangChain Tools
    ├── Retriever
    └── Vector DB
```

------------------------------------------------------------------------

## 8. How Does an Agent Know Which Tool to Call?

### Interview Answer

Tools are exposed to the LLM with their **name, description, and input
schema**.

Based on the user's request and available tool definitions, the model
decides which tool is appropriate and produces a structured tool-call
request.

``` python
@tool
def search_product(query: str):
    """Search for products."""
    pass

@tool
def check_inventory(product_id: str):
    """Check whether a product is currently in stock."""
    pass
```

``` text
User request
     ↓
LLM sees available tool schemas
     ↓
LLM selects/proposes tool
     ↓
Application validates request
     ↓
Application executes tool
     ↓
Tool result returned to LLM
     ↓
Final response
```

### Important Distinction

**The LLM selects/proposes the tool.**

**The application/orchestrator actually executes it.**

------------------------------------------------------------------------

## 9. Agent vs Deterministic Workflow

### Deterministic Workflow

The developer defines the sequence:

``` text
A → B → C → D
```

### Agentic Workflow

The agent dynamically decides the next action:

``` text
        Agent
          ↓
     Decide Next Step
      /    |     \
     A     B      C
     ↓     ↓      ↓
        Observe
           ↓
         Agent
```

### Hybrid Workflow

Production systems often combine both:

``` text
Deterministic Workflow
        ↓
     Agent Node
        ↓
Dynamic Tool Selection
        ↓
Deterministic Validation
        ↓
Approval
        ↓
Execution
```

Critical business rules, authorization, security checks, and
irreversible actions should generally remain deterministic rather than
being controlled solely by an LLM.

------------------------------------------------------------------------

## 10. Why Did You Choose an Agentic Architecture?

### Interview Answer

We chose an agentic approach because some decisions cannot be
efficiently represented as a completely fixed workflow.

Depending on the user's request and intermediate tool results, the
system may need to dynamically select different tools or processing
paths.

We use the LLM for **reasoning and dynamic decision-making**, while
keeping critical validations, permissions, and business rules
deterministic.

``` text
LLM
 ↓
Reasoning / Decision Making
 ↓
Orchestrator
 ↓
Tools / APIs
 ↓
Existing Services
 ↓
Databases
```

Agentic AI does **not** mean replacing the entire backend with an LLM.

------------------------------------------------------------------------

# Quick Interview Revision

### What is Agentic AI?

> An AI system that can reason, decide, use tools, observe results,
> maintain state, and continue working toward a goal.

### What is Multi-Agent AI?

> Multiple specialized agents collaborating or coordinating to
> accomplish an overall task.

### How do you prevent multiple tools from executing simultaneously?

> I control tool execution through the orchestration layer and workflow
> state. The LLM may propose multiple actions, but only the tool
> permitted for the current workflow step is executed.

### When do you use parallel tool calling?

> When tool calls are independent.

### When do you use sequential tool calling?

> When one tool depends on the output or successful completion of
> another.

### What is LangChain?

> LangChain provides components and integrations for building LLM
> applications, including models, prompts, tools, structured output,
> retrievers, vector stores, RAG, and agents.

### What is LangGraph?

> LangGraph is used to orchestrate stateful agent workflows involving
> nodes, edges, conditional routing, loops, persistence, checkpointing,
> and human-in-the-loop.

### LangChain vs LangGraph?

> LangChain helps build the components; LangGraph orchestrates their
> execution.

### Who decides which tool to call?

> The LLM can select or propose the tool based on the tool schema, but
> the application/orchestrator validates and executes it.

------------------------------------------------------------------------

# Final Mental Model

``` text
                     AGENTIC AI
                         │
                Reason + Decide + Act
                         │
                    LLM / Agent
                         │
              ┌──────────┴──────────┐
              ↓                     ↓
          LangChain             LangGraph
              │                     │
        Build Components        Orchestrate Flow
              │                     │
      ┌───────┼────────┐      ┌─────┼─────┐
      ↓       ↓        ↓      ↓     ↓     ↓
     LLM    Tools     RAG   State  Route  Loop
              │
         Tool Calling
              │
       ┌──────┴───────┐
       ↓              ↓
 Sequential        Parallel
       │
       ↓
   APIs / Services / Databases
```

## One Sentence to Remember

**LangChain gives the agent capabilities; LangGraph orchestrates those
capabilities; tools let the agent interact with external systems; state
tracks workflow progress; and multi-agent systems divide
responsibilities among specialized agents.**
