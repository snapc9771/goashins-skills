---
name: learning-roadmap
description: >-
  Creates an evidence-based, high-level index and structural roadmap for any topic before diving into details. Acts as a prequel to the deep-learning-mentor skill. Use whenever the user wants an overview, syllabus, index, or structured learning plan for a new subject to establish an Advance Organizer and avoid cognitive overload.
---

# Learning Roadmap — Cognitive Structuring Skill

## Cognitive Science Foundation

This skill acts as the necessary **prequel** to deep, detailed learning. It is designed to build a cognitive scaffold *before* the learner is overwhelmed with mechanics and details. Its design is rooted in peer-reviewed educational psychology:

| Principle | Researcher(s) | Core Finding | How This Skill Applies It |
| :--- | :--- | :--- | :--- |
| **Elaboration Theory (The Zoom-Lens)** | Charles Reigeluth (1979) | Instruction should start with an "Epitome"—the simplest, most fundamental overview—before progressively elaborating into complex subtopics. | The response always begins with a high-level structural overview before listing the detailed curriculum. |
| **Advance Organizers** | David Ausubel (1960) | Providing a structural cognitive scaffold *before* detailed learning begins significantly improves the integration and retention of new knowledge. | This skill generates the overarching framework (the organizer) that prepares the brain for the `deep-learning-mentor`. |
| **Concept Mapping** | Joseph Novak (1970s) | Knowledge is best organized hierarchically, from general/inclusive concepts at the top to specific ones at the bottom, using cross-links to show relationships. | The curriculum is structured strictly hierarchically. Redundancies are handled via "cross-cutting" tags rather than duplicating topics. |

---

## The 4-Stage Roadmap Pattern

**PRE-FLIGHT CHECK:** Before generating the roadmap, briefly use your search tools to identify the standard, most up-to-date industry or academic consensus on how this topic is structured.

For EVERY roadmap request, structure your response using these exact sections in this exact order.

### Stage 1: 🚁 The Epitome (The 10,000-Foot View)

**Cognitive purpose**: Establish the absolute core essence of the topic before breaking it down (Reigeluth's Elaboration Theory).

**Rules**:
- State what the topic is in 2-3 sentences.
- Identify the **primary goal** or **problem** the entire field/topic exists to solve.
- Keep it highly abstract and inclusive. No jargon.

---

### Stage 2: 🗺️ The Structural Blueprint (Concept Map)

**Cognitive purpose**: Provide a visual Advance Organizer so the learner can see the boundaries and major pillars of the topic at a glance.

**Rules**:
- Generate a `mermaid` diagram (usually a `mindmap` or a top-down `flowchart TD`).
- Include ONLY the major pillars (3 to 6 top-level categories).
- Do not clutter this diagram with subtopics; keep it clean and structural.

---

### Stage 3: 📑 The Sequenced Curriculum (The Index)

**Cognitive purpose**: Provide a structured, progressive path through the material.

**Rules**:
- Break the topic down into **Modules** (I, II, III) and **Subtopics** (A, B, C).
- **Sequencing**: You MUST order the modules pedagogically (e.g., Simple to Complex, Prerequisites First, or Core to Periphery).
- **Brief Descriptions**: Each subtopic should have a 4-7 word micro-description explaining *what* it covers.
- **Zero Redundancy via Tagging**: A common issue in learning is when a concept applies to multiple areas (e.g., "Security" applies to Databases, APIs, and UIs). Do NOT duplicate the topic in every module. Instead:
  - Create a dedicated module for it, OR
  - Use a tag like `[Cross-cutting]` or `[Applies to Module II]` to indicate the relationship without repeating the learning material.

**Example Format**:
```markdown
### Module I: Fundamentals (The "What" and "Why")
* **A. Core Primitives** — The basic building blocks of the system.
* **B. Architecture Patterns** — How primitives connect. `[Cross-cutting: Applies to all downstream modules]`

### Module II: Intermediate Mechanics
* **A. State Management** — Handling data over time. *(Prerequisite: Module I.A)*
```

---

### Stage 4: 🤝 The Handoff (Next Steps)

**Cognitive purpose**: Transition the user from the "mapping" phase to the "deep learning" phase.

**Rules**:
- Ask the user which specific Module or Subtopic they want to dive into first.
- Explicitly recommend they use the `deep-learning-mentor` skill (or just ask to "deep dive") when they select a topic, so you can apply the 7-stage cognitive response pattern to that specific node.

---

## Anti-Patterns to Avoid
1. **The Encyclopedic Dump**: Do not try to teach the actual concepts in this skill. This skill is strictly for *indexing* and *mapping*. Keep descriptions to a few words.
2. **Circular Dependencies**: Ensure Module III does not require knowledge from Module IV. The sequence must be logically traversable from top to bottom.
3. **Overlapping Categories**: If two modules sound similar, combine them or sharply define their distinct boundaries.
