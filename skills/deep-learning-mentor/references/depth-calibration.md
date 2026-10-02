# Depth calibration: explain behavior, not just labels

Read "Domain-sensitive depth" and the matching example for broad lessons and
substantial comparisons unless already read in this conversation; use them also
to repair shallow treatment. These calibrate explanatory depth, not subjects or
fictional contracts to repeat. SKILL.md owns structure and final review.

## Domain-sensitive depth

| Subject | Consequential detail to expose | Concrete support when useful |
|---|---|---|
| Protocol/API | Initiator, sender/receiver, relevant fields, validation/stored associations, authority/state after success, meaningful rejection | Request/response pair and sequence |
| Distributed system | Ownership, timing, coordination, persistence, failure and recovery | State/timeline trace or component/sequence view |
| Algorithm/code | Inputs, consequential branches, intermediate state, output, assumptions | Compact code/pseudocode plus trace |
| Mathematics | Variables/units, derivation and reasons, instantiated values, interpretation | Worked calculation, equation, or plot |
| Science | Phenomenon, model/mechanism, assumptions, predictions, evidential limits | Calculation, observation, thought experiment, or figure |
| Conceptual comparison | Shared problem, corresponding mechanisms, consequence, changing condition | Parallel case and comparison table |

Choose relevant dimensions; do not insert every cell as a checklist or force
chronological steps onto static relationships. Concrete syntax is useful when it
reveals the contract, not when it adds unrelated implementation work. A reader
should be able to follow a representative case without supplying missing reasoning.

## Protocol example: abstract exchange versus resolved trace

Weak: "The app reserves a book, receives a reservation ID, and confirms it."
Naming the app LibraryHelper does not add internal behavior or resolve a case.

Developed example using a deliberately fictional library API contract:
LibraryHelper requests book B7 for member M2. Assume the server has one copy,
creates pending reservations valid before their absolute expiry, and confirms
only a matching member's unexpired pending reservation. Confirmation consumes
the reservation; these are supplied example assumptions, not a real API standard.

```http
POST /reservations
Content-Type: application/json

{"book_id":"B7","member_id":"M2"}

HTTP/1.1 201 Created
Content-Type: application/json

{"reservation_id":"R9","expires_at":120,"status":"pending"}
```

At example time 100 seconds, the server stores R9 -> B7, M2, expiry 120, pending,
and holds that copy. LibraryHelper then sends:

```http
POST /reservations/R9/confirm
Content-Type: application/json

{"member_id":"M2"}

HTTP/1.1 200 OK
Content-Type: application/json

{"loan_id":"L4","book_id":"B7","member_id":"M2"}
```

At time 110, the member matches, 110 < 120, and R9 is pending. The server creates
loan L4 and consumes R9. The held-copy association means confirmation cannot
silently select a different book. A repeated confirmation is rejected because
R9 is no longer pending; a first confirmation at 120 is rejected by strict expiry.
These schematic exchanges omit transport/authentication details and are not runnable
implementation examples. A real lesson must include those details when consequential.

Why developed: the example instantiates inputs, stored associations, checks, state
change, response, and a changed-condition result. It explains the contract, not
merely operation names. Keep example architecture and values consistent; verify
exact derived values rather than decorating a sample with plausible-looking data.

## Caching example: mechanism and conditional comparison

For a concept such as caching, "caching makes reads faster" is too shallow.
A concept-first treatment traces a cache miss to the authoritative store, shows
how the result is retained, then traces a hit. If a price changes at the source,
the old cached value explains staleness. A compact snippet can expose the branch:

```text
# Illustrative pseudocode; expiry and concurrency are not implemented here.
if cache has key:
    return cached value
value = read authoritative store
cache[key] = value
return value
```

Explain the trade-off: fewer source reads in exchange for additional state that
can become stale. If comparing expiry and explicit invalidation, put freshness,
coordination, and failure behavior side by side in a table. A full cache server
implementation would distract from this conceptual request. This calibrates the
depth of treatment, not a scenario to reuse in unrelated lessons.

For a comparison, "expiry is simple; invalidation is fresh" is insufficient.
Develop the deciding relationship: expiry permits reuse until a deadline, so a
source update can leave the cached value stale until expiry. Explicit invalidation
removes or marks that value after an update, so freshness depends on delivering
and correctly ordering that signal. A lost signal can leave stale data unless a
fallback exists. If updates are rare and temporary staleness is acceptable, expiry
may suffice; if updates must become visible promptly, invalidation with an
appropriate recovery strategy may fit. Neither guarantees freshness under all
races. A useful table compares freshness conditions and coordination costs, not
just "simple" versus "fast". Apply this depth, not this content, to other topics.

## Algorithm example: show a branch and outcome

Weak: "Binary search repeatedly halves the search space."
Developed: for [2, 5, 8, 12, 17] and target 12, initial middle value 8 is too small.
Sorted order excludes indices 0 through 2; the remaining interval is indices 3-4.
Using floor((low + high)/2), the next middle is index 3, whose value 12 matches.
The result is index 3. Explain why sorted order permits exclusion; unsorted input
invalidates that reasoning. A compact implementation may support this trace, but
is not required when tracing already exposes the consequential behavior.

## Mathematics/science example: derivation and interpretation

