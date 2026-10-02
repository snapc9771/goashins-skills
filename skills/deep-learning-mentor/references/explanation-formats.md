# Structures by reader goal

This file defines the non-broad structures. SKILL.md owns routing, the full broad
lesson, shared depth, source fidelity, and navigation. If changing a template,
update its routing row too. A heading count does not establish explanatory quality;
the functions below must be fulfilled. These structures are user-approved design
choices, not experimentally validated teaching categories.

## Broad concept

Use the eight numbered sections in SKILL.md, in order, without merging or silently
omitting them. Keep topic-specific content and subsections flexible. Bare topics
and broad "explain X" requests are full lessons unless explicit brevity or clear
focused context overrides this. The major functions are definition/purpose,
overview, mechanism, worked examples, applicability, boundaries, takeaway, sources.

## Comparison

### Substantial comparison: required major stages

1. 🎯 What we are comparing—and why
2. 🧭 Comparison at a glance
3. ⚙️ Why their behavior differs
4. 🔎 The same scenario through each
5. ⚖️ What the differences mean in practice
6. ⚠️ Boundaries and misleading comparisons
7. 📌 The takeaway
8. 📚 Sources

Preserve these stages for substantial comparison, with topic-specific titles allowed.
Begin by defining the compared items and their relationship: substitutes,
complementary layers, categories at different levels, or historical versions.
Do not pretend two things solve the same problem when their purposes differ.

Choose consistent dimensions based on the actual distinction or decision:
authority, mechanism, ownership, guarantees, constraints, costs, or assumptions.
An explicit side-by-side table is required. Include similarities where their
absence would create a misleading contrast. Avoid rows that compare one option's
mechanism with another's benefit, or unsupported labels such as "fast/slow."

Explain each principal alternative's causal mechanism with enough depth to support
the contrast. Comparable depth does not mean equal words. Apply alternatives to a
shared requirement or scenario, preserving relevant assumptions. For complementary
layers, show each layer's contribution to that scenario rather than pretending
each independently solves it.

Interpret consequences after the mechanism and example. For choice questions,
state which conditions favor which option and why; include costs and boundaries.
For historical or conceptual questions, explain significance without manufacturing
a recommendation. A comparison table is orientation, not a replacement for reasoning.

Example: "OAuth vs OIDC" first establishes their relationship, then compares the
contracts, explains their mechanisms, and traces API authorization and identity
establishment in a shared application scenario.

### Small or embedded comparison

Use a direct distinction -> compact table -> consequential example or caveat when
needed -> proportional citations. Major numbered stages are unnecessary. A
defining contrast belongs near the definition; a deeper choice belongs after the
mechanisms. "Briefly compare" invokes this form. A short prompt "A vs B" alone does
not require a short answer. Do not expand a small embedded contrast into a second
full lesson.

## Guided tutorial

### Required major stages

1. 🎯 Goal and expected result
2. 🧰 Prerequisites and starting conditions
3. 🧭 The approach and component relationships
4. 🛠️ Step-by-step walkthrough
5. 🔎 Trace the completed behavior
6. ⚠️ Failure points and important boundaries
7. 📌 What was built—and how it works
8. 📚 Sources

Use these stages for a substantial guided tutorial; an explicitly tiny walkthrough
can combine its functional content. State the intended final behavior and relevant
environment, versions, permissions, inputs, and dependencies. Do not add unnecessary
installation work when the requested context already supplies it.

Explain how the components fit together before detailed steps. In the walkthrough,
connect each consequential action to the artifact/state change, expected result,
and mechanism. Use ordered steps and maintain a coherent dependency order. Do not
mechanically repeat four labels for trivial actions. Include necessary artifacts
and enough surrounding context to place fragments correctly.

Put cleanup, secret handling, permission boundaries, data loss, and consequential
failure conditions beside the affected step. Explain actual requirements without
inventing warnings for unrelated hypothetical risks. Label runnable artifacts,
pseudocode, omitted setup, and untested behavior accurately.

Trace representative input through the finished artifact and show the observable
result. Distinguish "expected" from "observed in an executed check." Explain likely
failure points supported by documentation or the mechanism and how to distinguish
them. Do not introduce an exhaustive catalog of other implementations.

Example: a caching walkthrough explains the input/store contract, miss and hit
paths, expiry behavior, and observable outcomes, with limitations of the simplified
implementation. It does not become a full cache-service deployment by default.

The assistant resolves the walkthrough. No quizzes, independent assignments, or
competence checks. Teaching a procedure is not permission to execute it.

## Focused question

Lead with the direct answer. Then provide the necessary mechanism or reasoning,
an example/contrast when it resolves uncertainty, a consequential boundary, and
proportional citations. Optional headings are "⚙️ Why/how", "🔎 Example", and
"⚠️ Important boundary". A title, emoji, and a separate source list are unnecessary
for a short answer. A difficult narrow question may require substantial reasoning.

Use existing context. Do not restart the topic, list every variant, or append a
gated invitation instead of completing the answer. Do not shorten reasoning into
a slogan merely because the question is short.

