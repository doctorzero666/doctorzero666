# Zhichao Jiang

Applied AI engineer in Sydney. I build LLM systems that fail safely: schema validation before anything is persisted, audit trails on every run, and the model kept off the safety-critical path. Master of Computer Science, University of Sydney (2025). Before that I was an RF engineer isolating faults on real hardware, which is where the habit of proving things by retest comes from.

Full Australian work rights (subclass 485, valid to 2028). Looking for applied AI, agent workflow, or Python backend roles.

## Selected work

### HireNet · [live demo](https://frontend-nine-gamma-37.vercel.app) · [code](https://github.com/doctorzero666/HireNet)

Turns a business goal into structured tasks and routes each one to an AI agent, a person, or both. My effort went into reliability rather than agent count:

- Every LLM output is schema-validated with a repair loop before it is persisted.
- Each run writes an audit row with cost, latency, and outcome.
- Royalty settlement sits behind a provider interface: a mock, a local Anvil chain, and a Sepolia testnet adapter share one state machine.
- The double-billing race is closed under a lock and proven with `threading.Barrier`: 1 success, 4 rejections, 1 ledger row.
- 1617 hermetic tests run in about 70 s. Test code outnumbers backend code. UI is bilingual, English by default.

Flask, React, SQLite, MCP. Deployed on Railway and Vercel.

### Wit or Die · [code](https://github.com/doctorzero666/Wit-or-die)

Real-time multiplayer quiz. LLM-track champion, 1st of 50 teams, sole full-stack developer. Grading runs server-side at P50 0.24 ms and sits behind a three-question prefetch queue with five graded fallbacks, so seconds of generation never block play.

### Universal Smart Clothes · [code](https://github.com/doctorzero666/universal-smart-clothing)

ESP32 wearable with three controllers. Sensor safety loops run standalone; the LLM sits strictly outside them. Diagnosed a silent BLE Notify transmit-buffer overflow and fixed it with an application-layer send queue: no loss at depth 8 / 20 ms.

Also: [htc-trading-core](https://github.com/doctorzero666/htc-trading-core), a safety-first multi-asset trading research system with deterministic signals and persistent risk controls, 514 tests.

## Contact

[LinkedIn](https://www.linkedin.com/in/zhichao-jiang-2146b82a0/) · CV on request
