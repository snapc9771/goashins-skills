---
name: learning-roadmap
description: >-
  Creates a research-informed, hierarchical learning roadmap and revision index
  for any topic. Acts as a prequel to the deep-learning-mentor skill. Builds a
  calibrated Master Index, elaborates qualifying concepts into grouped
  Sub-Indexes, and independently controls detail (Detailed or Index-Only) and
  tracking (Checklist or Non-Checklist). Defaults to Detailed + Checklist.
  Use for an overview, syllabus, index, revision plan, or learning tracker.
---

# Learning Roadmap — Cognitive Structuring Skill

## Cognitive Science Foundation

This skill acts as the necessary **prequel** to deep, detailed learning. Its content architecture draws on educational psychology and instructional design:

| Principle | Researcher(s) | Core Finding | How This Skill Applies It |
| :--- | :--- | :--- | :--- |
| **Elaboration Theory (The Zoom-Lens)** | Charles Reigeluth (1979) | Start with an Epitome, then recursively zoom in to elaborated layers, periodically zooming out for synthesis. | Detailed output begins with Epitome + Blueprint. Sub-Indexes elaborate qualifying concepts, grouped under their parent root. |
| **Advance Organizers** | David Ausubel (1960) | A structural scaffold before learning significantly improves retention. | Detailed output generates an Epitome and Blueprint before the index. Index-Only output omits this scaffold, regardless of checklist choice. |
| **Concept Mapping** | Joseph Novak (1970s) | Knowledge is best organized hierarchically, with cross-links for relationships. | The curriculum remains hierarchical. `[Cross-cutting]` tags identify shared concepts. Sub-Index headers carry their full path. |
| **Progressive Disclosure** | HCI & Instructional Design Research | Detailed information should only surface when complexity warrants it. Prevents overload. | The Master Index provides the overview. Only qualifying concepts receive Sub-Indexes, placed immediately after their parent root block. |

The foundation determines **what to include and elaborate**. The display rules below determine **how to present it**. Do not change the content selection or decision boundary merely to fit a visual pattern.

---

## Output Choices (Two Independent Axes — Never Ask the User)

Choose **detail** and **tracking format** separately. A signal on one axis never selects or cancels a choice on the other. Explicit instructions override inferred signals on their own axis. Do not present a mode menu. With no mode instructions, produce **Detailed + Checklist**.

### Axis 1: Detail

- **Detailed (default; `full mode` is an alias):** Epitome → Blueprint → grouped Master Index and Sub-Indexes → Handoff. Use when no detail level is requested, or when the user asks for a detailed/full roadmap, the Epitome and Blueprint, or an explanation alongside the roadmap.
- **Index-Only:** Output only the grouped Master Index and Sub-Indexes. Omit Epitome, Blueprint, stage labels, pre-flight notes, introduction, and Handoff. Use for `index only`, `just index`, `quick`, `summary`, `table only`, or `no explanation`, or clear context of rapid expert revision. `Table only` is a brevity signal; do not force a table that flattens the hierarchy.

### Axis 2: Tracking Format

- **Checklist (default):** Render terminal granular concepts as vertical Markdown `- [ ]` checkboxes. Use when no tracking format is requested, or for `checklist`, `tracker`, `checkboxes`, `todo`, `tasks`, or `progress`. A checkbox marks a concept to study or revise, never a structural heading or a concept expanded into children.
- **Non-Checklist:** Render terminal granular concepts as concise inline, comma-separated text. Use when the user explicitly asks for `non-checklist`, `without checkboxes`, `no checklist`, or inline/plain details.

| Request | Detail | Tracking format |
| :--- | :--- | :--- |
| No mode specified | Detailed | Checklist |
| `detailed without checklist` | Detailed | Non-Checklist |
| `index only checklist` | Index-Only | Checklist |
| `index only without checklist` | Index-Only | Non-Checklist |

---

## User Calibration: 3-Tier Inference (All Modes)

Infer the appropriate granularity without asking the user:

1. **Explicit context:** Use the role or goal the user gave in the conversation (for example, an architect preparing for an advanced certification).
2. **Topic signal:** Let the scope of the topic guide the abstraction level. A broad architecture topic needs different granularity from a single feature.
3. **Professional practitioner default:** If context and topic are ambiguous, assume someone with hands-on experience who needs a revision index.

