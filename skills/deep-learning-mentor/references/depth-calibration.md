# Depth calibration: explain behavior, not just labels

Read for broad lessons and substantial comparisons unless already read in this conversation; use it also to repair shallow mechanisms. This example calibrates explanatory depth, not subject matter to repeat. SKILL.md owns the structural rules.

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

