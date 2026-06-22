# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

When I first ran the game it looked polished but the logic was off. The hints were backwards — guessing a very low number like -100 still said "Go LOWER!" instead of "Go HIGHER." The New Game button didn't reset the game. The score also went negative which didn't seem right for a guessing game.

**Bug Reproduction Log**

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| Guessed -100 (secret was 47) | "Go HIGHER" hint | "Go LOWER!" shown | none |
| Played several rounds | Score stays positive | Score went to -20 | none |
| Clicked "New Game" button | Game resets with new number | Nothing happened | none |
| Played 8 attempts, all wrong guesses | Score stays at 0 or positive | Score went to -25 | none |

---

## 2. How did you use AI as a teammate?

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?

I used Claude Code inside VS Code as my main AI coding assistant. I attached app.py and logic_utils.py to give it context about my project, then described the bug I observed and asked it to explain the cause.

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).

Claude Code correctly identified that the hint messages in app.py lines 32-47 were swapped — "Go HIGHER" was returned when the guess was too high, and "Go LOWER" was returned when the guess was too low. I verified this by reading the code myself and confirming the conditions matched exactly what Claude described.

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

Claude noted that logic_utils.py had an unimplemented stub where check_guess raises NotImplementedError, meaning the actual game logic runs from app.py instead. I hadn't noticed that both files had a function with the same name, so I had to read both files carefully to verify this was true before trusting Claude's explanation.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