Respect natural-language modifiers such as `for a junior admin` or `for architect prep` as explicit overrides. The same calibration applies in every output mode.

---

## Internal Pre-Flight: Build the Content Before Formatting

Complete this planning silently before writing the visible answer. The response must begin with the requested output, never with planning notes, a brain dump, or a reasoning tag.

1. **Gather:** Identify the granular named concepts needed for a useful, reasonably complete map of the requested scope. Check coverage against the user's goal and level.
2. **Cluster bottom-up:** Group details into sub-categories, categories, and domains where those distinctions are meaningful. Preserve pedagogical sequence and avoid overlap.
3. **Apply the Decision Boundary:** Evaluate each substantive sub-category for a Sub-Index using the rule below. Mark only those that qualify.
4. **Elaborate qualifying roots:** For each qualifying sub-category, organize a focused second pass: the existing sub-category root → Sub-Index groups → Sub-Index items → terminal granular details. Do not create a third pass.
5. **Plan local placement:** Associate each Sub-Index with its parent root block so it can appear immediately after that block's Master Index portion.
6. **Choose the visible entry level:** Apply adaptive depth compression only after the conceptual map is sound. Omit redundant outer wrappers; do not remove concepts, recategorize them to satisfy a numeric threshold, or change which Sub-Indexes qualify.

---

## Conceptual Hierarchy and Adaptive Entry

The Master Index has up to four conceptual levels: **Domain → Category → Sub-Category → granular concepts**. A qualifying Sub-Category receives one further four-position view: **that Sub-Category → Sub-Index Group → Sub-Index Item → granular details**. This is the existing two-pass architecture; a Sub-Index does not generate another Sub-Index.

Display the hierarchy from the first level that adds useful information:

| Topic scope | Visible root | Typical shape |
| :--- | :--- | :--- |
| Several independent, broad pillars | Domain | `I.` → `A.` → `1.` → details |
| A subject within one domain, with distinct categories | Category | `A.` → `1.` → details |
| A focused feature or concept | Sub-Category | `1.` → details, with an expansion only if it qualifies |

The number of top-level clusters can inform the choice, but is not a rule. Do not create six domains to make a topic look vast, or relabel true domains as categories because there are fewer than six. If a root has only one meaningful child, suppress that redundant wrapper when doing so keeps the topic's meaning clear. Across all modes, omitted ancestors are absent from visible numbering and references.

### Display addresses

Use the following labels consistently. These are **address positions**, not a demand for seven levels in every branch:

| Position | Meaning | Label |
| :--- | :--- | :--- |
| L1 | Domain | Upper Roman: `I.`, `II.` |
| L2 | Category | Upper alpha: `A.`, `B.` |
| L3 | Sub-Category | Arabic: `1.`, `2.` |
| L4 | Master Index granular concepts | Inline in Non-Checklist; vertical checkboxes when terminal in Checklist |
| L5 | Sub-Index Group | Lower alpha: `a.`, `b.` |
| L6 | Sub-Index Item | Lower Roman: `i.`, `ii.` |
| L7 | Sub-Index granular details | Inline in Non-Checklist; vertical checkboxes when terminal in Checklist |

Addresses concatenate only visible ancestors: `I.A.2`, `A.2`, or `2`. Sub-Index paths continue from the referenced root, such as `I.A.2.a.i`. Restart child labels under each parent. A reference tag and its Sub-Index header must use the same address. Do not imply omitted levels with empty prefixes.

---

## Grouped Root Blocks (All Modes)

Each visible root is a self-contained block. Present its Master Index portion first, then the Sub-Indexes for qualifying sub-categories within that root, then move to the next root. The root is a Domain, Category, or Sub-Category depending on the topic scope. Never collect all Sub-Indexes at the end of the document.

Use a clear visual rhythm like the examples below: a short root heading, spaced category labels, numbered sub-categories, then a compact local Sub-Indexes section. Use whitespace and a simple `---` divider between roots when helpful. Never use ASCII box drawing or long character-rule banners.

Use a small, consistent emoji vocabulary as wayfinding: `🟦` for Domain roots, `🟩` for Category roots, `🟨` for Sub-Category roots, and `📑` for local Sub-Indexes. Emojis belong on these headings, not on every item or checkbox. Keep the alphanumeric address visible beside the emoji. The visual markers support the hierarchy; the text and addresses carry its meaning.