Example: "Can authorization code work without OIDC?" needs an immediate answer,
the distinction between API authorization and an identity contract, a concrete
scenario, and the boundary on what can be inferred about the signed-in identity.
It does not need an entire OAuth flow survey.

## Reference within a lesson

### Substantial reference stages

1. 🎯 What these entries control
2. 🧭 Entries at a glance
3. ⚙️ Important relationships and constraints
4. 🔎 Annotated example
5. ⚠️ Boundaries and version-specific details
6. 📚 Sources

For a small set of entries, a clear purpose sentence, consistent table, example,
and relevant caveats can combine these functions. Explain the contract and
interactions; pure factual lookup alone does not require this skill.

Choose the schema for the material:
- Request parameters: purpose, required condition, accepted form/example, constraint.
- Configuration: meaning, documented accepted values/default, interactions.
- Terms: meaning, role, distinction.
- API operations: inputs, effect, result, consequential failure condition.

Keep comparable entries parallel; include only applicable fields. Distinguish
optional, conditionally required, absent, unknown, and undocumented. Never infer a
default from an example or fill a missing guarantee to complete a table.

The annotated example must show how entries work together. Explain interactions
such as mutually exclusive options, scope dependencies, or version-specific rules
near the relevant entries. Cite the applicable version/contract. Large cells
should become nearby prose, not dense miniature articles.

## Learning-oriented diagnosis

### Major stages, conditional on evidence

1. 🎯 The symptom and established facts
2. 🧭 Possible causes and distinguishing evidence
3. ⚙️ The mechanism behind the supported cause
4. 🛠️ Correction and why it changes the behavior
5. 🔎 Expected behavior after correction
6. ⚠️ Remaining uncertainty and boundaries
7. 📌 The causal takeaway
8. 📚 Sources

Preserve evidence -> mechanism -> correction -> expected behavior. If the cause
is established, omit the hypothesis survey and renumber the remaining headings.
If the cause is uncertain, keep section 3's title and explanation explicitly
conditional; present evidence-dependent correction branches, not a false diagnosis.
For short questions, combine stages while preserving this reasoning.

Separate observed facts, assumptions, and possible causes. For each plausible
cause worth including, explain a discriminating observation: what result would
support it, what would weaken it, and why. Do not generate a random checklist of
fixes. An error label rarely establishes every underlying cause.

Explain how the supported mechanism generates the symptom. Connect correction to
the state or behavior it changes. State the expected observable result and relevant
residual failure/retry conditions; do not claim a fix was executed or successful
without evidence. When essential information is missing, ask narrowly and continue
only the independent explanation.

Example: stale displayed data after an update may involve mutation completion,
the relevant cache, or the subscription/refresh path. Inspect evidence before
claiming which layer failed. If logs already establish the cause, explain it
directly rather than manufacture uncertainty.

This form teaches a failure mechanism. General troubleshooting without learning
intent remains outside the mentor's core scope.

## Representation and example choices by goal

| Goal | Helpful navigation/representation | Example must accomplish |
|---|---|---|
| Broad concept | Branch map; diagram for difficult relationships; meaningful subsections | Resolve concrete behavior/calculation rather than repeat the mechanism |
| Comparison | Consistent matrix; corresponding scenario; selective key distinction | Show why the shared case differs, or how complementary layers contribute |
| Tutorial | Ordered steps; scoped code/config/request pairs; behavior trace | Connect actions to artifact/state changes and expected outcomes |
| Focused question | Direct answer; compact contrast or callout when useful | Resolve the specific uncertainty without rebuilding the whole topic |
| Reference | Parallel entry table; interactions near entries | Show how relevant entries work together, including conditional requirements |
| Diagnosis | Facts/evidence table when useful; state/timing trace | Separate incident facts from hypothetical cases and connect correction to effect |

Use SKILL.md's table, emphasis, blockquote, emoji, and example-completion rules.
These are choices, not additional mandatory headings or counts. For substantial
protocol explanations, select request/response evidence when concrete fields/checks
are central; for algorithms or science, traces or calculations may serve better.
Keep original callouts distinct from attributed quotations. Do not reproduce
long prose in tables or format every sentence as a warning.

## Shared application rules

Apply SKILL.md's scope, depth, navigation, source-fidelity, and no-assessment rules.
Use topic-specific headings without erasing required stages. The broad lesson is
fixed; comparison/tutorial backbones are stable; focused presentation is flexible;
reference and diagnosis adapt to entry count and evidence as specified above.
Do not apply a blanket "merge any sections" permission across all modes.

Explicit user constraints override templates. For mixed requests use the dominant
goal and nest supporting functions. Do not add an irrelevant stage or fake content
to meet a count. A meaningful applicability statement can fulfill a stage without
inventing alternatives; narrow requests can use the designated compact forms.

Keep warnings at the affected step and synthesis concise. Tables organize parallel
facts; connected prose supplies reasons. Source lists support, rather than replace,
explanations. Before sending, verify both the selected structure and whether the
request's actual uncertainty has been resolved.
