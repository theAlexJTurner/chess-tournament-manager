# Requirements Elicitation

## Purpose

This document records the initial requirements-elicitation approach used to develop the Chess Tournament Management System backlog.

The objective was to identify what a tournament organizer needs from a desktop Swiss-system tournament manager before making implementation decisions.

## Problem Context

Tournament organizers currently have to manage player registration, tournament configuration, Swiss pairings, colors, byes, round progression, results, standings, and tournament completion. Manual administration increases the risk of pairing mistakes, incorrect scores, duplicate results, and lost tournament information.

The proposed system addresses these administrative problems with a single desktop application.

## Primary Stakeholder

The primary stakeholder is the **tournament organizer / tournament director**, because this person performs the majority of the system's core operations.

Secondary stakeholders include:

- Chess club or tournament organization
- Tournament participants
- Software maintainer/developer

## Elicitation Focus

The elicitation process focused on:

1. Tournament creation and configuration.
2. Player records and tournament registration.
3. Starting and managing a tournament.
4. Swiss-system pairing.
5. Color balancing and repeat-opponent avoidance.
6. Bye assignment and bye history.
7. Round management.
8. Result entry and validation.
9. Score calculation and standings.
10. Tiebreak handling.
11. Tournament completion.
12. Data persistence and recovery.
13. Usability, reliability, integrity, compatibility, accessibility, offline operation, security, and maintainability.

## Requirements Refinement

The initial generated requirements were reviewed for:

- Clarity
- Unambiguity
- Atomicity
- Testability
- Feasibility
- Consistency
- Traceability
- Dependency correctness

Broad or overlapping requirements were refined or consolidated where necessary. Examples include:

- Separating removal before tournament start from withdrawal after tournament start.
- Separating first-round generation from subsequent-round generation.
- Folding missing-result handling into the round-completion requirement.
- Consolidating persistence/retrieval behavior.
- Removing overly broad data-consistency wording as an independent requirement.
- Making pairing constraints distinguish mandatory constraints from preferences.
- Making performance requirements measurable.
- Making usability requirements task-based and testable.

## Scope Decisions

The MVP is intentionally centered on one complete user journey:

**Register players → configure tournament → start tournament → generate pairings → run rounds → enter results → calculate standings → complete tournament**

Automatic rating calculation and late registration after tournament start were deferred because they add complexity without being necessary to complete that core workflow.

A participant-facing view was also deferred to the Could Have category because it is useful but not necessary for the organizer to run the tournament.

## Important Domain Clarifications

The backlog references Swiss-system rules, color balancing, bye rules, scoring, tiebreaks, and pairing constraints. These rules must be defined separately from the high-level requirements.

Those rules are documented in `domain-rules.md`.
