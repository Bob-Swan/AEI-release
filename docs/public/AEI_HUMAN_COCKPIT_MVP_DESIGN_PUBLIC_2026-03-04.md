# AEI Human Cockpit MVP Design (Public)

Date: March 4, 2026

## Purpose

Define the minimum operator interface required to prove governed AI-assisted operations.

## MVP Goal

One screen should answer:

1. What is the system doing now?
2. What is blocked and why?
3. What action is allowed next?
4. What evidence can be exported now?

## Panel Design

1. System status and policy gate:
   - Runtime state, governance state, block reason, and next allowed action.
2. Task queue:
   - Active and historical task states with filter and search.
3. Task drilldown:
   - Lifecycle timeline, retry lineage, and execution context.
4. Event stream:
   - Live timeline with task/correlation linkage.
5. Runbooks and quick actions:
   - Standardized recovery operations and evidence export.

## Operator Interaction Model

1. Detect issue in status, queue, or event timeline.
2. Inspect task drilldown and policy state.
3. Execute an approved quick action or workflow step.
4. Confirm outcome in event stream.
5. Export evidence bundle for handoff.

## Core Interaction Rules

1. Every block card includes a reason and allowed next action.
2. Side-effecting actions remain policy-gated.
3. Task-event linkage remains visible at selection time.
4. Evidence export returns deterministic payloads.

## MVP Exit Criteria

1. Restricted action in safe mode shows deterministic block behavior.
2. Task selection exposes lifecycle and drilldown context.
3. Event selection exposes linkage metadata.
4. Evidence export succeeds with status and event context.

## Forward-Looking Statement

This document contains forward-looking product statements. Features and sequencing may evolve.
