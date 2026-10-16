# Earl John B. Plaza

3rd year BSIT at Davao Del Norte State University.
Backend systems, distributed data structures, retrieval pipelines.

[Portfolio](https://earljohn-spec.github.io) · [Email](mailto:earljohnbplaza@gmail.com) · [GitHub](https://github.com/earljohn-spec)

---

## Projects

### rfc-rag-pipeline — Hybrid Retrieval Engine for IETF RFCs

Retrieval-augmented generation pipeline for technical documents. Dense embeddings
and BM25 sparse retrieval fused via Reciprocal Rank Fusion (k=60). Structural
chunking follows RFC section boundaries instead of splitting on token count.

- 64 tests, mypy strict, ruff linting
- Python library — import and call, no HTTP server or daemon
- Retrieval bias documented via ADR; ragas evaluation isolated as optional
  dependency to prevent LangChain from entering the dependency tree

[Repository](https://github.com/earljohn-spec/rfc-rag-pipeline)

### convergence-crdt — Op-Based CRDT for Collaborative Text

RGA (Replicated Growable Array) with causal ordering, out-of-order delivery,
and fuzz-tested convergence across N sites. Lamport clocks for total ordering
with deterministic tiebreak on site ID.

- 77 tests including 3-site 50-op fuzz convergence across 5 delivery orderings
- Optional WebSocket transport; core engine has zero runtime dependencies
- SQLite checkpoint persistence; opt-in tombstone garbage collection

[Repository](https://github.com/earljohn-spec/convergence-crdt)

---

## Stack

**Backend:** Python, Java, PHP, Laravel
**Data:** MySQL, SQLite, ChromaDB
**Retrieval:** sentence-transformers, BM25, RRF
**Distributed systems:** CRDTs, version vectors, Lamport clocks, causal delivery
**Frontend:** HTML, CSS, Tailwind CSS, Alpine.js
**Tooling:** Git, pytest, mypy, ruff, Vite

---

## Practices

- Tests before merge. Both projects above ship with full pytest suites
  and strict type checking.
- Linting and formatting enforced in CI (ruff).
- Dependencies pinned in lockfiles.
- Parameterized SQL everywhere. No pickle deserialization, no shell=True,
  no live network calls in test suites.
