# 🎯 TargetScore

A single-screen Android app, built with **MIT App Inventor**, that challenges players to guess a randomly generated number — with instant colour-coded feedback and a restart option.

## How it works

1. The app picks a random secret number between **1 and 30** when it loads
2. Type your guess into the input box
3. Tap **Guess** to check your answer
4. Get instant feedback — told whether your guess is too high, too low, or spot on
5. Tap **Restart** to generate a new secret number and play again

## Features

- 🔢 Random target number generated between 1–30
- ✅ Correct-guess detection with a personalised success message
- ⬆️⬇️ Higher/lower hints when the guess is wrong
- 🟢🔴 Colour-coded feedback text — green for correct, red for incorrect
- 🔁 One-tap **Restart** to reset the number and clear feedback
- 🖥️ Simple single-screen UI — just a text box and two buttons

## Tech Stack

- **Platform:** MIT App Inventor (block-based, no native code)
- **Components:** `Guess_box` (TextBox), `Guess_button`, `Restart_button`, `Right_or_wrong` (Label)
- **Variables:** `global num` — stores the current secret number
- **Logic:** Nested `if/then/else` blocks comparing `Guess_box.Text` to `global num`

## How the Blocks Work

| Event | Action |
|---|---|
| `initialize global num` | Sets the starting secret number to `random integer from 1 to 30` |
| `Guess_button.Click` | Compares `Guess_box.Text` to `global num` |
| ↳ if equal | Sets `Right_or_wrong.Text` to "Correct!... My Number was `[num]`" and `TextColor` to green |
| ↳ if less than `global num` | Sets `Right_or_wrong.Text` to "Wrong!..... My Number is higher...." |
| ↳ else | Sets `Right_or_wrong.Text` to "Wrong!..... My Number is lower...." |
| (wrong branch) | Sets `Right_or_wrong.TextColor` to red |
| `Restart_button.Click` | Re-randomizes `global num` (1–30) and clears `Right_or_wrong.Text` |

## Example

| Action              | Result                                  |
|---------------------|-------------------------------------------|
| Guess `15`, secret is `22` | "Wrong!..... My Number is higher...." (red) |
| Guess `28`, secret is `22` | "Wrong!..... My Number is lower...." (red)  |
| Guess `22`, secret is `22` | "Correct!... My Number was 22" (green)      |
| Tap Restart          | New secret number chosen, feedback cleared |

## Screenshot



![App Screenshot](screenshot.png)



*The app in action — guessing the number with colour-coded feedback.*

## Limitations (v1.0)

- No input validation — non-numeric guesses aren't handled
- No attempt counter or scoring system
- Fixed range of 1–30 — not configurable in-app
- No difficulty levels

## Future Improvements

- Add input validation for non-numeric entries
- Track and display number of attempts / a score
- Add adjustable difficulty (range, number of guesses allowed)
- Add a "Play Again" confirmation dialog
- Add sound effects for correct/incorrect guesses

---
