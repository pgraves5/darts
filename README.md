# Darts Games App

A responsive browser-based darts scoreboard for X01, Standard Cricket, 3-Way Cricket, and BowTie. Open `index2.html` in a browser to use it.

## Starting a Match

1. Select a game mode.
2. Select the number of players.
3. Enter player names:
   - X01 and BowTie support the configured player limits.
   - Standard Cricket supports 2 players.
   - 3-Way Cricket supports 3 players.
   - BowTie player names are limited to 5 characters.
4. Select **START MATCH**.

Use **New Match** to return to setup or **Menu** to leave the live scoreboard.

## X01 Games

Available X01 games: 601, 501, 401, 301, 201, and 101.

### Objective

Each player starts with the selected score. Players alternate turns and subtract their turn score until they reach exactly zero.

### Rules

- X01 supports 1–4 players.
- 601, 501, 401, and 301 default to 2 players.
- 201 and 101 default to 1 player.
- A turn consists of up to three darts.
- Enter a turn as a score or a calculation using `+` and `*`, for example `60+40+20` or `20*3`.
- A score that leaves the player at 1 or below 0 is a bust. The turn scores zero and the player stays at the score from the start of the turn.
- The final dart must finish on a double or the Bull, with Bull counting as 50 and the outer Bull counting as 25.
- The app provides 2-dart and 3-dart checkout suggestions.

## Standard Cricket

Standard Cricket is for 2 players.

### Objectives and Targets

The targets are 20, 19, 18, 17, 16, 15, and Bull.

- Single hit: 1 mark
- Double hit: 2 marks
- Treble hit: 3 marks

A player closes a target after earning 3 marks.

### Scoring

- Hit a closed target for points after the opponent has not closed it.
- 20–15 score their own value per extra hit.
- Bull scores 25 per hit.
- A target is not worth points once both players have closed it.

The turn advances through the **ENTER** control. **UNDO** rolls back the previous action.

## 3-Way Cricket

3-Way Cricket uses the same targets and closing system as Standard Cricket, but allows 3 players.

### Rules

- Each player can close targets by earning 3 marks.
- When a player scores extra marks on an open target, those marks produce points.
- Opponents score normally only when they have not closed the target.
- Extra marks on Bull count as 25 points per mark.
- The player with the highest score after the game is complete wins.

Use the target and T/D controls in the cricket tracking board to enter marks.

## BowTie

BowTie supports 1–15 players and uses a 12-round target sequence.

### Round Sequence

1. Free
2. 20
3. 19
4. Treble
5. 18
6. 17
7. Double
8. 16
9. 15
10. 3 Color
11. BowTie
12. Bull

### Turn Entry

- The active player is shown in red.
- The target round is highlighted in red in the target list.
- Enter scores in the **Score for round** field.
- The 20–15 and Bull targets add values to the field when selected.
- Select **ENTER** to submit the player's 3-dart turn.
- Select **CLEAR** to clear the entered round.
- Select **UNDO** to restore the previous completed turn.

### Scoring Rules

- **Free:** Any hits score. If no dart scores, halve the player's score.
- **20 / 19 / 18 / 17 / 16 / 15:** Only hits on the displayed target count. If no required hit is made, halve the player's score.
- **Treble:** Entered round total must be divisible by 3. Otherwise, halve the player's score.
- **Double:** Entered round total must be divisible by 2. Otherwise, halve the player's score.
- **3 Color:** Enter the score for the round. A valid positive total is added; a zero/empty round causes halving.
- **BowTie:** Enter the score for the round. A valid positive total is added; a zero/empty round causes halving.
- **Bull:** Outer Bull is 25 and inner Bull is 50. If no Bull is hit, halve the player's score.

### Halving Penalty

If a player misses the round requirement, their current total is cut in half:

- Odd totals are adjusted before halving so the result remains a whole number.
- For example, 41 becomes 21.

### Winning

Each player completes every round. After the final Bull round, the player with the highest BowTie score wins.
