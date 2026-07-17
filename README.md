# Quiz CLI

An interactive command-line quiz game for learning JavaScript concepts.

## Features

- Category-based quizzes
- Multiple choice questions
- Progress tracking during each quiz
- Score summary at the end
- Explanations for incorrect answers
- Option to play again without restarting the app

## Requirements

- Node.js 18 or newer

## Getting Started

### Install dependencies

```bash
npm install
```

### Run the quiz

```bash
npm start
```

## Project Structure

- `index.js` - Application entry point
- `src/quiz.js` - Quiz game logic
- `src/input.js` - Command-line input helpers
- `src/colors.js` - Terminal color utilities
- `data/questions.json` - Quiz questions and categories

## How It Works

1. Choose a quiz category.
2. Select how many questions you want to answer.
3. Answer each multiple-choice question from the terminal.
4. Review your score and incorrect answers.
5. Decide whether to play another round.

## Scripts

- `npm start` - Start the quiz application
- `npm test` - Run the test suite

## Notes

This project is designed as a small educational CLI example and demonstrates modern JavaScript features such as ES modules, async/await, and basic object-oriented design.