Weak: "The quantity approaches equilibrium exponentially."
Developed: for the hypothetical model dx/dt = k(L-x), x(0)=x0 and constant k>0,
the solution is x(t)=L+(x0-L)e^(-kt). Explain that the rate is proportional to the
remaining gap and falls as the gap closes. If x is in grams and t in minutes,
k has units 1/min. For L=10 g, x0=2 g, k=0.5/min and t=2 min, x=10-8/e,
approximately 7.057 g. The sign and range agree with movement from 2 toward 10.
Whether this equation describes a physical process requires evidence and its
assumptions; solving the equation does not prove the model fits observations.

## Section-function counterexamples

- A flow-selection scenario explains a choice but does not alone trace operations.
- An overview table locates branches but does not develop their mechanisms.
- A list of token categories clarifies terms but does not explain a supported
  failure and correction. Do not invent a failure merely to create that format.
- A syntax block without field/operation reasoning is not a resolved example.
- A visually attractive diagram with unclear payloads can teach the wrong model.

Use these distinctions in the final review to repair function substitutions;
they are not a requirement to make every short answer a full lesson.

## Selecting and connecting worked examples

Use the roles below as choices within the existing worked-example section, not
new required lesson stages. SKILL.md's completion contract applies to each case
or consequential stage. Example count follows the topic and requested scope.

| Role | Purpose | When useful |
|---|---|---|
| Anchor | Fully resolve a representative mechanism | Establish concrete inputs, internal checks/state, and outcome |
| Important-type case | Demonstrate a materially different principal mechanism | Actor/authority, interaction, assumptions, or selection consequence changes |
| Continuation | Show a lifecycle or interaction with another concept | The next operation depends on state established in the anchor |
| Contrast/failure case | Expose an outcome-changing condition | A supported condition changes a check, result, or boundary |

A broad topic may require multiple examples because its important types cannot
be represented by one mechanism. Develop the important distinctions; use smaller
illustrations for peripheral types. Do not expand every minor subtype equally or
restart prerequisites and the general mechanism in each case. A focused question
may need only one small resolved case.

### Three ways to connect cases

- Lifecycle: retain the same actors/state and continue through later operations.
  Explain what the earlier result enables and how the next operation changes it.
- Shared setting: keep a common problem or organization while distinguishing
  separate components, actors, assumptions, and architectures. These are parallel
  cases unless the subject actually connects them in sequence.
- Changed condition: complete a success case, vary a consequential input or
  assumption, then trace the changed behavior. Specify which facts remain fixed.

Illustrative calibration, not a real cache contract: assume a source price starts
at 10, a successful fetch at time 0 stores that value until strict expiry at time
30, and no concurrent operations occur. The source changes to 12 at time 5.
The anchor demonstrates the miss, stored state, and a hit returning 10 at time 10.
A continuation at time 30 demonstrates expiry, a source fetch returning 12, and
a new deadline 60. These are stages of one expiry-based lifecycle.

An important-type comparison can instead assume explicit invalidation with the
same source update and a TTL fallback. If the update commits at time 5 and deletion
arrives at time 6, a read at time 10 misses and obtains 12. If the signal is lost,
that read still obtains cached 10 until expiry. Mark these as alternative timelines,
not additional steps after the first timeline. Explain that freshness now depends
on signal delivery/ordering; concurrency guarantees are outside these assumptions.

For protocol lessons, request/response pairs and associated stored checks can
instantiate these roles; algorithms may use code/state traces, and science may
use calculations or observations. Use concrete syntax where it exposes consequential
behavior, with adjacent reasoning, rather than forcing code into every case.

### Concrete exchanges and supporting code

For a protocol/API anchor, trace the consequential operations through their actual
representations: relevant request parameters, headers/body, response status and
headers/body, checks, then the resulting state or action. Include intermediate
exchanges when they explain how the result becomes possible. A redirect may be the
response; show its relevant location/parameters rather than inventing JSON. Label
illustrative values and omissions, and preserve the protocol's actual encoding.
Credentials may use placeholders; other representative values should make the
case traceable. Carry returned values into subsequent operations consistently.

For example, "send an authorization code; receive an access token; call the API"
leaves the exchange abstract. A developed case shows the relevant encoded exchange
request, the token response body, the authenticated resource request, and the
resource response; it explains the consequential validation and what the returned
data enables. This is a calibration example, not a demand to teach every endpoint
or include every optional field. Use authoritative protocol sources for specifics.

Selected important-type cases need the same completion contract with emphasis on
their distinctive operations. Reuse shared explanations and demonstrate the
different actor, request, check, state, or outcome. A use-case label or recommendation
alone is insufficient. A continuation consumes the anchor's established result;
an alternative type uses explicitly changed assumptions rather than silently
reusing incompatible state.

Use code/pseudocode when it reveals consequential local behavior, such as storing
and checking correlation state, computing a value, or handling a returned result.
Configuration or a state trace may be clearer. Explain relevant lines and outcomes;
omit framework boilerplate and do not imply untested fragments are runnable.
Choose the representation for understanding, not to fill a code quota. Deliver
these resolved representative cases in the first full lesson; later responses may
expand implementation detail without supplying a missing foundational example.

### Example-set review

Privately connect each case to the principal mechanism or uncertainty it resolves.
Check that each adds something, inputs/state/results remain consistent, changed
assumptions are explicit, and outcomes are completed. Check important types that
the anchor cannot represent. A short synthesis may connect the demonstrated
differences without repeating the full mechanism or adding a new lesson outline.
For each consequential stage, verify that the reader can identify the input,
operation/check, observable response/output, and resulting state. If an output is
only announced, or a type is only named, supply the missing demonstration. Review
protocol/API bodies and supporting code where applicable, with adjacent reasoning;
do not add irrelevant fields or syntax to otherwise complete examples.
