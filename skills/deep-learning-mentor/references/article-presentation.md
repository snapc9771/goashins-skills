# Article presentation and depth examples

Read this for article formatting and compact/developed calibration. SKILL.md owns
routing, the authoritative Navigation and representations standard, shared quality
requirements, and the eight-section Structured broad backbone;
diagram-guidance.md owns construction and delivery checks for explanatory visuals.
These are editorial examples, not evidence that a layout guarantees retention.

## Choose a useful representation

| Information need | Markdown tools and selection rule |
|---|---|
| Navigate a substantial article | Descriptive headings, anchors, and related-topic links under the main navigation standard; linked contents only on explicit request. The outline below illustrates optional depth. |
| Signal meaning | Apply the main emphasis hierarchy; *italics* can lightly emphasize or introduce terms. Use strikethrough only for an explained replacement/correction. |
| Group or order | Bullets for parallel points; numbered steps for sequence; nested lists only for real hierarchy. Task lists belong to requested procedures/tracking, not learner assessment. |
| Compare or expose a contract | Parallel tables with consistent dimensions; include relevant conditions, operations, and consequences. Split dense cells or independent decisions. |
| Show actual behavior | Language-labelled fenced code/configuration, separate output blocks, or state traces. Explain consequential lines nearby and label hypothetical/untested material. |
| Highlight a boundary | Use the main standard’s callout labels and severity; blockquotes, supported alerts, or ordinary labelled text provide the presentation. |
| Explain relationships | Mermaid, images with useful alt text/captions, or supported mathematical notation. Follow diagram-guidance.md for visuals; define math symbols/units and provide readable equations when rendering is unavailable. |
| Supply evidence | Descriptive inline links and the source section. Reference-style link definitions can keep source Markdown manageable without changing citation meaning. |
| Control rhythm | Whitespace and focused paragraphs; separators only between meaningful units. Deliberate line breaks suit addresses/verse or comparable layouts, not every sentence. Escape Markdown characters when displaying literal syntax. Restrained heading emoji follow SKILL.md. |
| Offer optional detail | Supported footnotes for secondary notes; `<details><summary>Additional failure example</summary>…</details>` for supplementary examples, long code, or derivations, subject to the main visible-content boundary. |
| Use viewer extensions | HTML, color, superscript/subscript, and other tags only where supported and useful. Prefer standard Markdown; retain text meaning without styling. Do not insert arbitrary tags to decorate an article. |

Use SKILL.md's viewer-support and visible-content rules throughout this toolkit.
Features serve the information; using more of them does not establish quality.

## Free Layout presentation

Use the shared representation toolkit above and SKILL.md's content standards.
Choose descriptive headings and a coherent progression suited to the subject;
title, numbering, and the Structured subdivision label scheme are optional.
When headings are used, nest them semantically. Keep selective emphasis, readable
tables, nearby explanations, accessible fallbacks, and essential boundaries visible.
Contents remain opt-in. Use ordered steps when procedure order matters.

Integrate examples and qualifications where they explain behavior; do not force
separate overview, example, pitfalls, or takeaway sections. Substantial articles
retain inline citations and a plain source list with flexible placement and heading.
The numbered outline and paired articles below illustrate Structured Layout only.
Their depth standards remain useful, but their arrangement is not a Free template.

For example, a free caching article could open with a stale price, trace a hit and
miss with concrete values, explain expiry at the point it changes the outcome,
then compare invalidation under a different freshness requirement. The trace
carries both mechanism and example; trade-offs and boundaries appear beside the
relevant behavior. This is one possible progression, not a required outline or
minimum length. Other subjects should use their own explanatory progression.

## Practical navigation outline (Structured Layout)

This hypothetical outline illustrates all five available content levels under an
H1 title, only to show their syntax. It does not recommend five-level depth: use
fewer levels whenever the content needs fewer independently revisitable topics.
Earlier/later major sections and explanatory prose are omitted from this outline;
a Structured broad article still contains all eight major sections.

```markdown
# Collections and lookup

## 3. How it works
### 3.1 Elements and identity
[Explanation.]

### 3.2 Collections
#### i. Lists
[Explanation.]
#### ii. Sets
[Explanation.]
#### iii. Maps
##### a. Key lookup
###### Collision handling
[Detail, if independently useful at this depth.]

Step 1. Locate the candidate entry.

Step 2. Check the key and select the result.

##### b. Updating a mapping
[Explanation.]

## 4. Worked examples
### 4.1 Resolving a lookup
[Resolved case referring to 3.2(iii), Maps, or
3.2(iii)(a), Key lookup, when needed.]
```