For a broad Domain root, use `## 🟦 I. Domain Name`, a bold `A. Category Name` line, and a Markdown `1.`/`2.` list for its Sub-Categories. For a Category root, use `## 🟩 A. Category Name` and the same numbered Sub-Category list. For a focused Sub-Category root, use `## 🟨 1. Sub-Category Name` followed by its details or local Sub-Index. Use actual Markdown numbering for L3 so the rows scan cleanly. Roman and alphabetic addresses are literal text, because Markdown ordered lists do not reliably render those markers.

### Master Index rows

- Bold only category and concept labels. Keep reference tags, prerequisite tags, and granular details in plain text; do not bold whole detail lines.
- In Non-Checklist format, keep terminal granular concepts concise and inline on the same row as their parent, separated by commas. Do not use italics as a navigation device.
- In Checklist format, place terminal granular concepts on separate, properly indented `- [ ]` lines. L4 and L7 are the usual leaf positions, but a branch can end sooner. Put the checkbox on the actual leaf instead of forcing empty lower levels.
- A sub-category with a Sub-Index carries a compact pointer. Render the entire reference tag as inline code, including its brackets, for example: `` `[↳ Ref: I.A.2]` ``. Its Master Index row serves as a pointer; avoid duplicating checkboxes there for concepts tracked in its Sub-Index.
- Add `[Prerequisite: X]` where pedagogical sequencing requires it. Mark a shared sub-category `[Cross-cutting]` instead of repeating its full content in multiple roots. Keep such tags readable beside the relevant concept.

### Sub-Indexes

- After the Master Index portion of a root, use one `---` divider and `#### 📑 SUB-INDEXES (I.)` or the corresponding visible root address if any sub-categories qualify. Give each Sub-Index a compact heading containing its exact parent address and name, for example `**[ I.A.2 ] Relationship Topologies**`.
- Under each Sub-Index heading, use nested Markdown bullets with literal lower-alpha group labels (`a.`, `b.`) and lower-Roman item labels (`i.`, `ii.`). Always show L6 when a group has items; do not jump from `a.` straight to terminal details. Indent L6 under L5 and checkboxes under L6. Keep inline terminal details on the L6 row in Non-Checklist format.
- Show the relationship through the matching pointer address and local placement. Do not use detached boxes or a separate appendix.
- Include only the elaboration justified by the Decision Boundary. Stop before configuration values, tutorial steps, or behavioral teaching.

### Layout examples

Non-Checklist format, with either detail choice:

```markdown
## 🟦 I. Data and Storage Architecture

**A. Relational Data Modeling**

1. **Object Architecture:** standard objects, custom objects, schema inspection
2. **Relationship Topologies** `[↳ Ref: I.A.2]`

---

#### 📑 SUB-INDEXES (I.)

**[ I.A.2 ] Relationship Topologies**

- **a. Coupling choices**
  - **i. Master-detail:** ownership inheritance, cascade deletion, reparenting
  - **ii. Lookup:** independent ownership, optional relationships
```

Checklist format, with either detail choice:

```markdown
## 🟦 I. Data and Storage Architecture

**A. Relational Data Modeling**

1. **Object Architecture:**
   - [ ] Standard objects
   - [ ] Custom objects
   - [ ] Schema inspection
2. **Relationship Topologies** `[↳ Ref: I.A.2]`

---

#### 📑 SUB-INDEXES (I.)

**[ I.A.2 ] Relationship Topologies**

- **a. Coupling choices**
  - **i. Master-detail:**
    - [ ] Ownership inheritance
    - [ ] Cascade deletion
    - [ ] Reparenting
  - **ii. Lookup:**
    - [ ] Independent ownership
    - [ ] Optional relationships
```

Focused topic, Index-Only + Non-Checklist:

```markdown
## 🟨 1. Core Concepts

- **Evaluation timing:** save order, formula evaluation
- **Error presentation:** field-level messages, page-level messages

## 🟨 2. Formula Functions `[↳ Ref: 2]`

---

#### 📑 SUB-INDEXES (2.)

**[ 2 ] Formula Functions**

- **a. Logical operators**
  - **i. AND and OR:** syntax requirements, nesting limits
```

