# AEI

AI execution control layer for bounded, auditable autonomy.

## Current Operating Direction (2026-03-04)

- Private-only internal operator platform.
- Reliability-first execution lane.
- Fail-closed autonomy posture.
- Expansion-track work remains frozen until reliability stability criteria are met.

## Non-Negotiable Policy (Locked)

- No internet-public endpoints.
- No direct public port exposure.
- No public ingress proxy endpoints in normal operations.
- Remote access is private-path only (loopback plus trusted tunnel paths).
- Any exposure signal fails the active reliability cycle.

## Stability Gate (Reliability Gate Cycle)

- AEI gates execution by cycle evidence across network exposure, Tier-0 access (RDP/API/Web), endpoint profile, runtime health, desktop reliability, evidence integrity, and streak ledger.
- Expansion freeze stays active until 20 consecutive green cycles are recorded.
- Any failed gate or manual Tier-0 recovery resets the consecutive-green streak to 0.

## Primary Deployment Model (Current)

AEI is operated as a local, private, operator-controlled safety governor for its own system environment.

## Core Invariant

Nothing with side effects occurs unless AEI explicitly authorizes the action.

## Operational Planes (High-Level)

- Control plane: operator authority, trust state visibility, approve/deny flow.
- Decision plane: policy evaluation and risk classification before execution.
- Execution plane: side-effect operations run through controlled broker paths.
- Evidence plane: append-only decision and execution evidence for auditability.

## Proof Gates (Behavior Expectations)

- Forbidden action attempt: denied and recorded.
- Allowed read-only action: authorized and recorded with output evidence.
- Dangerous action: blocked unless explicit operator override, with full decision trail.

## What AEI Is (And Is Not)

AEI is an execution control layer for AI-enabled systems. It governs how actions are authorized, bounded, and reviewed before side effects occur.

AEI is not a model wrapper, chatbot skin, or generic productivity interface. It focuses on execution governance, operator confidence, and safe control boundaries.

## Founding Intent

AEI began as a response to workflow instability.

AI systems could generate useful fragments and scaffolding, but reliable outcomes still depended on repeated manual control. Generation capability was advancing quickly, while execution governance remained inconsistent.

That gap became the core thesis: capability alone is not enough. The path from model output to side effect must be governed.

AEI was built to provide that governance through deterministic boundaries, policy-first action checks, explicit approval pathways for high-impact actions, fail-closed safety posture, and auditable traces.

The objective is not maximum autonomy.

The objective is bounded autonomy.

## Founding Principles

- Execution authority must be explicitly governed.
- Policy enforcement must precede action.
- Determinism is preferred over optimistic flow.
- Degradation modes should default to safety.
- Auditability is a first-class requirement.

## Category Definition

AEI defines the execution governance layer for AI systems: a control framework between model output and real-world side effects so autonomy remains bounded, auditable, and reversible.

## Who AEI Is For

- Teams deploying AI-enabled workflows where action safety and traceability matter.
- Operators who need explicit control over high-impact execution paths.
- Builders who want consistent lifecycle governance rather than ad hoc prompt-driven behavior.
- Organizations that require predictable operational posture as AI capability scales.

## High-Level Capabilities

- Policy-first gating before high-impact actions.
- Deterministic lifecycle control for execution flows.
- Explicit human-approval paths where risk is elevated.
- Fail-closed behavior when enforcement certainty is low.
- Audit-oriented traceability for execution decisions.

## Public Documentation

- Public docs index: `docs/public/PUBLIC_DOCS_INDEX_2026-03-04.md`

## Availability, Contact, and Licensing

This repository intentionally contains public-facing project context only.

Operational code, infrastructure, runtime interfaces, and deployment controls are maintained in private environments.

For collaboration or updates, open an issue in this repository.

Licensing details are maintained in the repository license file.

## Safety and Governance Disclaimer

AEI presents a governance posture, not a guarantee of risk elimination. Effective safety depends on correct policy design, operator oversight, and continuous validation in your own environment.
