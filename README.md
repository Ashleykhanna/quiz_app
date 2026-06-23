# quiz_app

A GUI-based True/False trivia quiz app built with Python and Tkinter. Questions are fetched live from the Open Trivia Database API, so you get a fresh set every time you play.

## Features

- Fetches 10 fresh True/False questions on every run via the Open Trivia DB API
- Graphical interface — no terminal interaction needed
- Live score tracking in the top-right corner
- Colour feedback (green / red) for 1 second after each answer
- Buttons disable automatically when the quiz ends
- HTML-encoded characters in questions are decoded properly (e.g. `&amp;` → `&`)

## Requirements

- Python 3.x
- `requests` library
- `tkinter` (included with most Python installations)

## Installation

```bash
pip install requests
```

> If you are using the included virtual environment (`quenv`), activate it first:
> ```bash
> source quenv/bin/activate
> ```

## How It Works

1. `data.py` calls the Open Trivia DB API and stores the results in `question_data`.
2. `main.py` converts each result into a `Question` object and builds a `question_bank` list.
3. A `QuizBrain` object manages which question is current and tracks the score.
4. A `QuizInterface` object builds the Tkinter window and drives the quiz by talking to `QuizBrain`.
