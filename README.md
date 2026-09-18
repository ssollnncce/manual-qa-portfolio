# Game QA Portfolio: Wheel of Fortune Testing

## Project Overview

This repository contains a self-created Game QA portfolio project focused on a hypothetical mobile game feature: **Wheel of Fortune**. The project demonstrates manual QA documentation for a reward-based spin mechanic, including test planning, functional test cases, and edge cases.

## Scope

The tested feature is a fictional Wheel of Fortune mechanic with the following assumed behavior:

- The feature becomes available after the player reaches Level 3.
- A free Spin is available once every 24 hours.
- The Spin can award regular rewards and a Mega Prize.
- A daily streak mechanic tracks consecutive daily Spins.
- The UI may display a Red Dot Badge when a free Spin is available.
- The feature should handle network interruption, app restart, time manipulation, and duplicate user actions safely.

## Repository Structure

| File | Description |
| --- | --- |
| [test-plan.md](test-plan.md) | Test strategy, scope, assumptions, risks, and coverage approach |
| [test-cases-en.md](test-cases-en.md) | Main English test case suite with 22 commercial-style test cases |

## QA Areas Covered

- Functional testing
- Boundary value testing
- Negative testing
- State persistence testing
- Reward integrity testing
- Cross-screen data consistency
- Network interruption handling
- Duplicate action prevention
- Time manipulation checks
- Access control
- Daily streak mechanics
- Localization testing
- UI state validation

## Tools and Format

This project is written in Markdown so it can be published directly as a GitHub repository. The test cases use a structured manual QA format suitable for portfolio review.

## Suggested Use

For recruiters and hiring managers, start with:

1. [test-plan.md](test-plan.md)
2. [test-cases-en.md](test-cases-en.md)
