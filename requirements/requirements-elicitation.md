# Requirements Elicitation

## LLM Used

ChatGPT

## Purpose

The LLM was used to perform an initial requirements elicitation pass
for a chess tournament management desktop application.

## Prompt

I am developing a desktop application for managing chess tournaments. The application is intended to help chess tournament organizers manage tournaments more efficiently and reduce manual work.

The application should support:

Player registration and management
Tournament creation and configuration
Swiss-system tournament pairing
Round management
Game result entry
Tournament standings
Chess ratings/ELO management
Color balancing
Bye handling
Tournament data storage and retrieval

The application is intended primarily for chess clubs and tournament organizers. It should be usable for tournaments with varying numbers of players.

My planned implementation may use React, TypeScript, Electron, Node.js, SQLite, and a C++ pairing engine, but do not assume these technologies are requirements unless they are directly relevant to a user or system requirement.

I am currently performing an initial requirements elicitation pass. Help me identify what the system should accomplish from the perspective of its stakeholders.

Based on the chess tournament management application described above, identify the stakeholders who would interact with, depend on, or be affected by the system.

For each stakeholder:

Identify the stakeholder.
Describe their role.
Describe their goals.
Identify what they would expect from the system.
Identify any potential conflicts between stakeholder needs.

Focus on realistic stakeholders for a chess tournament management application rather than inventing unnecessary roles.

Using the chess tournament management application description and stakeholder analysis, create an initial requirements backlog representing the outcome of an initial requirements elicitation pass.

Generate approximately 30–40 requirements.

For every requirement, provide the following metadata:

Requirement ID
Requirement description
Requirement type (functional or non-functional)
Priority (Must, Should, Could, Won't)
Stakeholder
Rationale
Dependencies on other requirements
Acceptance criteria
Status

Requirements should describe what the system needs to accomplish rather than specifying implementation details.

Write functional requirements using clear, testable language such as:
"The system shall..."

For non-functional requirements, make them measurable or testable whenever possible.

Identify dependencies between requirements. For example, generating tournament pairings may depend on having registered players and an active tournament.

Avoid duplicate requirements, vague requirements, and requirements that are actually implementation decisions.

Organize the backlog into logical categories such as:

Player Management
Tournament Management
Pairing and Swiss System
Round Management
Results
Standings
Ratings
Data Management
User Interface
Non-functional Requirements

Focus specifically on the Swiss-system tournament functionality of the chess tournament management application.

Identify the requirements necessary for correctly managing Swiss-system pairings.

Consider:

Player scores
Avoiding repeat opponents
Color allocation and color balancing
Number of rounds
Odd numbers of players
Byes
Players withdrawing from a tournament
Players joining or being removed before the tournament starts
Players with equal scores
Pairing constraints
Round generation
Invalid or impossible pairing situations
Recording pairing history

For each requirement, provide:

ID
Requirement
Priority
Rationale
Dependencies
Acceptance criteria

Do not assume a particular pairing algorithm or programming language. Focus on what the system must accomplish.

# Second Prompt

Review the initial requirements backlog for the chess tournament management system you just created. Perform a requirements gap analysis.

Identify:

Important requirements that are missing.
Requirements that are too vague.
Requirements that are duplicates.
Requirements that combine multiple independent requirements.
Requirements that are not actually requirements.
Requirements that are too difficult to test.
Missing non-functional requirements.
Missing edge cases.
Missing stakeholder needs.
Incorrect or questionable dependencies.

For each issue, explain why it is an issue and propose a revised or additional requirement.

Do not unnecessarily expand the scope of the application

# Third Prompt

Review the requirements backlog with the additions and revisions you just made using standard software requirements engineering principles. For every requirement, evaluate whether it is:

Clear
Unambiguous
Atomic
Testable
Feasible
Consistent
Traceable

Flag requirements that fail one or more criteria and explain how they should be rewritten.

Do not change requirements for stylistic reasons alone. Focus on issues that could cause ambiguity, implementation problems, or disagreement between stakeholders.

# Fourth Prompt

Now using the requirements backlog with the most recent changes you just made for clearness, consistency, etc, analyze the requirements backlog for dependencies.

For each requirement:

Identify prerequisite requirements.
Identify requirements that depend on it.
Explain the dependency.
Identify circular dependencies.
Identify requirements that incorrectly claim a dependency.

Then produce a dependency map showing the major dependency chains.

Pay particular attention to dependencies involving:

Tournament creation
Player registration
Player assignment
Round creation
Pairing generation
Result entry
Standings
Next-round generation
Rating calculations
Tournament completion

# Fifth Prompt

With the dependency mapping you just made and the most recent iteration of the requirements backlog:

Determine whether the backlog contains an appropriate balance of functional and non-functional requirements.

Identify missing non-functional requirements related to:

Performance
Reliability
Data integrity
Usability
Accessibility
Security
Maintainability
Offline operation
Compatibility
Backup and recovery

Only recommend non-functional requirements that are realistically relevant to a desktop chess tournament management application.

Make each proposed requirement specific and testable rather than vague statements such as "the system should be fast" or "the system should be user-friendly."

# Sixth Prompt

Review the latest chess tournament management requirements backlog with all additions you just made.

Prioritize the requirements for an initial MVP.

Use:

Must Have
Should Have
Could Have
Won't Have for this version

The MVP should allow a tournament organizer to successfully create and run a Swiss-system chess tournament from player registration through final standings.

Explain the reasoning behind each major prioritization decision.

Do not prioritize implementation technologies. Prioritize capabilities from the user's perspective.



Lastly,
Create a professional Markdown requirements backlog suitable for submission in a GitHub repository with 
stakeholder-analysis.md, requirements-backlog.md, requirements-elicitation.md, domain-rules.md using the rules below or your own discretion based on optimal structure for requirements.
Merge or create additional files as neccesary for optimal requirements structure.

Rules:

Organize the document into:

Briefly describe the problem being solved.

Stakeholders

List the relevant stakeholders.

Requirements Backlog

Create a table containing:

ID
Requirement
Type
Priority
Stakeholder
Dependencies
Status
Acceptance Criteria

Provide acceptance criteria for each requirement.

Dependency Overview

Summarize the major dependency chains.

Initial Scope

Identify the requirements considered essential to the initial version.

Do not add new requirements at this stage. Only organize and clearly present the requirements provided.

## Output

The resulting requirements backlog is documented in
`requirements-backlog.md`.

## Notes

The generated requirements represent an initial pass and may be
refined as additional stakeholder information becomes available.
