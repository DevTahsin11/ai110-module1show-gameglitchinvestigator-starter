# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- **Describe the game's purpose.**  
  The game is a number guessing game built with Streamlit. Players select a difficulty level (Easy, Normal, Hard) which determines the range of numbers (e.g., 1-20 for Easy, 1-100 for Normal). The player has a limited number of attempts to guess the secret number, receiving hints like "Go HIGHER!" or "Go LOWER!" after each guess. The goal is to guess correctly within the attempt limit to win points, with scoring based on the number of attempts used.

-  **Detail which bugs you found.**  
  Flipped Hints Bug: The hint messages were incorrect. When the guess was too high, it displayed "📈 Go HIGHER!" (telling the player to guess higher when they should guess lower), and when too low, it displayed "📉 Go LOWER!" (telling them to guess lower when they should guess higher).  
  Mixed Logic and UI Code: The core game logic functions (`get_range_for_difficulty`, `parse_guess`, `check_guess`, `update_score`) were defined directly in `app.py`, mixing business logic with UI code, making it harder to test and maintain.  
  Test Failures: The existing tests in `test_game_logic.py` were expecting `check_guess` to return only the outcome string, but the function actually returns a tuple `(outcome, message)`, causing assertion errors.  
  Additional Issues Noted: There are FIXME comments indicating that the secret number doesn't regenerate when difficulty changes, the UI always shows a range of 1-100 regardless of difficulty, and values are sometimes compared as strings, but these were not fixed as part of the requested changes.

- **Explain what fixes you applied.** 
  - Fixed the Flipped Hints: Corrected the logic in `check_guess` to display the proper hints: "📉 Go LOWER!" for too high guesses and "📈 Go HIGHER!" for too low guesses. Removed unnecessary try-except block that was handling type errors.  
  - Refactored Logic Functions: Moved all core logic functions (`get_range_for_difficulty`, `parse_guess`, `check_guess`, `update_score`) from `app.py` to `logic_utils.py` to separate concerns. Updated imports in `app.py` to use these functions from the new module.  
  - Updated Tests: Modified the existing tests to properly unpack the tuple returned by `check_guess` and assert on the outcome. Added a new test `test_check_guess_messages` that specifically validates the hint messages to prevent regression of the flipped hints bug.  
  - Validation: Ran pytest to ensure all tests pass, and checked for syntax errors in the refactored code. Also tested the game itself to verify proper results.

## 📸 Demo

![alt text](<Screenshot 2026-03-23 at 2.30.11 AM.png>)

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
