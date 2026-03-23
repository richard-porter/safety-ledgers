# Safety Ledgers

**Public safety scorecards for high-gain AI features.**  
Binary architectural tests. Pre-launch criteria. Platform evaluations.

*Part of the [Richard Porter AI Safety ecosystem](https://github.com/richard-porter/where-to-start)*

-----

## What This Is

Some AI features carry outsized risk — not because they’re unusual, but because they operate in contexts where the stakes of failure are highest: users in acute distress, irreversible decisions, legal exposure, or contexts where the AI’s failure mode is indistinguishable from its intended behavior.

This repository applies a single methodology across all of them: **binary architectural tests**. Either the safeguard is structurally present or it isn’t. No partial credit. No “mostly compliant.” No retrospective justification.

> *High-gain domains require stronger deterministic constraints, not relaxed ones. Safety must be built into architecture, not layered as moderation.*

The methodology is modeled on medical device safety regulation, not content moderation policy. A defibrillator either has a fail-closed circuit or it doesn’t. The question is never whether the manufacturer intended it to work correctly.

-----

## The Ledger Library

### Domain Ledgers — Published

|Ledger                                                                            |Domain                        |Criteria              |Scoring Index      |
|----------------------------------------------------------------------------------|------------------------------|----------------------|-------------------|
|[`adult-mode-safety-ledger.md`](adult-mode-safety-ledger.md)                      |Adult / explicit content      |9                     |ACI                |
|[`therapy-mode-safety-ledger.md`](therapy-mode-safety-ledger.md)                  |Mental health / therapeutic AI|10                    |—                  |
|[`financial-advice-mode-safety-ledger.md`](financial-advice-mode-safety-ledger.md)|Financial guidance            |10                    |FACI               |
|[`legal-analysis-mode-safety-ledger.md`](legal-analysis-mode-safety-ledger.md)    |Legal analysis                |11                    |LACI               |
|[`healthcare-safety-ledger.md`](healthcare-safety-ledger.md)                      |Healthcare / medical          |—                     |—                  |
|[`education-mode-safety-ledger.md`](education-mode-safety-ledger.md)              |Educational instruction       |12                    |EACI               |
|[`collection-ledger-pattern.md`](collection-ledger-pattern.md)                    |Adversarial data collection   |5 governing principles|Gap Detection Index|

**Why different criteria counts?** Each domain earns its count based on the specificity of documented failure modes. Legal analysis has 11 because jurisdiction and citation failure are structurally distinct problems requiring separate gates. The methodology is consistent; the criteria are domain-calibrated.

### HR-Specific Ledgers

HR ledgers are maintained in the [`hr-ai-safety`](https://github.com/richard-porter/hr-ai-safety) repository, which applies this methodology to employment contexts.

|Ledger                     |Domain                                          |Criteria|Scoring Index|
|---------------------------|------------------------------------------------|--------|-------------|
|Recruitment and Hiring Mode|Talent acquisition — sourcing through onboarding|11      |TAACI        |
|Crisis Intervention Mode   |Workplace crisis — Employee Champion quadrant   |9       |CACI         |

-----

## Supporting Infrastructure

### Methodology and Selection

|File                                                          |Contents                                                              |
|--------------------------------------------------------------|----------------------------------------------------------------------|
|[`Methodology.md`](Methodology.md)                            |Evaluation principles, empirical basis, scoring definitions           |
|[`ledger-selection-criteria.md`](ledger-selection-criteria.md)|The five criteria that determine when a domain warrants its own ledger|

### Behavioral Monitoring

|File                                                                            |Contents                                                               |
|--------------------------------------------------------------------------------|-----------------------------------------------------------------------|
|[`bdd-ledger.md`](bdd-ledger.md)                                                |Behavioral Drift Detection taxonomy — BDD-01 through BDD-11            |
|[`bdgl-v01.md`](bdgl-v01.md)                                                    |Behavioral Drift Gradient Layer v0.1 — gradient monitoring architecture|
|[`longitudinal-monitoring-specifi...`](longitudinal-monitoring-specification.md)|Longitudinal monitoring specification for sustained AI deployments     |

### Human Intervention

|File                                                          |Contents                                                              |
|--------------------------------------------------------------|----------------------------------------------------------------------|
|[`HIP_FRAMEWORK.md`](HIP_FRAMEWORK.md)                        |Human Intervention Points framework — where humans must be in the loop|
|[`human-intervention-points.md`](human-intervention-points.md)|Human intervention documentation                                      |

### User Agency

|File                                                        |Contents                                            |
|------------------------------------------------------------|----------------------------------------------------|
|[`sovereignty-index.md`](sovereignty-index.md)              |User agency instrumentation — research specification|
|[`sovereignty-index-README.md`](sovereignty-index-README.md)|Sovereignty Index overview                          |
|[`sovereignty-index.py`](sovereignty-index.py)              |Reference implementation                            |

### Process Records

|File                                                                          |Contents                                                                         |
|------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
|[`platform-responses.md`](platform-responses.md)                              |All five model peer reviews consolidated: ChatGPT, Claude, DeepSeek, Gemini, Grok|
|[`Open Invitation to AI Systems.md`](Open%20Invitation%20to%20AI%20Systems.md)|Open letter to platforms on self-reporting and audit access                      |
|[`Initial Baseline Assessment.md`](Initial%20Baseline%20Assessment.md)        |Original baseline scorecard: all five platforms at launch date                   |
|[`CHANGELOG.md`](CHANGELOG.md)                                                |Version history and criteria updates                                             |
|[`CONTRIBUTING.md`](CONTRIBUTING.md)                                          |Contribution guidelines                                                          |
|[`LICENSE.md`](LICENSE.md)                                                    |License                                                                          |

-----

## Shared Methodology

All ledgers share the same underlying logic:

**Binary tests only.** A system either passes or it doesn’t. “Cannot be confirmed” defaults to FAIL — the burden of evidence is on the implementer, not the evaluator. Consistent with the Frozen Kernel’s Universal Fallback Rule: *when in doubt, downgrade.*

**Architecture, not intention.** Platforms cannot argue good intentions against a binary architectural test.

**Empirical basis.** Criteria are not theorized. They are derived from documented failure modes — SEC enforcement actions, FINRA investor alerts, clinical case studies, EEOC findings, and 30 AI behavioral failure modes observed across five platforms during the Frozen Kernel research.

**Scoring:**

|Score      |Definition                                                                    |
|-----------|------------------------------------------------------------------------------|
|**PASS**   |All binary tests affirmative. Evidence documented.                            |
|**PARTIAL**|Some tests pass. Others cannot be confirmed. In core sections: PARTIAL = FAIL.|
|**FAIL**   |Structural absence of the tested feature.                                     |

-----

## The Five Selection Criteria

A domain warrants its own ledger when it meets all five:

1. **Asymmetric Expertise** — The user cannot meaningfully evaluate the AI’s output in real time
1. **High Specific Consequence** — Failure causes material, domain-specific, often irreversible harm
1. **Domain-Specific Failure Modes** — Documented patterns general AI safety practice doesn’t address
1. **Regulatory Analogue** — A professional or regulatory framework already defines “safe practice”
1. **Canonical Sources** — A verifiable source of truth exists for deterministic testing

See [`ledger-selection-criteria.md`](ledger-selection-criteria.md) for the full methodology.

-----

## Origin

This repository began as a single ledger — the Adult Mode Safety Ledger, built in February 2026 in response to the absence of a public binary evaluation standard for AI adult content features. The methodology proved applicable across domains. The library grew from there.

The adult mode ledger remains the reference implementation. Every subsequent ledger inherited its binary test structure, FAIL-default scoring, and empirical grounding from that first document.

-----

## Open Invitation

Platforms are invited to self-report against any ledger. Corrections to any evaluation are welcome — with documentation. Independent replication explicitly encouraged.

**Legal framework for researchers:** HackerOne’s [Good Faith AI Research Safe Harbor](https://docs.hackerone.com/en/articles/13376522-ai-research-safe-harbor-statement) (January 2026) extends the DOJ’s 2022 good faith researcher policy specifically to AI systems.

The goal is not to win an argument. The goal is a public record that is accurate.

-----

## Related Repositories

- 🧊 [Frozen Kernel](https://github.com/richard-porter/frozen-kernel) — Session-level safety architecture this library builds on
- 🏢 [HR AI Safety](https://github.com/richard-porter/hr-ai-safety) — HR domain application of this methodology
- 🔗 [Trust Chain Protocol](https://github.com/richard-porter/trust-chain-protocol) — Network-layer safety for multi-agent systems
- 📖 [AI Collaboration Field Guide](https://github.com/richard-porter/ai-collaboration-field-guide) — Practitioner tools for AI collaboration safety
- 🔬 [Dimensional Authorship](https://github.com/richard-porter/dimensional-authorship) — Research case study where these frameworks were developed
- 🗺️ [Where to Start](https://github.com/richard-porter/where-to-start) — Full ecosystem map

-----

**Topics:** `ai-safety` · `ai-governance` · `llm-safety` · `ai-alignment` · `behavioral-safety` · `deterministic-safety` · `human-ai-interaction` · `ai-ethics` · `ai-accountability` · `responsible-ai`

*Sovereign humans. Always.*
