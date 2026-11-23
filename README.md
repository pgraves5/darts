# Darts Games Scoreboard

A responsive, browser-based darts scoreboard application supporting **X01 Games** (601, 501, 401, 301, 201, 101), **Standard Cricket**, **3-Way Cricket**, **BowTie**, and **Shanghai**. Open `index2.html` directly in any modern desktop, tablet, or mobile browser to play.

---

## Table of Contents
1. [Match Setup & Navigation](#match-setup--navigation)
2. [Universal Rules & Controls Across All Games](#universal-rules--controls-across-all-games)
3. [X01 Games](#x01-games-601-501-401-301-201-101)
4. [Standard Cricket](#standard-cricket-2-players)
5. [3-Way Cricket](#3-way-cricket-3-players)
6. [BowTie](#bowtie-1-15-players)
7. [Shanghai](#shanghai-1-15-players)
8. [Keyboard & Input Shortcuts](#keyboard--input-shortcuts)

---

## Match Setup & Navigation

### Starting a Match
1. **Game Mode**: Choose from **601, 501, 401, 301, 201, 101, Standard Cricket, 3-Way Cricket,** or **BowTie**.
2. **Player Count Defaults**:
   - Selecting an X01 game (601, 501, 401, 301) defaults to **2 Players** (supports 1–4 players).
   - Selecting 201 or 101 defaults to **1 Player** (supports 1–4 players).
   - Selecting Standard Cricket defaults to **2 Players** (fixed at 2).
   - Selecting 3-Way Cricket defaults to **3 Players** (fixed at 3).
   - Selecting BowTie defaults to **2 Players** (supports 1–15 players).
3. **Player Name Defaults**:
   - Selecting a new **Game Mode** automatically resets player names back to their defaults (`P1`, `P2`, `P3`, etc.).
   - Players can customize names prior to starting the match.
   - Names are automatically sanitized to uppercase alphanumeric characters.
   - Name length limits: Up to 5 characters for standard games and BowTie; up to 2 characters for games with more than 6 players.
4. **Starting Mode (X01 Only)**: Choose between **Straight-in** (score counts immediately) and **Double-in** (must hit a double to begin scoring).
5. Select **START MATCH** to begin live scoring.

### In-Match Navigation
- **Header Title**: Dynamically displays the active game mode and rule set (e.g. `501 - Double-in` or `BowTie`).
- **HELP Button**: Located in the top header bar next to New Match. Selecting **HELP** opens this `README.md` file in a new tab for instant access to game rules, keyboard shortcuts, and match mechanics.
- **New Match**: Located at the top right of the header bar. Selecting **New Match** returns to the setup screen at any time to configure and launch a fresh match.
- **Enhanced High-Visibility Displays**: All scoreboards, target matrices, player cards, average displays, and keypad controls are scaled up by 20% with high-contrast typography for optimal readability across phones, tablets, and large screens.

---

## Universal Rules & Controls Across All Games

### Maximum Turn Score Guard (The 180 Rule)
- In standard darts, the maximum possible score with 3 darts in a single turn is **180** (three Triple 20s).
- Across all game types (X01, BowTie, etc.), entering any turn score greater than 180 is blocked.
- The app displays an alert in bold red font:
  > **"The max score is 180, please correct the score and try ENTER again"**
- The entered score is **not** automatically capped or recorded as 180. The user's input remains in the entry field so they can correct it using `Del` or the keypad and press `ENTER` again.

### Multi-Level Undo
- The **UNDO** button rolls back the most recent completed turn or individual dart action.
- Undo restores the exact snapshot of scores, marks, round progression, active player, and turn states.
- Selecting **UNDO** clears any active warning or validation messages.

---

## X01 Games (601, 501, 401, 301, 201, 101)

### Objective
Each player begins with the chosen starting score (e.g., 501). Players alternate turns, throwing up to 3 darts per turn, subtracting their turn total from their remaining score until reaching exactly **0**.

### Rules & Mechanics
- **Starting In Rules**:
  - **Straight-in**: Any dart scores points immediately starting from the first throw.
  - **Double-in**: A player's score does not begin counting down until they hit any double (D1–D20) or the Double Bull (50). Darts thrown prior to the first double do not score.
- **Bust Rule**:
  - A turn is a **Bust** if the turn score reduces the remaining score below 0 or leaves a remaining score of exactly 1 (since it is impossible to finish on a double with a score of 1).
  - On a bust, the turn scores 0 points, the player's score reverts to what it was at the start of that turn, and the message `"You Busted....use UNDO to correct this if appropriate."` is displayed.
- **Finishing (Double-Out)**:
  - The final winning dart must land on a **Double** (D1–D20) or the **Double Bull** (50) to reach exactly 0.
- **Live Checkout Suggestions**:
  - For scores of 170 or lower, the app automatically calculates checkout routes, displayed on a single line. When the remaining score is a valid double finish (≤ 50), both the 1-dart (double out) option and a 2-dart option are shown; otherwise the best 2-dart and/or 3-dart routes are shown. Routes prioritize standard tournament doubles (D20, D16, DBull).
- **Running 3-Dart Average**:
  - The live scoreboard tracks and displays each player's 3-dart running average on their score card.

### Keypad & Scoring Controls
- **Numeric Keypad (0–9)**: Enter turn scores directly.
- **Arithmetic Operators (`+`, `*`)**: Enter multi-dart formulas, e.g. `20*3 + 19` or `60+60+20`.
- **Del**: Deletes the last entered character.
- **MISS**: Quick-enters a score of 0.
- **BUST**: Manually records a bust for the active player.
- **Quick Preset Buttons**: One-tap buttons for common turn scores: `26`, `41`, `45`, `60`, `81`, and `100`.
- **ENTER**: Submits the turn, applies bust checks and the max score guard (> 180), and advances to the next player.

---

## Standard Cricket (2 Players)

### Objective
Close all designated targets and accumulate a point total equal to or higher than the opponent. The first player to close all targets with equal or greater points wins the match.

### Targets & Markings
The 7 active targets are **20, 19, 18, 17, 16, 15, and Bullseye (B)**.
- **Single Hit**: 1 mark (`/`)
- **Double Hit (D)**: 2 marks (`X`)
- **Triple Hit (T)**: 3 marks (`⨷` - closed)
- **Single Bull (outer)**: 1 mark
- **Double Bull (inner)**: 2 marks (Double hit)

### Scoring Points & Permanent Score Rule
- A target is **closed** for a player once they earn **3 marks**.
- Once a player has closed a target, any subsequent hits they land on that target award points (face value per mark; Bull awards 25 points per mark) **as long as the opponent has not closed it**.
- **Permanent Score Guarantee**: Points earned on open targets are **permanently kept**. When an opponent subsequently closes that target, the first player stops earning *new* points on it, but their previously scored points are **never** wiped out or reset to zero. Scores are only adjusted if **UNDO** is clicked.

### Closed-for-Game Rule
- A target becomes **closed for the game** when **both players have earned 3 or more marks on it**.
- Once closed for the game, neither player can score points on that number.
- If a player clicks on a target that has already been closed for the game:
  - The click does **not** count as a dart (turn darts do not increment).
  - No marks or scores are altered.
  - A red notification appears directly above UNDO and ENTER:
    > **"# is already closed, select UNDO or ENTER or another number to continue"**
  - Selecting **UNDO**, **ENTER**, or any unclosed target dismisses the message.

### Turn Entry & Controls
- Up to 3 darts may be recorded per turn. If a player attempts a 4th hit, the app prompts: `"3 dart hits recorded, click on UNDO or ENTER to continue"`.
- Use the **T** (Triple), **Target** (Single), and **D** (Double) buttons in each target row to record hits.
- **UNDO**: Reverts the last recorded hit and its associated points.
- **ENTER**: Finalizes the 3-dart turn and passes the turn to the next player.
- The alert line reserves spacing (`\u00A0`) so the UNDO and ENTER buttons remain large and never squish under the board.

---

## 3-Way Cricket (3 Players)

### Objective
A 3-player version of Cricket using the same targets (20, 19, 18, 17, 16, 15, and Bull). Players race to close all targets while accumulating the highest score.

### Rules & Mechanics
- **Marks & Closing**: Each player earns marks individually (1 = `/`, 2 = `X`, 3 = `⨷`). A target is closed for a player once they accumulate 3 marks.
- **Scoring Points (Exclusive Closer Rule)**:
  - **When a player has closed a number target, other players can NOT score on that same target**.
  - A player can only score points for additional marks beyond 3 if **no other player has closed that target** (both opponents have $< 3$ marks).
  - Once any opponent closes that target, no player can score further points on it.
  - Points once earned remain permanently in the player's total and are never wiped out or reduced when another player closes the target later.
- **Closed-for-Game & Dart Protection**:
  - A target is closed for scoring once another player has closed it. If a player already has 3 marks on a target and can no longer score points on it (or when all three players have closed it), clicking on that target does **not** count as a dart and displays:
    > **"# is already closed, select UNDO or ENTER or another number to continue"**
  - Any player who has not yet closed the target ($< 3$ marks) can still hit it to earn marks toward closing that target on their board.
- **Winning**: The game ends when all targets are closed by all players (or when the leader has closed all numbers with the highest score). The player with the highest total points wins.

---

## BowTie (1–15 Players)

### Objective
Navigate through a sequence of **12 specific target rounds**. Players aim to maximize their score while avoiding the **Halving Penalty**.

### The 12-Round Sequence
1. **Free**: Any dart that hits the board scores face value. If no dart hits a scoring segment, the player's score is halved.
2. **20**: Only hits on segment 20 (single, double, or treble) score points.
3. **19**: Only hits on segment 19 score points.
4. **Treble (T)**: Any treble segment scores points. The entered round total **must be divisible by 3**.
5. **18**: Only hits on segment 18 score points.
6. **17**: Only hits on segment 17 score points.
7. **Double (D)**: Any double segment scores points. The entered round total **must be divisible by 2**.
8. **16**: Only hits on segment 16 score points.
9. **15**: Only hits on segment 15 score points.
10. **3 Color**: A valid multi-color round score must be entered.
11. **BowTie (BT)**: Valid BowTie round hits score points.
12. **Bull (B)**: Single Bull scores 25 points; Double Bull scores 50 points.

### The Halving Penalty
- If a player fails to make a qualifying hit during a round (or scores 0 points), their accumulated score is **cut in half**.
- **Odd Number Adjustment**: If a player's score is an odd number when halved, it is rounded up before halving so the score remains an integer (for example, a score of `41` becomes `21`).

### Controls & Input
- **Active Round Indicator**: The current round is highlighted in red on the left-hand TARGETS list.
- **Target Quick-Add**: Clicking buttons 20–15 or Bull in the left targets list automatically appends the target value to the round input.
- **Score for Round Input**: Enter scores as total points (e.g. `60`), space/comma separated hits (`20 20 18`), or multiplication expressions (`20*3`).
- **Numeric Keypad**:
  - Standard 0–9 keypad with arithmetic operators (`+`, `×`).
  - Column 4 contains **Del** (Row 1), **CLEAR** (Row 2), and **UNDO** (Row 3).
  - Redundant UNDO buttons next to ENTER have been eliminated, providing a clean, full-width **ENTER** button.
- **Max Score Limit**: Scores $> 180$ are rejected with `"The max score is 180, please correct the score and try ENTER again"`.
- **Winning**: After all players have completed Round 12 (Bull), the player with the highest overall BowTie score is declared the winner.

---

## Shanghai (1–15 Players)

### Objective
Shanghai is a fast-paced dart game where players throw three darts per round at a single target number, moving sequentially from 1 through 10. You can win either by having the highest total score at the end of the final round, or by ending the game immediately with an instant-win "Shanghai" on any single turn.

### Setup & Objective
- **Players**: 1–15.
- **Targets**: Numbers 1 through 10, played in numerical order (Round 1 is 1s, Round 2 is 2s, up to Round 10).
- **Goal**: Score the most points by the end of the final round, or end the game immediately by hitting a Shanghai.

### Throw at the Target Number
On your turn, all three darts must be aimed at the active number for that round. Only darts that land in the active number count toward your score. Any darts hitting other numbers or missing the board score 0.

- **Single**: Face value of the number (e.g., Single 5 = 5 points).
- **Double**: 2× the number (e.g., Double 5 = 10 points).
- **Triple**: 3× the number (e.g., Triple 5 = 15 points).

Each scoring button (Single, Double, Triple) may be hit more than once per turn — for example, a player can record three Triples of the round number in a single three-dart turn.

### Instant Win ("Shanghai")
If a player hits a Single, a Double, and a Triple of the round's active number in a single three-dart turn (in any order), they immediately win the game — regardless of how far behind they are in points.

### Penalties (Zero-Score Turns)
If a player misses the target and scores 0 for the round:
- **Miss Target 3**: the player's score goes to zero.
- **Miss Target 5**: the player's score is cut in half (rounded up if odd before halving).
- **Miss Target 8**: the player is eliminated — skip this player for targets 9 and 10.

### Winning
- The game ends after Round 10; the surviving player with the highest total score wins.
- A Shanghai instant win ends the game immediately, no matter the scores.

---

## Keyboard & Input Shortcuts

- **Enter Key**: Submits the current turn in X01, Cricket, or BowTie.
- **Backspace**: Deletes the last character in the active input field.
- **Numbers (0–9)**: Enters values into the score expression or input box.
- **`+` / `*` / `x`**: Enters addition or multiplication into score calculations.
- **Touch / Mobile Optimization**: Interactive elements feature active press scaling (`transform: scale(0.95)`), `touch-action: manipulation` for rapid tap response, and zero browser overscroll.
