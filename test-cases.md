# Wheel of Fortune Manual Test Cases

## TCS_COOLDOWN

### TC-01
**Test Case ID:** TC-01  
**Test Case Title:** Block repeated Spin before the 24-hour cooldown expires  
**Test Description:** Verify that the player cannot start another free Spin before the 24-hour cooldown is completed.  
**Module/Feature:** Wheel of Fortune / Spin Cooldown  
**Priority:** High

**Preconditions:**
- The player has reached Level 3.
- The player completed a Spin less than 24 hours ago.
- Internet connection is stable.

**Test Steps:**
1. Open the Wheel of Fortune screen.
2. Check the Spin button state.
3. Attempt to start another free Spin.

**Test Data:**
- Time since previous Spin: less than 24 hours.

**Expected Results:**
- The Spin button is displayed as disabled.
- A new free Spin cannot be started.
- The remaining cooldown time is displayed accurately.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-02
**Test Case ID:** TC-02  
**Test Case Title:** Unlock Spin exactly after 24 hours  
**Test Description:** Verify that Spin becomes available when exactly 24 hours have passed since the previous Spin.  
**Module/Feature:** Wheel of Fortune / Spin Cooldown  
**Priority:** High

**Preconditions:**
- The player has reached Level 3.
- The previous Spin was completed exactly 24 hours ago.
- Internet connection is stable.

**Test Steps:**
1. Open the Wheel of Fortune screen.
2. Wait until exactly 24 hours have passed since the previous Spin.
3. Check the Spin button state.
4. Start a free Spin.

**Test Data:**
- Cooldown duration: 24 hours.

**Expected Results:**
- Spin becomes available at the 24-hour boundary.
- The Spin button becomes active.
- The Spin starts successfully.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** Boundary value test.

---

### TC-03
**Test Case ID:** TC-03  
**Test Case Title:** Allow Spin after the 24-hour cooldown has expired  
**Test Description:** Verify that Spin remains available after more than 24 hours have passed since the previous Spin.  
**Module/Feature:** Wheel of Fortune / Spin Cooldown  
**Priority:** Medium

**Preconditions:**
- The player has reached Level 3.
- More than 24 hours have passed since the previous Spin.
- Internet connection is stable.

**Test Steps:**
1. Open the Wheel of Fortune screen.
2. Check the Spin availability state.
3. Start a free Spin.

**Test Data:**
- Time since previous Spin: more than 24 hours.

**Expected Results:**
- Spin is available.
- The cooldown countdown is not displayed or is shown as completed.
- A new Spin starts successfully.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-04
**Test Case ID:** TC-04  
**Test Case Title:** Reset cooldown after early Spin with gems  
**Test Description:** Verify cooldown behavior after the player uses premium currency to start an early Spin.  
**Module/Feature:** Wheel of Fortune / Premium Spin  
**Priority:** High

**Preconditions:**
- The player has reached Level 3.
- The free Spin is currently on cooldown.
- The player has enough gems for an early Spin.

**Test Steps:**
1. Open the Wheel of Fortune screen.
2. Start an early Spin using gems.
3. Wait until the Spin is completed.
4. Check the cooldown state.

**Test Data:**
- Sufficient gem balance.

