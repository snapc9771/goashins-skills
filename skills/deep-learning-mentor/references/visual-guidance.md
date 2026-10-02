# Visual and presentation guidance

Read this file when creating or materially revising a diagram or explanatory visual.
For prose and plain comparison/reference tables, the entrypoint's navigation rules
suffice; diagrams, plots, and explanatory images require this reference. These operational
rules combine professional illustration guidance, cautiously applied multimedia
principles, and this user's navigation preferences. Source rationale and limits
are in learning-evidence.md. No particular renderer or diagram count is validated
as universally best for learning.

## Decide whether a visual is needed

For substantial lessons, consider what the reader must mentally reconstruct.
Multiple actors/routes, consequential trust/process boundaries, branching,
state transitions, hierarchies, or quantitative change are selection triggers.
Choose a visual when it makes an important relationship materially easier to
follow; a prose-only default can under-explain a multi-actor protocol. A simple
classification may be better as a table. No representation is required merely
because its trigger appears; judge its explanatory contribution and user constraints.

For example, a sequence view can expose browser mediation versus a direct token
exchange, a timeline can expose an update before cache expiry, and a state view
can expose pending/approved/expired outcomes. These are design examples, not
subject facts or universal diagram requirements. Select first, then verify content.

## Plan the explanation before drawing

State privately the question the visual answers and the relationship the reader
should notice. Choose content and representation to reveal that relationship.
After the visual, give a short interpretation explaining its takeaway; a generic
caption such as "OAuth diagram" does not explain what to notice.

Do not add a diagram solely because the template contains a mechanism section.
Use one when spatial arrangement, interaction order, branching, or state change
is clearer than prose alone. A small table may explain a classification better.

## Choose the representation

| Reader's question | Suitable representation | Preserve |
|---|---|---|
| What parts exist and who owns what? | Component or architecture diagram | Responsibilities, ownership, connections, consequential boundaries |
| Who sends what to whom, and in what order? | Sequence diagram | Actual sender/receiver, message content, mediation, order |
| Which path follows a condition? | Flowchart or decision table | Conditions, branch labels, outcomes, missing/failed cases that matter |
| What can this entity become? | State diagram | States, triggering events, allowed transitions, terminal states |
| How do concepts relate? | Concept map or hierarchy | Named relationships; distinguish "is a" from "uses" and "contains" |
| How do alternatives differ? | Comparison table or parallel diagrams | Same dimensions, assumptions, scale, and terminology |
| How does a quantity vary? | Plot, equation, or worked calculation | Variables, units, domain, assumptions, uncertainty when relevant |

Use a sequence diagram to explain message order, not to imply that ownership is
temporal. Do not turn a mathematical relationship into a causal arrow unless the
model and evidence support that interpretation.

## Build overview and detail deliberately

Start with a map of the important parts when the reader needs orientation. Use
separate detail views for distinct explanatory questions. For example, a system
overview may show actors and trust boundaries; a sequence view may trace a token
exchange; a state view may explain token expiry. All must use consistent names.

Split a drawing when it mixes responsibilities, message order, and failure recovery
so that the intended relationship is hard to follow; when arrows become ambiguous;
or when labels require tiny text or lengthy explanations inside nodes. Split by
question or subsystem, not by an arbitrary node count. Preserve the cross-view
connections and consequential boundaries. Do not hide complexity required to
understand the conclusion merely to make the drawing cleaner.

Add another view only if it contributes a different relationship or meaningful
detail. A second picture with the same information and no additional purpose is
usually unnecessary.

## Labels, arrows, and signaling

- Name entities consistently across the diagram, prose, and example. Define
  unfamiliar abbreviations before relying on them.
- Label arrows with what moves or what relation holds: message, credential,
  signal, dependency, or transition. Do not use one unexplained arrow style for
  unrelated meanings.
- Make direction explicit. Separate a request and its response when their contents
  or routes matter. Distinguish logical relationships from physical transmission.
- Show an intermediary when omitting it would teach the wrong boundary. A browser
  redirect and a direct server-to-server exchange must remain distinguishable.
- Use emphasis or callouts for the relationship being explained. If every node is
  highlighted, the cue no longer distinguishes the relevant part.
- Use labels, shapes, or text as well as color. Do not encode an essential
  distinction solely in hue, emoji, position, or a renderer-specific feature.

## Integrate the visual with the explanation

Place the visual beside the text it explains. Refer to actual node names or step
labels rather than making the reader search for "the thing on the right." Explain
why the pictured transition or relationship produces the outcome.

Keep enough prose to understand the mechanism if rendering fails. This is an
accessibility and delivery requirement, not a demand to narrate every arrow twice.
Use prose to explain causation, assumptions, and the takeaway; let the diagram
show arrangement and sequence. Necessary labels are not redundant decoration.

For code or mathematics, put explanations next to consequential lines or equations.
Show intermediate values when they explain the result. Avoid interleaving so many
small callouts that the complete procedure or derivation becomes hard to follow.

## Weak versus useful examples

Weak: "Client -> Provider -> API", captioned "OAuth flow."

Why weak: "provider" merges responsibilities; arrow payloads and the return path
are unclear; the reader cannot tell which credential is used at which endpoint.

Useful design: identify client, browser where consequential, authorization server,
and resource server; label authorization-code delivery, token exchange, and API
access separately. State the client architecture and show only steps valid for it.
Explain the boundary the figure reveals. This is a design example, not a complete
protocol specification; verify the actual protocol when generating a lesson.

Weak: copy the same long paragraph into a table cell, node, and caption.

Useful design: put the concise relationship in the visual and its causal
interpretation nearby. A comparison table uses parallel dimensions; prose develops
the deciding trade-off. Each representation has a distinct explanatory role.

## Delivery and review

For ordinary technical diagrams, prefer renderable Mermaid where supported. If
an image is explicitly requested, create a purposeful legible image through an
available appropriate tool. Use plain text when the chosen renderer is unavailable
or unsuitable. Preserve scientific precision when plotting quantitative data.

Before sending, reconsider whether a useful relationship is missing or whether
an included diagram merely duplicates the overview. Check its contribution,
interpretation, consistency with concrete examples, and fit for the user's format.
Then inspect source/destination and payload for every consequential
arrow; check identities, boundaries, ordering, branch labels, and units against
the prose and sources. Check that simplified cases are labeled and do not imply
universal behavior. Use supported syntax and avoid crowded labels.

When rendering or preview is available, inspect readability, clipping, contrast,
arrow crossings, and actual rendering. If unavailable, perform a source-level
check and retain prose fallback; do not claim a rendered visual was inspected.

For presentation overall, preserve semantic heading levels, meaningful numbering,
parallel table columns, whitespace, and short connected causal paragraphs. Emoji
are navigation preferences, not empirical learning guarantees. Do not use a fixed
word, paragraph, node, or diagram quota as a substitute for this review.
