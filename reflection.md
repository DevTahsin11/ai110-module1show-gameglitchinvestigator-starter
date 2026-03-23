# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

When I first started the game, it looked pretty normal and functioned normally at first until I noticed several different bugs and issues with the game once I started playing it further. Firstly, I noticed the "new game" button only worked at the very beginning and during the game however, it would not work and reset the game entirely after finishing the game despite if you win or not. I expected the "new game" button to ultimately reset the entire game and prompt the user to guess a new number at any point in playing the game when the user has pressed that button. Another bug that I have noticed is that the game incorrectly provides the wrong hint of the hidden number when the user inputs a number and is instead reversed and backwards, which I expected the hint for the inputted number to lead closer to the hidden number and not further away from it. Another bug that I have found is that, the range for "Normal" and "Hard" difficulty should be flipped and that the range for each difficulty is not shown on the screen (the screen stays stuck on the range being from 1-100), which I expected the range to change depending on the level of difficulty the user has selected and for the range of numbers to properly match each difficulty correctly.

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

I used Claude Code for this project and an example of where the AI suggestion was correct was when it found a specific error in regards to a specific kind of user input. It found an error where a certain variable was represented as the wrong data type which caused even number inputs to result in a TypeError issue and it suggested to remove the string conversion block and always pass that variable as a string. I verified this result by testing the app once again by using different kinds of even and odd numbers and I noticed that no errors arised anymore from this fix for this specific issue. An example of an AI suggestion that was a bit misleading was the tests that it created for the function "parse_guess" as it initially did not account properly for the even numbers being inputted. I checked this when I played the game and came across this issue that the AI suggestion failed to solve through this test from that exact function.

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I decided how a bug was really fixed through my gameplay of the app and seeing if there were any noticable bugs that arised from the changes that I have made. A test that I ran was about the numbers being inputted and seeing if the hints were accurate towards helping the user get closer to the secret number. Yes, AI did help me understand some of this tests by explaining what the tests they are suggesting and the reasoning behind the logic and functionality of them.

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
