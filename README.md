# Recreate from Scratch

**Master systems by rebuilding them from first principles.**

This is an original curated index of paths, tutorials, and patterns for reimplementing familiar technologies yourself — not a mirror of any other list. Star counts elsewhere measure popularity; this repo measures *whether you could build the thing*.

> Fork the flow. Alter the weights. Become a Scout.  
> Do not claim you understand a system until you have rebuilt a thin slice of it.

---

## Table of contents

- [How to use this list](#how-to-use-this-list)
- [Programming languages & runtimes](#programming-languages--runtimes)
- [Databases & storage](#databases--storage)
- [Networking & the web](#networking--the-web)
- [Version control & collaboration](#version-control--collaboration)
- [Containers, VMs & isolation](#containers-vms--isolation)
- [Distributed systems & consensus](#distributed-systems--consensus)
- [Cryptography & trust](#cryptography--trust)
- [Agents, swarms & authorization](#agents-swarms--authorization)
- [Editors, shells & tools](#editors-shells--tools)
- [Graphics & games](#graphics--games)
- [Related repos](#related-repos)
- [Contributing](#contributing)
- [Licence](#licence)

---

## How to use this list

1. Pick one system you use every day but have never implemented.
2. Rebuild the **smallest useful core** (not a product clone).
3. Write down what surprised you — that note is the real artifact.
4. Optional: open an issue titled `I rebuilt X` with a link and one paragraph of lessons.

**Rule of thumb:** if the guide only teaches you to *call* an API, it does not belong here. If it teaches you to *become* the API, it does.

---

## Programming languages & runtimes

- **Tiny interpreters** — Build a tree-walk interpreter for a minimal language (arith + functions + env).
- **Bytecode VM** — Compile a subset of that language to bytecode; write a stack machine.
- **Regex engine** — Thompson NFA or backtracking matcher from a pattern string.
- **Garbage collector** — Mark-and-sweep or copying GC over a toy heap.
- **Type checker** — Hindley–Milner or a simple bidirectional checker for a lambda calculus.

*Search terms to find quality guides:* `crafting interpreters`, `write a language in X`, `bytecode VM tutorial`, `build a regex engine`.

---

## Databases & storage

- **KV store** — Append-only log + in-memory index; then add compaction.
- **B-tree or LSM** — Implement one page format and one read/write path.
- **SQL subset** — Parse `SELECT` / `INSERT`; execute against in-memory tables.
- **CRDT** — G-Counter or LWW-Register; show concurrent merge.
- **SQLite-shaped learning** — Single-file DB mental model: pages, btree, WAL (read official file format docs; implement a reader first).

---

## Networking & the web

- **TCP-ish over UDP** — Sequence numbers, acks, resend (educational only).
- **HTTP/1.1 server** — Parse requests; serve files; one connection at a time, then pool.
- **DNS resolver** — Query A records recursively (respect rate limits and law).
- **Reverse proxy** — Accept HTTP; forward; add a request id header.
- **WebSocket framing** — Masking, opcodes, continuation — without a framework.

---

## Version control & collaboration

- **Snapshot store** — Content-addressed blobs + tree objects + commit parents (Git’s idea, your code).
- **Diff & merge** — Line diff; three-way merge with conflict markers.
- **Simple patch format** — Apply and create unified diffs.

---

## Containers, VMs & isolation

- **Jail from parts** — Namespaces / chroot / cgroups *concepts* on Linux (where permitted); or a userspace simulator.
- **Image tarball** — Rootfs + JSON config; “run” = unpack + isolated process (platform-dependent).
- **Init process** — Reap zombies; forward signals; PID 1 responsibilities.

---

## Distributed systems & consensus

- **Raft in one file** — Leader election + log replication for 3 nodes in-process.
- **Gossip membership** — Failure detection with SWIM-style messages (simulated network).
- **Exactly-once illusion** — Inbox table + idempotency keys.
- **Vector clocks** — Causality tracking for concurrent writes.

*See also:* [hivemind](https://github.com/miigwech-potato/hivemind) — experimental consensus *notation* and authorization boundaries (not a Raft implementation).

---

## Cryptography & trust

- **Merkle tree** — Build, prove inclusion, verify.
- **Hash chain / toy ledger** — Append-only; detect tampering.
- **Password hashing** — Use a real KDF library correctly; understand salt and parameters (do not invent crypto).
- **Capability tokens** — Bearer token with scope + expiry + signature *using standard libraries*.

**Warning:** Never ship homemade encryption. Rebuild to *understand*; deploy peer-reviewed primitives.

---

## Agents, swarms & authorization

- **Tool-using loop** — Model proposes → validate schema → execute allowlisted tool → observe → repeat.
- **Supervisor + workers** — One router agent; N specialists; shared scratchpad.
- **Human gate** — Interrupt before side effects; resume only with recorded approval.
- **Proposal hash** — Canonicalize action payload; hash; refuse execution if hash mismatches approval.

Design notes living in this org:

- [hivemind](https://github.com/miigwech-potato/hivemind) — Scout / Worker / Queen / Consensus Gate; capability ≠ authority.
- Boundaries: `flow/BOUNDARIES.flow` — near-miss patterns for systems that help humans.

---

## Editors, shells & tools

- **Line editor** — Buffer, cursor, insert/delete, write file.
- **Mini shell** — Parse commands; pipes; redirection; `cd` / env.
- **grep subset** — Literal and simple `.*` matching over files.
- **Make-like DAG** — Targets, dependencies, mtime checks.

---

## Graphics & games

- **Software rasterizer** — Triangles, z-buffer, one light.
- **Tile engine** — Camera, sprites, collision in 2D.
- **Parser + VM for a tiny adventure** — Rooms, items, verb-noun commands.

---

## Related repos

| Repo | Why |
|------|-----|
| [hivemind](https://github.com/miigwech-potato/hivemind) | Swarm consensus notation, authorization boundaries |
| *(your forks of learning projects)* | Link what *you* rebuilt |

---

## Contributing

PRs welcome when they:

1. Point to **from-scratch** learning paths (not product wrappers only).
2. Prefer primary sources and well-known educational projects.
3. Add one sentence: what “done” means for a minimal rebuild.
4. Stay lawful (no guides aimed at unauthorized access or harm).

Issue template idea: `I rebuilt X` — link, language, one lesson.

---

## Licence

CC0 1.0 (dedication to the public domain) for this curated index text, unless a subdirectory says otherwise.

Individual linked projects keep their own licences — always read them.

---

## Lineage (honest)

The *genre* — curated “build X from scratch” lists — is popular on GitHub for good reason.  
**This repository is not affiliated with codecrafters-io/build-your-own-x or any other list.**  
Content here is original curation and framing for [miigwech-potato](https://github.com/miigwech-potato).

米 only on a recorded AUTHORIZED.  
Everything else: 𝄐
