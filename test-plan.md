# Test Plan: Wheel of Fortune

## 1. Objective

The objective of this test plan is to validate the quality of a hypothetical Wheel of Fortune feature in a mobile game. The focus is on business rules, player-facing behavior, reward integrity, edge cases, and resilience to interruption scenarios.

This test plan is part of a self-created Game QA portfolio project and is not connected to any internal or confidential production system.

## 2. Feature Under Test

**Feature:** Wheel of Fortune  
**Platform:** Mobile game, Android and iOS assumed  
**Testing Type:** Manual functional testing  
**Test Level:** Feature-level QA  
**Primary Language:** English

## 3. Assumptions

- The Wheel of Fortune feature becomes available after the player reaches Level 3.
- A free Spin is available once every 24 hours.
- The game displays cooldown state when a free Spin is not available.
- The game may allow an early Spin by spending premium currency, if supported by requirements.
- Rewards must be granted exactly once per successful Spin.
- The daily streak mechanic progresses through consecutive daily Spins.
- A Mega Prize is guaranteed after completing a 7-day streak.
- Server-side state is considered the source of truth for cooldown, rewards, and streak.
- RU, EN, and DE are assumed supported localization languages for this practice project.

## 4. Out of Scope

- Internal implementation details
- Backend database validation
- Probability distribution auditing beyond the guaranteed Mega Prize rule
- Payment flow testing for premium currency purchase
- Performance testing
- Automation implementation
- Real production telemetry or analytics validation

## 5. Test Approach

The test suite combines positive, negative, boundary, and interruption scenarios. The goal is not only to confirm that the Spin can be launched, but also to validate state transitions and player account integrity.

Key test design techniques:

- Boundary value analysis for the 24-hour cooldown
- Equivalence partitioning for access by player level
- Negative testing for cooldown bypass and offline behavior
- State transition testing for cooldown, streak, and reward states
- Interruption testing for app close and network loss
- Data integrity testing for duplicate rewards and duplicate actions

## 6. Entry Criteria

- A test build with the Wheel of Fortune feature is available.
- Test accounts can be configured at different player levels.
- Test accounts can be configured with known resource balances.
- QA can modify device time and network state.
- Requirements or acceptance criteria are available for cooldown, streak, and reward behavior.

## 7. Exit Criteria

- All high-priority test cases are executed.
- Any potential issues observed during real execution would be documented separately in an actual issue tracking system.
- Reward duplication and reward loss scenarios are verified.
- Cooldown and streak behavior are validated against requirements.
- Execution status, blockers, and requirement questions should be documented only after testing an actual build.

## 8. Test Environment

| Area | Value |
| --- | --- |
| Devices | Android and iOS mobile devices or emulators |
| Network | Wi-Fi, mobile network simulation, offline mode |
| Accounts | Level 1, Level 2, Level 3+, streak-specific accounts |
| Locales | EN, RU, DE |
| Build Type | QA or staging build |

## 9. Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Cooldown can be bypassed by changing device time | Players may receive extra rewards | Test forward and backward time manipulation |
| Network loss during Spin causes reward loss | Player trust impact | Test interruption and sync recovery |
| Multiple taps trigger duplicate Spin requests | Economy balance impact | Test duplicate action prevention |
| Streak resets incorrectly | Retention mechanic impact | Test streak boundaries and missed-day behavior |
| Localization text is clipped | Poor UX in supported markets | Test RU, EN, and DE UI states |

## 10. Deliverables

- Test plan
- English test case suite (22 test cases)