The examples illustrate display only. Choose the actual concepts, depth, and number of branches from the requested subject and the Decision Boundary.

---

## Detailed Output Wrapper

In Detailed output, place these sections around the grouped root blocks regardless of tracking format:

### Stage 1: 🚁 The Epitome

State what the topic is in 2–3 sentences. Identify the primary goal or problem the field addresses. Keep it abstract and accessible, without teaching the subtopics.

### Stage 2: 🗺️ The Structural Blueprint

Generate a `mermaid mindmap` or `flowchart TD` showing only the major meaningful pillars of this roadmap. Usually show 3–6 for a broad topic; show fewer for a narrow topic rather than inventing pillars. Keep detailed concepts in the index.

### Stage 3: 📑 The Grouped Root Blocks

Render the Master Index and qualified Sub-Indexes using the same content and layout rules as the other modes.

### Stage 4: 🤝 The Handoff

After all root blocks, briefly invite the user to pick any terminal granular concept from the Master Index or a Sub-Index for a deep-learning-mentor explanation of that exact topic.

---

## The Decision Boundary (Granularity Rule — All Modes)

> **The Architect's Decision Boundary:** Elaborate a Sub-Category into a Sub-Index if its granular concepts contain multiple **independently decidable concepts** — concepts with their own names in official documentation that represent distinct architectural choices — **and** each has meaningful sub-components that a practitioner at the calibrated level would evaluate separately.

Apply this to the conceptual Sub-Category even when its visible address begins at `1.` because outer wrappers were compressed. Presentation mode, root labels, and checklist formatting must not change the qualification result.

**Stop elaborating when you reach:**

- Configuration values (for example, `Private` as an OWD option: list it, do not break it down further).
- Implementation steps (tutorial content, not index content).
- Behavioral mechanics (deep-learning-mentor territory).

**Quick litmus, applied implicitly as calibrated judgment rather than a per-item checklist:**

- Does the concept have its own name and official documentation page? Include it.
- Could it be a standalone interview question or exam topic? Include it.
- Is it only a setting, parameter, or internal behavior within a larger named concept? Stop. It is a terminal detail or deep-learning-mentor territory.

**Recursion hard stop:** Sub-Indexes do not generate their own Sub-Indexes. The two-pass architecture stops at Pass 2. Deeper exploration belongs to deep-learning-mentor.

---

## Anti-Patterns to Avoid

1. **Detached Sub-Indexes:** Never append every Sub-Index at the document bottom. Place each immediately after its parent root block's Master Index portion.
2. **Asking which concepts to elaborate:** Apply the Decision Boundary and generate the complete appropriate index in one response, without pauses or mode questions.
3. **Encyclopedic teaching:** This skill maps and indexes. Keep descriptions brief; leave mechanisms and tutorials to deep-learning-mentor.
4. **Circular dependencies:** Make the sequence pedagogically traversable from top to bottom. Do not require a later root to understand an earlier one without an explicit prerequisite.
5. **Overlapping categories:** Combine near-duplicates or sharply define their boundaries. Use `[Cross-cutting]` where a concept spans roots.
6. **Visible pre-flight work:** Never print the brain dump, clustering rationale, qualification analysis, or reasoning tags.
7. **Framing in Index-Only output:** Index-Only contains only structured index blocks, whether or not checkboxes are used; no stage names, preamble, diagram, or Handoff.
8. **Decorative index layout:** Avoid ASCII boxes, long character rules, repeated icons on every row, whole-line bolding, and italics used solely as pointers. Use the limited heading emojis above.
9. **Artificial depth or duplicate tracking:** Do not create empty ancestors, force a cluster count, add levels to satisfy the address scheme, or put checkboxes on both a pointer and the same concept's expansion.

## Final Readability Check

Before sending, inspect the visible response as an index: Detailed output begins with the Epitome; Index-Only begins with the first index root. The tracking choice changes only terminal detail presentation. Use Roman Domain addresses rather than `DOMAIN 1` labels, and show no internal plan. Each Sub-Index sits under its root, each pointer matches its Sub-Index address, and reference tags appear as inline code. Lower-Roman `i.` items appear between `a.` groups and terminal details. Checkboxes appear only on leaves when Checklist is selected. If the rendering looks like a wall of text, add spacing or a simple root divider without adding explanations or changing the concept map.
