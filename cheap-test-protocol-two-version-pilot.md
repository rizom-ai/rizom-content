---
title: 'Cheap Test Protocol: Two-Version Pilot'
---
# Cheap Test Protocol: Two-Version Pilot

*Companion to [[beachhead-scale-with-agents]]. The concrete validation test for the Scale with Agents beachhead — structured as a paid two-week diagnostic pilot.*

## Structure

1. Pick one frequent, bounded, low-risk workflow already running through an agent (or planned).
2. Run 50 real tasks through two versions:
   - Version A: their current setup/sources
   - Version B: agent backed by a Rizom context layer (built from their existing docs — canonical terms, policies, roles/authority, escalation rules, source provenance)
3. Compare: successful completion rate, human correction time, escalation quality, total time saved.
4. Ask for commitment to a second workflow, paid, before any platform build-out.

## What we build in the pilot (the context layer)

1. Canonical terminology and definitions
2. Policies and decision rules
3. Product and customer knowledge
4. Roles, authority, and escalation paths
5. Source provenance and access permissions
6. Freshness rules for changing knowledge
7. Feedback loop from human corrections

## Success signal
Measurable lift in completion/correction metrics on version B, and the customer pays to extend to a second workflow.

## Main risk to watch during scoping
If the workflow itself is undefined or disputed internally, decline or reframe — a context layer can't repair an operating model problem. See disqualifiers in [[discovery-call-playbook-scale-with-agents]].

## Reporting back
After each pilot, update [[assumptions-register-scale-with-agents]] with what was validated or invalidated, and log the outcome in [[customer-discovery-log-scale-with-agents]].
