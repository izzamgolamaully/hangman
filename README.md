# hangman

A command-line Hangman game built in Python.

## How to play
1. Run `python hangman.py` (or execute the Jupyter notebook cell)
2. The game picks a secret word — you see blanks for each letter
3. Guess one letter at a time
4. You have 6 wrong guesses before you're hanged
5. Win by revealing all letters before you run out of lives

## Requirements
- Python 3.x (no external libraries needed)

## Features
- ASCII gallows that builds up with each wrong guess
- Input validation (single letters only, no repeats)
- Session statistics: wins, losses, win rate, average guesses
- Play multiple rounds in one session
