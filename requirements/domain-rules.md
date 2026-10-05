# Domain Rules

## Purpose

This document identifies the domain rules referenced by the requirements backlog. It separates chess-tournament rules from software requirements so that requirements such as pairing generation and standings calculation have clear meanings.

## Swiss Tournament Lifecycle

The tournament follows this general lifecycle:

1. Tournament is created.
2. Tournament settings are configured.
3. Players are registered.
4. Pre-start registrations may be removed.
5. Tournament is started.
6. First-round pairings are generated.
7. Results and non-game outcomes are recorded.
8. The round is completed.
9. Current scores and history are used to generate the next round.
10. Steps 7–9 repeat until the configured tournament completion conditions are satisfied.
11. Final standings are calculated and the tournament is completed.

## Eligible Players

A player is eligible for pairing when the player is registered for the tournament and has not been withdrawn or otherwise made ineligible under the tournament's configured rules.

A player removed before the tournament starts is not part of the tournament.

A player withdrawn after the tournament starts remains part of historical tournament data but is not eligible for future pairings.

## Tournament Scores

A player's tournament score is calculated from the recorded outcomes according to the tournament's configured scoring rules.

Bye scores are applied according to the configured bye score.

## Pairing Constraints and Preferences

Supported pairing rules are classified as either:

- **Mandatory constraints** — rules that should not be violated unless the system reports that no pairing satisfying all mandatory constraints exists.
- **Pairing preferences** — rules the pairing process should try to satisfy after mandatory constraints have been considered.

This distinction determines how the system handles conflicts between pairing objectives.

## Swiss Score Groups

For subsequent rounds, the current tournament score of each eligible player is an input to pairing generation.

The pairing process should attempt to pair players within compatible score groups according to the configured Swiss-system rules and the priority of pairing constraints/preferences.

## Repeat Opponents

The system should avoid pairing two players who have already played.

A repeat opponent is permitted only when no pairing satisfying all mandatory pairing constraints can be generated.

Pairing history therefore must remain available throughout the tournament.

## Color Assignment

Colors are assigned using:

- Previous color history.
- The tournament's configured color-balancing rules.
- The applicable pairing constraints and preferences.

The first round requires an initial color-assignment rule because players have no prior color history.

## Bye Assignment

When a round has an odd number of eligible players:

- Exactly one eligible player receives a bye.
- The bye is recorded as a non-game outcome.
- The configured bye score is applied to that player.
- Bye history is retained and considered when selecting later byes.

## Round Completion

A round cannot be completed while a required pairing lacks a valid recorded outcome.

A valid outcome may be:

- A recorded game result.
- A bye.
- Another explicitly supported non-game outcome, such as an approved forfeit.

Once all required outcomes are present, the round may be completed and its results become part of the tournament state used for subsequent pairing.

## Standings and Tiebreaks

Standings are calculated from recorded tournament outcomes.

Players are ranked according to:

1. Tournament score.
2. The tournament's configured tiebreak method when scores are equal.

The specific supported tiebreak algorithms must be defined before implementation of FR-036.

## Tournament Completion

A tournament can be completed only when:

- The required number of rounds under the tournament configuration has been completed.
- All required outcomes for those rounds have been recorded.
- The tournament state permits completion.

## Rating Information

The MVP stores player rating information when provided.

Automatic rating calculation/update is outside the MVP.

## Out-of-Scope Domain Rules for the MVP

The following are intentionally not defined as part of the current version because their corresponding functionality is deferred:

- Rating calculation/update rules.
- Late-entry pairing rules for players added after tournament start.
