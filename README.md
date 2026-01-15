# Semantic Todo Engine

This repository is the starting point for building a **semantic todo system** that treats tasks as meaning, not strings.

The goal is to build a working system where todos are embedded as vectors and retrieved by similarity, enabling search, grouping, and reasoning based on intent rather than exact wording.

This is a build-first project. The emphasis is on producing something functional, understanding trade-offs, and iterating based on real behavior—not speculation.

---

## Why This Project

Traditional todo apps are optimized for:
- Exact text matching
- Manual categorization
- Rigid structures

This project explores a different premise:

> If todos are represented as vectors, you can search and organize them by semantic similarity.

That unlocks:
- Finding related tasks even when phrasing differs
- Grouping todos by theme or intent
- Detecting overlap and duplication
- Querying with vague or incomplete ideas and still getting useful results

---

## Core Goal

Build a todo system where:
- Todos are written in natural language
- Each todo is embedded into a vector
- Queries are also vectors
- Retrieval is based on similarity, not keywords

---

## Planned Capabilities

- [ ] Create todos as free-form text
- [ ] Convert todos into vector embeddings
- [ ] Store embeddings in a vector database
- [ ] Perform similarity search over todos
- [ ] Rank results by relevance
- [ ] Query using:
  - Natural language
  - Another todo
  - Partial or high-level intent

---

## Mandatory Intelligence Loop

Every intelligent action follows this pipeline:

User intent (natural language)

Embedding-based retrieval (vector DB)

Context assembly

LLM reasoning constrained to retrieved context

Structured output (not prose when possible)

---

## Open Design Space

These questions are intentionally left open and will be answered through implementation:

- How small can a todo be before embeddings lose signal?
- Should completed todos remain searchable?
- How should metadata (priority, date, tags) interact with vectors?
- When does vector search outperform hybrid approaches?

---

## Expansion Ideas (After Core Works)

- [ ] Automatic clustering of todos
- [ ] Duplicate and near-duplicate detection
- [ ] Suggested todos based on existing ones
- [ ] Time-aware relevance decay
- [ ] Hybrid vector + keyword retrieval


## Updated Capabilities (LLM-Required)
#1. Semantic Search (LLM-Interpreted)

Retrieval finds candidates

LLM explains why they match

LLM can re-rank or filter

Example:

“Find tasks that are probably blockers”

LLM interprets “blocker” using retrieved tasks only.

# 2. Dynamic Grouping (LLM-Synthesized)

Vector clustering proposes groups

LLM names and explains clusters

Clusters are ephemeral, not stored

# 3. Intent-Aware Prioritization

LLM answers:

“What should I work on next?”

“What has been lingering too long?”

“What is urgent but not explicit?”

LLM reasoning is bounded by:

task content

timestamps

status

### 4. Meta-Reasoning Over Tasks

LLM can:

Summarize current workload

Detect avoidance patterns

Identify scope creep or overload

Generate reflective insights

This is where learning happens.

Revised Architecture (Still Minimal)

User Intent
   ↓
Embed Query
   ↓
Vector Retrieval (Qdrant)
   ↓
Context Window Assembly
   ↓
LLM Reasoning (OpenAI)
   ↓
Structured Result


---

## Scope and Expectations

- Not a production app
- Not optimized for scale
- Explicitly experimental

Progress is measured by:
- Working code
- Clear mental models
- Fewer black boxes

---

## Current Status

- Initialization phase
- Architecture intentionally flexible
- No stable API yet

---

## License

MIT.
