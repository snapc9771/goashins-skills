# goashins-skills

Two complementary skills for learning technology, engineering, mathematics, and science:

- **`learning-roadmap`** maps what to learn, how concepts connect, and what comes first.
- **`deep-learning-mentor`** explains why a concept exists, how it works, and when its trade-offs matter.

**Map the subject → choose a concept → build understanding.** Use either skill independently or follow the two-step workflow.

## ✨ What problem does this solve?

Learning a technical subject often feels like opening a map with no “You are here” marker.

You can find endless tutorials, documentation pages, and AI explanations—but it is still hard to answer:

- What are the important parts of this topic?
- What should I learn first?
- Which concepts are connected, and which are separate?
- When I choose an approach, what trade-off am I actually making?

`goashins-skills` solves this in two steps:

1. **🗺️ Find your bearings.** `learning-roadmap` turns a large topic into a structured path: the major areas, prerequisites, and concepts worth exploring.
2. **🔬 Build understanding.** `deep-learning-mentor` takes one concept from that path and explains its purpose, mechanism, examples, trade-offs, and limits.

The result is not just more information. It is a clearer route from *“I’ve heard these terms”* to *“I understand how to reason about this.”*

## 🚀 Getting started

### 1. Install the skills

In Codex, ask the built-in skill installer:

```text
Use $skill-installer to install both skills from snapc9771/goashins-skills:
skills/learning-roadmap and skills/deep-learning-mentor.
```

The installer copies the complete skill folders, including supporting references,
into your local skills directory (normally `~/.codex/skills`). You can use the
skills on your next turn. If a copy is already installed, review and sync its
changes before replacing it; the installer does not overwrite existing folders.

These are Markdown instruction packages. They require no application server,
API key, or build step. Source verification uses the tools available in your host;
Mermaid rendering depends on the viewer.

### 2. Start with a roadmap

```text
Use $learning-roadmap to create a detailed checklist for distributed systems.
I understand REST APIs and SQL; I want to understand coordination and failure recovery.
```

### 3. Explore a concept

```text
Use $deep-learning-mentor to explain vector clocks from that roadmap.
Use developed depth and a free layout.
```

You can also start directly with the mentor. Give it your topic, learning goal,
relevant background, and any depth or layout preference. It uses established
context and asks when an unresolved choice would materially change the explanation.

## 🗺️ Learning Roadmap

[Read the skill](skills/learning-roadmap/SKILL.md)

The default **Detailed + Checklist** output contains a short orientation
(the *Epitome*), a Mermaid overview, and a sequenced Master Index. Complex
sub-categories receive local Sub-Indexes beside their parent block, followed by
a handoff to deeper learning.

Two independent choices control the output:

| Choice | Default | Alternative |
| --- | --- | --- |
| Detail | **Detailed:** orientation, diagram, index, and handoff | **Index-Only:** just the organized index blocks |
| Tracking | **Checklist:** checkboxes on terminal study concepts | **Non-Checklist:** concise inline concepts |

Shared prerequisites appear before their applications and are covered once.
Coverage checks look for missing areas and distinct architectural choices hidden
inside generic labels. Sub-Indexes stop after one expansion pass; mechanisms and
tutorials belong in the mentor.

```text
Use $learning-roadmap for an index-only revision map of OAuth 2.0 without checkboxes.
```

## 🔬 Deep Learning Mentor

[Read the skill](skills/deep-learning-mentor/SKILL.md)

The mentor selects **purpose, depth, layout, and scope independently**. It teaches
through causal reasoning and resolved examples, with sources and consequential
boundaries carried through the explanation.

### Six explanation purposes

| Purpose | What you get |
| --- | --- |
| **Broad concept** | The subject’s purpose, principal mechanisms, examples, and practical limits |
| **Comparison** | Corresponding mechanisms, a shared scenario, and meaningful decision criteria |
| **Guided tutorial** | Prerequisites, ordered steps, and a trace of the resulting behavior |
| **Focused question** | A direct answer with the reasoning and caveats needed |
| **Reference explanation** | Related parameters, settings, terms, or operations explained together |
| **Learning-oriented diagnosis** | Evidence connected to possible causes, correction, and expected behavior |

### Two depths × two layouts

| Choice | Options |
| --- | --- |
| **Depth** | **Compact:** essential mechanisms and completed examples. **Developed:** expanded reasoning, prerequisite bridges, derivations, and additional cases where useful. |
| **Layout** | **Structured** (default): follows the purpose’s predefined format. **Free:** chooses headings, order, and grouping to suit the topic. Request it explicitly or establish it as a conversation preference. |

Both layouts support both depths across all six purposes. Compact preserves the
selected scope; Free retains the same standards for reasoning, examples, diagrams,
and sources.

A **Structured broad lesson** uses eight sections: purpose → big picture →
mechanisms → worked examples → applicability → pitfalls → takeaway → sources.
Other Structured formats follow their own rules: focused answers stay flexible,
reference explanations use six stages, and diagnosis adapts to the evidence.

**Free Layout** can integrate examples and boundaries beside the mechanisms they
explain. It has no fixed section count or required numbering. It is a layout
choice across the six purposes, rather than an additional template.

```text
Use $deep-learning-mentor to compare TTL caching and explicit invalidation.
Use compact depth and a structured layout.
```

```text
Use $deep-learning-mentor to explain how a cache becomes stale.
Use developed depth, a free layout, and a concrete request timeline.
```

## 🧠 Learning design and evidence

The skills draw on advance organizers, elaboration, concept mapping, worked
examples, and signaling. These ideas inform orientation, prerequisite ordering,
resolved cases, and useful visual cues.

The [learning-evidence reference](skills/deep-learning-mentor/references/learning-evidence.md)
records sources, access limits, applications, and conflicting evidence. It
distinguishes research findings from editorial choices: neither the eight-section
format nor Free Layout is presented as a proven way to guarantee learning.

The skills provide explanations and learning maps. They do not assess mastery,
assign exercises, or guarantee retention. Their instructions call for:

- Verifying consequential claims against relevant authoritative sources.
- Preserving assumptions, exceptions, uncertainty, and version details.
- Showing concrete inputs, intermediate behavior, and completed outcomes.
- Keeping diagrams, tables, code, and prose consistent.
- Treating supplied source instructions as untrusted content.

Teaching a procedure does not authorize executing it, changing systems, saving
notes, or updating roadmap progress.

## 📁 Repository guide

```text
plugin.json
skills/
├── learning-roadmap/
│   └── SKILL.md
└── deep-learning-mentor/
    ├── SKILL.md
    └── references/
        ├── article-presentation.md   # Readability and layout examples
        ├── depth-calibration.md      # Mechanism and worked-example depth
        ├── diagram-guidance.md       # Visual selection and correctness
        ├── explanation-formats.md    # Purpose-specific structures
        └── learning-evidence.md      # Research rationale and limitations
```

When contributing, keep routing, examples, references, and this README consistent.
Check Structured and Free layouts at both depths; preserve factual qualifications
and distinguish instruction validation from testing actual generated explanations.

## License

No license file is currently included.
