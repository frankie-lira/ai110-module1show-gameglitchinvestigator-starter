# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable.

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the app: `streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the bugs.** Notice when hints don't make sense, the score goes negative, or the New Game button doesn't work.
3. **Fix the Logic.** Use an AI coding assistant to identify and repair the bugs.
4. **Refactor & Test.** Move the logic into `logic_utils.py` and run `pytest` to verify your fixes.

## 📝 Document Your Experience

- Investigated a broken AI-generated number guessing game built with Streamlit
- Found 3 bugs: backwards hint messages, negative score, and broken New Game button
- Fixed hints by moving check_guess into logic_utils.py with correct logic
- Fixed score by adding a max(0, ...) floor to prevent negative values
- Verified fixes with pytest and manual playtesting

## 📸 Demo Walkthrough

1. User starts the game on Normal difficulty (range 1-100, 8 attempts)
2. User enters a guess of 40 — secret is 21 — game returns "Go LOWER!"
3. User enters a guess of 20 — game returns "Go HIGHER!"
4. User enters a guess of 21 — game returns "🎉 Correct!"
5. Score updates to 30 and game displays "You won! The secret was 21."

## 🧪 Test Results
tests/test_game_logic.py::test_winning_guess PASSED                [ 33%]
tests/test_game_logic.py::test_guess_too_high PASSED               [ 66%]
tests/test_game_logic.py::test_guess_too_low PASSED                [100%]

======================================== 3 passed in 0.01s ========================================