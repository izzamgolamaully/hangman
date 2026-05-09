# Hangman

A command-line Hangman game built in Python as part of my first Python project.
The player guesses a hidden word one letter at a time, with a maximum of 6 wrong
guesses before the game ends. Session statistics are tracked across multiple rounds.

---

## How to run

You can run the game in two ways:

**Option 1 — Jupyter Notebook**
Open the `.ipynb` file in JupyterLab, VS Code, or classic Jupyter Notebook
and run the code cell. The game will run in the output below the cell.

**Option 2 — Python script**
If you have saved the code as a `.py` file, open a terminal and run:

```
python hangman.py
```

No installation required. The only module used is `random`, which is built
into Python and does not need to be installed separately.

---

## Requirements

- Python 3.x
- No external libraries needed

---

## How to play

1. Run the program — a secret word is chosen automatically and you are shown
   how many letters it contains
2. Type a single letter and press Enter
3. If the letter is in the word, it is revealed in the correct position(s)
4. If the letter is not in the word, a wrong guess is recorded and the next
   stage of the gallows is drawn
5. You have **6 wrong guesses** before the game ends in a loss
6. Win by revealing every letter in the word before running out of lives
7. At the end of each round you can choose to play again or quit
8. When you quit, your stats for the full session are displayed

---

## Example gameplay

```
-----------------------------------
New game! The word has 9 letters.
-----------------------------------

  +---+
  |   |
      |
      |
      |
      |
=========

Word:   _ _ _ _ _ _ _ _ _
Wrong:  none so far
Lives:  6 left

Guess a letter: p
Yes! 'p' is in the word.

  +---+
  |   |
      |
      |
      |
      |
=========

Word:   _ _ _ _ _ _ _ _ _   (p revealed in its position)
Wrong:  none so far
Lives:  6 left
```

---

## Project structure

```
├── Python_04_01_Project_PythonGameDevelopment_v2.ipynb   # main notebook
└── README.md                                              # this file
```

---

## Functions overview

| Function | Purpose |
|---|---|
| `choose_word()` | Picks a random word from the word bank |
| `get_display()` | Builds the blanks string shown to the player |
| `get_valid_guess()` | Validates player input — rejects repeats, numbers, symbols |
| `display_state()` | Prints the gallows, blanks, wrong letters, and lives remaining |
| `play_round()` | Runs one complete game and updates global stats |
| `show_stats()` | Displays session stats when the player quits |
| `main()` | Entry point — welcome message and play-again loop |

---

## Global variables

| Variable | Type | Purpose |
|---|---|---|
| `total_games` | int | Total rounds completed |
| `total_wins` | int | Total rounds won |
| `total_losses` | int | Total rounds lost |
| `total_guesses` | int | Total guesses across all rounds |
| `MAX_WRONG` | int | Maximum wrong guesses allowed (set to 6) |

---

## Input validation

The game handles bad input without crashing. The following are all caught
and the player is asked to try again:

- Entering more than one character
- Entering a number or symbol
- Pressing enter with no input
- Guessing a letter that has already been tried this round

Inputs are automatically converted to lowercase so capitalisation does not matter.

---

## Session stats

At the end of a session the game shows:

- Total games played
- Total wins and losses
- Win rate as a percentage
- Average number of guesses per game

---

## Word bank

The game includes 15 words, all related to programming and computer science.
The word is chosen randomly at the start of each round with an equal chance
of any word being selected. The word bank can easily be extended by adding
strings to the `WORD_BANK` list at the top of the code.

---

## Known limitations

- The word bank is hardcoded — words cannot be added without editing the source
- Stats are not saved between sessions; closing the program resets everything
- There is no difficulty setting — all words are treated the same regardless of length

---

## Potential improvements

- Load words from an external text file for a much larger word bank
- Add difficulty levels based on word length or category
- Save stats to a file so they persist between sessions
- Add a hint system that reveals a letter at the cost of one life
- Build a GUI version using Tkinter
```

