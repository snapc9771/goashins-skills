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
| **Law of Chunking** | George A. Miller (1956) | The human working memory can only hold 7±2 pieces of information simultaneously. Information must be grouped logically to bypass cognitive limits. | The skill strictly enforces grouping bounds. If a topic is vast, features are rolled up into overarching macro-capabilities to ensure no module exceeds 7 subtopics. |

---

## The 4-Stage Roadmap Pattern

**PRE-FLIGHT CHECK (The Hidden Brain Dump):** Before generating the roadmap, you MUST use a hidden `<thinking>` block. In this block, you must perform a "brain dump" by listing out ALL the granular, detailed topics (Level 4 concepts) of the subject. Only *after* you have gathered the granular details should you group them into higher-level categories (Bottom-Up Clustering). This ensures no critical details are missed before you output the roadmap.

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
- **4-Level Bottom-Up Taxonomy**: The curriculum must be structured up to 4 levels deep to balance vastness with readability (Progressive Disclosure):
  - **Level 1 (Domain):** The macro-bucket (e.g., `### 1️⃣ Domain: Data Architecture`).
  - **Level 2 (Category):** The major pillar. Add visual prerequisites here if applicable (e.g., `**A. Relational Modeling** [Prereq: Fundamentals]`).
  - **Level 3 (Sub-Category):** The grouping of features (e.g., `* **Object Types:**`).
  - **Level 4 (Granular Details):** The specific technical features. **CRITICAL:** Level 4 MUST be formatted horizontally in italics on the same line as Level 3 to prevent a massive "Wall of Text". (e.g., `*Standard vs Custom, External IDs.*`).
- **Sequencing**: You MUST order the modules pedagogically (e.g., Simple to Complex, Prerequisites First).
- **Zero Redundancy via Tagging**: Do NOT duplicate topics across domains. Use `[Cross-cutting]` tags to indicate relationships.

**Example Format**:
```markdown
### 1️⃣ Domain: Backend Infrastructure
**A. Database Management** `[Prerequisite: Computer Science 101]`
* **Relational Storage:** *SQL, Table Joins, Primary Keys, Normalization.*
* **NoSQL Storage:** *Document Stores, Key-Value, Graph Databases.*

**B. API Ecosystem**
* **REST APIs:** *GET/POST methods, Status Codes, JSON payloads.*
```

---

### Stage 4: 🤝 The Handoff (Next Steps)

**Cognitive purpose**: Transition the user from the "mapping" phase to the "deep learning" phase.

**Rules**:
- Explicitly tell the user: *"Pick any italicized concept from Level 4, and I will instantly run the `deep-learning-mentor` skill on that exact topic."*
- Transition them from the "mapping" phase to the "deep learning" phase by treating the Level 4 italicized concepts as an interactive menu.

---

## Anti-Patterns to Avoid
1. **The Encyclopedic Dump**: Do not try to teach the actual concepts in this skill. This skill is strictly for *indexing* and *mapping*. Keep descriptions to a few words.
2. **Circular Dependencies**: Ensure Module III does not require knowledge from Module IV. The sequence must be logically traversable from top to bottom.
3. **Overlapping Categories**: If two modules sound similar, combine them or sharply define their distinct boundaries.