Roman numerals restart within each decimal subsection; letters restart within
each Roman parent. Short local labels can remain unnumbered headings, bullets,
or callouts without inventing intervening branches. Keep heading levels semantic.

The default outline has no standalone Contents section. Include one only on
explicit request, with links matching actual headings and useful nesting. Anchors
and related-topic links remain useful independently: for example,
`[Maps](#iii-maps)` uses a common GitHub-style automatic anchor for the example
heading. Other viewers may differ; this is not a claim of checked links. When
heading text repeats, use the target viewer's duplicate-anchor convention or a
supported explicit anchor. A table might be labelled “Lookup conditions and
outcomes”; add “Table 1” only if later references benefit.
The paired miniature articles below need no subdivisions merely to demonstrate
the hierarchy, and no contents list unless explicitly requested.

## Paired miniature broad articles (Structured Layout)

The same deliberately fictional cache contract appears below. Both examples are
complete for this narrow contract, not templates for reducing a broad real-world
subject to these lengths. Their source section honestly identifies supplied
assumptions. Real subject claims require the applicable authoritative sources.

### Compact treatment

#### 1. 🎯 Expiring a cached price
A cache reuses a fetched price until its deadline, reducing source reads while
permitting temporary staleness.

#### 2. 🧭 Components
The source owns the current price; the cache stores a value and deadline. Assume
sequential operations, immediate successful fetches, and no invalidation signal.

#### 3. ⚙️ Read rule
| Condition at read time t | Operation and result |
|---|---|
| Entry exists and t < deadline | Return cached value; source changes remain unseen. |
| Entry absent or t >= deadline | Fetch source, store value with deadline t + 30, return it. |

#### 4. 🔎 Resolved case
At t=0, a miss fetches 10 and sets deadline 30. The source changes to 12 at t=5.
A read at t=10 returns **10** because the entry remains valid. At t=30, the deadline
check fails: the read fetches **12** and stores deadline 60.

#### 5. ⚖️ Applicability
This rule suits reads that tolerate temporary stale prices. It avoids an update
signal but cannot guarantee immediate visibility of source changes.

#### 6. ⚠️ Boundary
> **Boundary:** Expiry does not refresh proactively: the next read performs the fetch.

Fetch failures and concurrent reads are outside this supplied contract.

#### 7. 📌 Takeaway
The deadline controls reuse, not whether the cached value matches the source.

#### 8. 📚 Sources
Supplied fictional contract above; this is not documentation for a cache product.

### Developed treatment

#### 1. 🎯 Expiring a cached price
Reading the source for every request can be unnecessary when temporary staleness
is acceptable. This cache trades fewer source reads for a second copy of the price
that may lag behind the authoritative value.

#### 2. 🧭 Components and assumptions
The source owns the current price. Each cache entry contains a fetched value and
an absolute deadline. Assume sequential operations, immediate successful fetches,
a 30-second lifetime, and no invalidation signal; time values are seconds.

#### 3. ⚙️ Why the deadline changes behavior
An entry is reusable only while t < deadline. Reuse returns its stored value
without consulting the source, which explains both the saved read and the stale
result after a source update. At or beyond the deadline, a read fetches the source
and stores a new entry with deadline t + 30. The strict inequality makes t=30
expired for an entry created at t=0; equality is not an extra valid instant.

#### 4. 🔎 One timeline and a changed condition
| Time | Event/check | Observable result and stored state |
|---|---|---|
| 0 | Read; no entry | Fetch 10; return 10; store (10, deadline 30). |
| 5 | Source changes to 12 | Cache still holds (10, 30); no signal updates it. |
| 10 | Read; 10 < 30 | Return 10 without a source read. |
| 30 | Read; 30 < 30 is false | Fetch/return 12; store (12, 60). |

In an alternative timeline with no read at t=30 and the next read at t=45, that
read fetches 12 and sets deadline 75. Nothing in this rule schedules a refresh at
30; the read triggers it. This alternative changes the request time, not the rule.

#### 5. ⚖️ When this trade-off fits
Choose this rule when temporary staleness is acceptable and avoiding source reads
matters. A shorter lifetime offers less reuse and more frequent opportunities to
observe updates. If every read must see the latest committed price, this contract
is insufficient: valid entries deliberately bypass the source.

#### 6. ⚠️ What the contract does not establish
A deadline limits reuse; it does not certify freshness. The rule also supplies no
fetch-failure response or concurrency guarantee. Those require additional defined
behavior before applying the model to a real system.

#### 7. 📌 Takeaway
Two facts govern the result: the stored value determines what a hit returns, and
the deadline determines whether a read may reuse it. A source change alone changes
neither fact in this cache.

#### 8. 📚 Sources
Supplied fictional contract above. Product-specific guarantees would require the
relevant implementation's documentation.
