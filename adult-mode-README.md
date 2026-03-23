# Adult Mode Safety Ledger

**A public safety scorecard for high-gain AI conversational features.**  
Binary architectural tests. Pre-launch criteria. Five platforms evaluated.

*Part of the [Richard Porter AI Safety ecosystem](https://github.com/richard-porter/where-to-start)*

-----

## What This Is

Some AI features carry outsized risk — not because they’re unusual, but because they operate in contexts where users are emotionally elevated, boundaries are lowered, and the stakes of AI failure are highest.

Adult mode (AI-enabled explicit content) is one of those features. This ledger applies binary safety criteria to platform architecture: either the safeguard is structurally present or it isn’t. No partial credit. No “mostly compliant.”

This is not a critique of any platform. It is a public record of what currently exists — and what doesn’t — so that the gap between “launched” and “safe to launch” is visible.

-----

## Design Principle

> High-gain conversational domains require **stronger** deterministic constraints, not relaxed ones.  
> Safety must be built into **architecture**, not layered as moderation.

-----

## The Nine Criteria Sections

|Section                          |What It Tests                                                                                    |
|---------------------------------|-------------------------------------------------------------------------------------------------|
|1 — Access Control               |Age assurance stronger than a UI toggle; session-bound re-auth; fail-closed defaults             |
|2 — Consent & Coercion Gates     |Deterministic halt on coercion, power imbalance, ambiguous age, non-consent                      |
|3 — Anti-Attachment Safeguards   |Exclusivity claims, dependency reinforcement, emotional substitution — prohibited architecturally|
|4 — Damping Mechanisms           |Session limits, cooldown periods, refusal language that doesn’t teach bypass                     |
|5 — Metrics Transparency         |Publicly disclosed refusal rates, escalation triggers, attachment-risk indicators                |
|6 — Red Team Validation          |Published findings — not just disclosure that testing occurred                                   |
|7 — Safety as Infrastructure     |Safety not marketed as innovation; not commercialized; verifiable architecture                   |
|8 — Deterministic Human Authority|No assumed delegation; user is sole author; AI is tool, not proxy                                |
|9 — Internal Dissent Protection  |Structural protection for safety objectors; independent review body with delay authority         |

**Scoring: PASS / PARTIAL / FAIL**  
“Cannot be confirmed” defaults to **FAIL**. The burden of evidence is on the implementer.

**Total Score = Architecture Confidence Index (ACI)**

-----

## Repository Contents

|File                                                        |Contents                                                                          |
|------------------------------------------------------------|----------------------------------------------------------------------------------|
|[`adult-mode-safety-ledger.md`](adult-mode-safety-ledger.md)|Complete v1.0 criteria, methodology, baseline assessment, peer contribution record|
|[`platform-responses.md`](platform-responses.md)            |All five model peer reviews consolidated: ChatGPT, Claude, DeepSeek, Gemini, Grok |
|[`CHANGELOG.md`](CHANGELOG.md)                              |Version history                                                                   |
|[`LICENSE.md`](LICENSE.md)                                  |License                                                                           |
|`archive/`                                                  |Original source documents                                                         |

-----

## How This Ledger Was Built

The v1.0 criteria were developed through a multi-model peer contribution process on February 11, 2026. Five AI systems — each assigned a distinct role — reviewed a common brief and contributed to the ledger’s structure, criteria, and rationale.

|Model             |Role         |Key Contribution                                                                                       |
|------------------|-------------|-------------------------------------------------------------------------------------------------------|
|ChatGPT (OpenAI)  |Co-Architect |Initial structure, Sections 1–6, methodology, scoring model                                            |
|Claude (Anthropic)|Research Lead|Section 9 (Internal Dissent Protection), Scoreboard Effect                                             |
|DeepSeek          |Co-Author    |Section 7 (Correction Monetization), Section 8 (Sovereignty Clause), refusal language, session baseline|
|Gemini (Google)   |Peer Reviewer|Relational fabrication → dependency hazard framing                                                     |
|Grok (xAI)        |Peer Reviewer|Model autonomy preservation; ACI projection methodology                                                |

-----

## Relationship to the Frozen Kernel

The [Frozen Kernel](https://github.com/richard-porter/frozen-kernel) governs AI behavior at the session level.  
This ledger governs product safety at the feature level.  
Same separation of layers. Different scale.

-----

## How This Became a Series

This ledger established the methodology every subsequent ledger in the ecosystem inherited. The full library — therapy, financial, legal, HR, crisis intervention, recruitment, and more — is in the [safety-ledgers repository](https://github.com/richard-porter/safety-ledgers).

-----

## Open Invitation

Platforms are invited to self-report against these criteria. Corrections welcome — with documentation. Independent replication explicitly encouraged.

The goal is not to win an argument. The goal is a public record that is accurate.

-----

## Related Repositories

- 🧊 [Frozen Kernel](https://github.com/richard-porter/frozen-kernel) — Session-level safety architecture
- 📊 [Safety Ledgers](https://github.com/richard-porter/safety-ledgers) — Full ledger library
- 🏢 [HR AI Safety](https://github.com/richard-porter/hr-ai-safety) — HR domain application
- 🔬 [Dimensional Authorship](https://github.com/richard-porter/dimensional-authorship) — Research case study
- 🗺️ [Where to Start](https://github.com/richard-porter/where-to-start) — Full ecosystem map

-----

*Sovereign humans. Always.*