**Expected Results:**
- The required number of gems is deducted exactly once.
- The Spin is completed successfully.
- A new 24-hour cooldown starts from the moment the early Spin was completed (not from the original cooldown's end time).
- Another free Spin is unavailable until the new 24-hour cooldown ends.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** The 24-hour reset rule is an assumption for this practice project; on a real build this must be confirmed against actual requirements before execution.

---

### TC-05
**Test Case ID:** TC-05  
**Test Case Title:** Prevent cooldown bypass by moving system time forward  
**Test Description:** Verify that changing the device time forward does not allow the player to receive an early Spin.  
**Module/Feature:** Wheel of Fortune / Spin Cooldown  
**Priority:** High

**Preconditions:**
- The player completed a Spin less than 24 hours ago.
- Spin is currently on cooldown.
- Internet connection is stable.

**Test Steps:**
1. Record the current cooldown state.
2. Change the device system time to a later time.
3. Restart the app if required.
4. Open the Wheel of Fortune screen.
5. Check Spin availability.

**Test Data:**
- Device system time changed forward.

**Expected Results:**
- Changing device time does not bypass the cooldown.
- Spin remains unavailable until the actual cooldown condition is met.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** Especially relevant if cooldown must be controlled by server time.

---

### TC-06
**Test Case ID:** TC-06  
**Test Case Title:** Preserve cooldown when system time is moved backward  
**Test Description:** Verify that the current cooldown state remains valid after the device time is moved backward.  
**Module/Feature:** Wheel of Fortune / Spin Cooldown  
**Priority:** Medium

**Preconditions:**
- Spin is currently on cooldown.
- The tester can change device date and time settings.

**Test Steps:**
1. Open the Wheel of Fortune screen.
2. Record the remaining cooldown time.
3. Move the device system time backward.
4. Return to the app.
5. Check the Spin state.

**Test Data:**
- Device system time changed backward.

**Expected Results:**
- Cooldown is not reset.
- Spin does not become available incorrectly.
- The feature state matches the actual cooldown end condition.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

## TCS_ERROR_HANDLING

### TC-07
**Test Case ID:** TC-07  
**Test Case Title:** Handle network loss on the 2nd second of Spin animation  
**Test Description:** Verify that the app handles network interruption during Spin without reward loss or duplication.  
**Module/Feature:** Wheel of Fortune / Network Handling  
**Priority:** High

**Preconditions:**
- The player has an available Spin.
- Internet connection is stable before the test starts.

**Test Steps:**
1. Start a Spin.
2. Disable the internet connection on the 2nd second of the animation.
3. Wait until the current Spin state is resolved.
4. Restore the internet connection.
5. Check reward and Spin states.

**Test Data:**
- Network interruption during Spin.

**Expected Results:**
- The app handles the connection loss gracefully.
- The Spin does not cause reward loss or reward duplication.
- After reconnection, Spin and reward states are synchronized with the server.
- The player receives a relevant message if required by the feature design.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-08
**Test Case ID:** TC-08  
**Test Case Title:** Award reward after app closure during Spin  
**Test Description:** Verify that the Spin result is preserved when the app is closed before the animation finishes.  
**Module/Feature:** Wheel of Fortune / Reward Handling  
**Priority:** High

**Preconditions:**
- The player has an available Spin.
- Internet connection is stable.

**Test Steps:**
1. Start a Spin.
2. Close the app while the Spin animation is running.
3. Launch the app again.
4. Open the Wheel of Fortune screen.
5. Check reward state and next Spin availability.

**Test Data:**
- Forced app closure during Spin.

**Expected Results:**
- The Spin result is not lost.
- The reward is granted exactly once.
- Cooldown state is updated correctly.
- The same reward cannot be granted again.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

## TCS_ACCESS

### TC-09
**Test Case ID:** TC-09  
**Test Case Title:** Open Wheel of Fortune after reaching Level 3  
**Test Description:** Verify that the feature becomes available when the player reaches the required level.  
**Module/Feature:** Wheel of Fortune / Access  
**Priority:** Medium

**Preconditions:**
- The player is currently on Level 2.

**Test Steps:**
1. Level up the player to Level 3.
2. Go to the main game screen.
3. Check whether the Wheel of Fortune entry point is displayed.
4. Open the Wheel of Fortune screen.

**Test Data:**
- Player Level: 3.

**Expected Results:**
- Wheel of Fortune becomes available after Level 3 is reached.
- The feature entry point is displayed.
- The Wheel of Fortune screen opens without errors.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-10
**Test Case ID:** TC-10  
**Test Case Title:** Keep Wheel of Fortune unavailable before Level 3  
**Test Description:** Verify that players below the required level cannot access the feature.  
**Module/Feature:** Wheel of Fortune / Access  
**Priority:** Medium

**Preconditions:**
- The player is below Level 3.

**Test Steps:**
1. Open the main game screen.
2. Check whether the Wheel of Fortune entry point is displayed.
3. Try to access the feature if any entry point is visible.

**Test Data:**
- Player Level: 1-2.

**Expected Results:**
- Wheel of Fortune is unavailable.
- The feature entry point is hidden, not just disabled.
- The player cannot open the Wheel of Fortune screen.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

## TCS_STREAK

### TC-11
**Test Case ID:** TC-11  
**Test Case Title:** Increase daily Spin streak after consecutive daily Spins  
**Test Description:** Verify that the streak increases correctly when the player uses Spin every day.  
**Module/Feature:** Wheel of Fortune / Daily Streak  
**Priority:** High

**Preconditions:**
- The player has reached Level 3.
- Daily Spin is available.
- Streak is currently on Day 1.

**Test Steps:**
1. Complete a Spin on Day 1.
2. Wait until the next eligible Spin period.
3. Complete a Spin on Day 2.
4. Repeat the flow until Day 7.
5. Check the streak value after each Spin.

**Test Data:**
- Consecutive Spin usage over 7 days.

**Expected Results:**
- The streak increases by 1 after each successful daily Spin.
- No streak day is skipped.
- Day 7 is displayed correctly.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-12
**Test Case ID:** TC-12  
**Test Case Title:** Grant guaranteed Mega Prize after completing a 7-day streak  
**Test Description:** Verify that the player receives the guaranteed Mega Prize after meeting the 7-day streak condition.  
**Module/Feature:** Wheel of Fortune / Mega Prize  
**Priority:** High

**Preconditions:**
- The player completed Spins for 6 consecutive days.
- Current streak is Day 6.
- Spin is available.

**Test Steps:**
1. Complete a Spin on Day 7.
2. Wait until the Spin is completed.
3. Check the Spin result.
4. Check the granted reward.

**Test Data:**
- Streak: Day 6 to Day 7.

**Expected Results:**
- Streak increases to Day 7.
- The Spin result corresponds to the guaranteed Mega Prize.
- Mega Prize is granted exactly once.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-13
**Test Case ID:** TC-13  
**Test Case Title:** Reset streak to Day 1 after a missed daily Spin  
**Test Description:** Verify that the current streak resets after the player misses the required daily Spin.  
**Module/Feature:** Wheel of Fortune / Daily Streak  
**Priority:** High

**Preconditions:**
- The current streak is higher than Day 1.
- The player misses an available daily Spin.

**Test Steps:**
1. Record the current streak value.
2. Do not use Spin during the full eligible period.
3. Wait until the next available Spin.
4. Complete a Spin.
5. Check the streak value.

**Test Data:**
- Streak: Day 2-Day 6.
- One missed daily Spin.

**Expected Results:**
- The missed Spin breaks the current sequence.
- After the next Spin, streak resets to Day 1.
- The streak value is displayed correctly.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-14
**Test Case ID:** TC-14  
**Test Case Title:** Preserve streak when Spin is completed before the current day ends  
**Test Description:** Verify that a valid daily Spin completed before the day boundary preserves streak progression.  
**Module/Feature:** Wheel of Fortune / Daily Streak  
**Priority:** Medium

**Preconditions:**
- The player has an active daily streak.
- Spin is available near the end of the current day.
- The day boundary rule is defined by requirements.

**Test Steps:**
1. Open Wheel of Fortune shortly before the current day ends.
2. Complete the available Spin before the boundary.
3. Wait until the next day or next eligible period begins.
4. Open Wheel of Fortune again.
5. Check the streak value.

**Test Data:**
- Spin completed shortly before the day boundary.

**Expected Results:**
- The Spin is counted as a valid daily Spin.
- The streak is preserved and progresses according to the day-boundary rule.
- Streak does not reset incorrectly.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** The exact day-boundary rule should be clarified in requirements.

---

## TCS_REWARDS

### TC-15
**Test Case ID:** TC-15  
**Test Case Title:** Grant the displayed reward after Spin completion  
**Test Description:** Verify that the reward granted to the player matches the completed Spin result.  
**Module/Feature:** Wheel of Fortune / Rewards  
**Priority:** High

**Preconditions:**
- The player has an available Spin.
- The current amount of the relevant resource is known.

**Test Steps:**
1. Record the player's resource balance before Spin.
2. Start a Spin.
3. Wait until the animation is completed.
4. Record the displayed reward.
5. Check the player's updated resource balance.

**Test Data:**
- Initial resource balance.
- Displayed Spin reward.

**Expected Results:**
- The granted reward matches the Spin result.
- The reward is granted in the full expected amount.
- The player balance increases by the received reward amount.
- The reward is granted only once.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-16
**Test Case ID:** TC-16  
**Test Case Title:** Preserve awarded reward after app restart  
**Test Description:** Verify that a granted reward remains saved after the app is restarted.  
**Module/Feature:** Wheel of Fortune / Reward Persistence  
**Priority:** High

**Preconditions:**
- The player has an available Spin.
- The current resource balance or inventory state is known.

**Test Steps:**
1. Start and complete a Spin.
2. Confirm that the reward is granted.
3. Close the app.
4. Launch the app again.
5. Check the relevant balance or inventory state.

**Test Data:**
- Reward granted by Spin.
- Balance or inventory before and after restart.

**Expected Results:**
- The awarded reward remains saved after restart.
- The balance or inventory reflects the granted reward.
- The same reward is not granted a second time after restart.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-17
**Test Case ID:** TC-17  
**Test Case Title:** Synchronize reward balance across all game screens  
**Test Description:** Verify that a reward granted by Spin is reflected consistently across every screen that displays that resource, not only the Wheel of Fortune screen.  
**Module/Feature:** Wheel of Fortune / Reward Synchronization  
**Priority:** High

**Preconditions:**
- The player has an available Spin.
- The current coin and gem balances are known.

**Test Steps:**
1. Record the coin and gem balances shown on the main HUD.
2. Complete a Spin that awards coins or gems.
3. Confirm and close the reward popup.
4. Check the balance on the main HUD without navigating away.
5. Open the in-game shop and check the same balance.
6. Open the inventory screen (if applicable) and check the same balance.

**Test Data:**
- Coin balance before and after Spin.
- Gem balance before and after Spin.

**Expected Results:**
- The updated balance is identical across the HUD, shop, and inventory immediately after the reward is granted.
- No screen shows a stale or delayed value.
- No screen shows the reward applied more than once.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** This case specifically targets desync bugs where one screen updates before another.

---

## TCS_LOCALIZATION

### TC-18
**Test Case ID:** TC-18  
**Test Case Title:** Display localized Wheel of Fortune UI for RU, EN, and DE  
**Test Description:** Verify that the feature UI is correctly localized in supported languages.  
**Module/Feature:** Wheel of Fortune / Localization  
**Priority:** Medium

**Preconditions:**
- Wheel of Fortune is available to the player.
- RU, EN, and DE localizations are available in the game.

**Test Steps:**
1. Set the game language to RU.
2. Open Wheel of Fortune and check the UI text.
3. Repeat the check for EN.
4. Repeat the check for DE.

**Test Data:**
- RU locale.
- EN locale.
- DE locale.

**Expected Results:**
- UI text is translated for each selected language.
- No fallback or placeholder keys are displayed.
- Cooldown, reward, error, streak, and Mega Prize texts are localized.
- Text is not clipped, overlapped, or truncated in supported screen sizes.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** DE strings are typically ~30% longer than EN; check UI elements with the least horizontal space first (buttons, badges).

---

## TCS_UI

### TC-19
**Test Case ID:** TC-19  
**Test Case Title:** Display Red Dot Badge when Spin is available  
**Test Description:** Verify that the Red Dot Badge appears when the player has an available free Spin.  
**Module/Feature:** Wheel of Fortune / UI Indicators  
**Priority:** Medium

**Preconditions:**
- The player has reached Level 3.
- Free Spin is available.

**Test Steps:**
1. Open the main game screen.
2. Check the Wheel of Fortune entry point.
3. Open Wheel of Fortune.
4. Complete a Spin.
5. Return to the main game screen.
6. Check the Red Dot Badge state again.

**Test Data:**
- Spin state: available, then unavailable after use.

**Expected Results:**
- Red Dot Badge is displayed when free Spin is available.
- Red Dot Badge is removed after the Spin is used.
- Badge state matches the actual Spin availability.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

### TC-20
**Test Case ID:** TC-20  
**Test Case Title:** Display reward popup with correct content after Spin  
**Test Description:** Verify that the reward popup shown after a Spin displays the correct reward and can be dismissed correctly.  
**Module/Feature:** Wheel of Fortune / Reward Popup UI  
**Priority:** Medium

**Preconditions:**
- The player has an available Spin.
- Internet connection is stable.

**Test Steps:**
1. Start a Spin and wait for the animation to finish.
2. Check the reward popup content against the wheel's landing sector.
3. Check that a "Claim" (or equivalent) button is present and enabled.
4. Tap the "Claim" button.
5. Check that the popup closes and control returns to the main Wheel of Fortune screen.

**Test Data:**
- Spin result / landing sector.

**Expected Results:**
- The popup displays the reward that matches the wheel's landing sector.
- The "Claim" button is visible, enabled, and tappable exactly once.
- Tapping "Claim" closes the popup without freezing the screen or requiring a second tap.
- The popup does not reappear after being dismissed for the same Spin.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -

---

## TCS_INTEGRITY_AND_PERSISTENCE

### TC-21
**Test Case ID:** TC-21  
**Test Case Title:** Prevent repeated Spin start after multiple rapid taps  
**Test Description:** Verify that multiple rapid taps on the Spin button do not trigger duplicate Spins or duplicate rewards.  
**Module/Feature:** Wheel of Fortune / Duplicate Action Prevention  
**Priority:** High

**Preconditions:**
- The player has an available Spin.
- Internet connection is stable.

**Test Steps:**
1. Open the Wheel of Fortune screen.
2. Tap the Spin button rapidly several times.
3. Wait until the operation is completed.
4. Check Spin count, reward state, and cooldown state.

**Test Data:**
- Multiple rapid taps on Spin.

**Expected Results:**
- Only one Spin is processed.
- Only one reward is granted.
- Only one cooldown state is created.
- Additional taps are ignored or blocked while the first Spin is in progress.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** Duplicate action and race-condition scenario.

---

### TC-22
**Test Case ID:** TC-22  
**Test Case Title:** Preserve cooldown after app restart  
**Test Description:** Verify that the cooldown state remains saved after the app is closed and reopened.  
**Module/Feature:** Wheel of Fortune / State Persistence  
**Priority:** High

**Preconditions:**
- The player has reached Level 3.
- The player has an available Spin.

**Test Steps:**
1. Complete a Spin.
2. Confirm that cooldown starts.
3. Close the app completely.
4. Launch the app again.
5. Open Wheel of Fortune.
6. Check the cooldown state.

**Test Data:**
- App restart during active cooldown.

**Expected Results:**
- Cooldown remains active after app restart.
- Remaining cooldown time is displayed correctly.
- Free Spin does not become available early.

**Actual Results:** To be completed during execution.  
**Status:** Not Executed  
**Notes:** -
