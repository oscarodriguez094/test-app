# quiz-cli

Interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts.

## Overview

**quiz-cli** is a terminal-based quiz application built with Node.js and native ES Modules. It loads quiz questions from a JSON file, lets you choose a category and question count, and then walks you through a multiple-choice quiz with progress tracking, instant feedback, explanations, and a final score summary.

The project is intentionally lightweight: it uses only Node.js built-in modules, custom terminal colors via ANSI escape codes, and a small set of files that demonstrate practical concepts such as async/await, file reading, user input handling, class-based game logic, and simple CLI UX.

## Features

- Interactive CLI with menu-driven navigation
- Multiple quiz categories:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Choice of question count per round
- Shuffled questions for each game session
- Immediate correctness feedback
- Explanations shown after each answer
- Final score summary with performance message
- Review of incorrect answers at the end
- No external runtime dependencies

## Tech Stack

- **Runtime:** Node.js `>=18.0.0`
- **Language:** JavaScript (ES Modules)
- **Standard libraries used:**
  - `node:fs/promises`
  - `node:path`
  - `node:url`
  - `node:readline`
- **Package manager:** npm

## Repository Structure

```text
.
├── README.md
├── package.json
├── index.js
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### Important files

- `index.js` — application entry point; loads questions and runs the main quiz loop
- `data/questions.json` — quiz content organized by category
- `src/quiz.js` — quiz engine: shuffling, scoring, progress, and results
- `src/input.js` — readline-based input helpers
- `src/colors.js` — ANSI terminal color helpers

## Prerequisites

- Node.js 18 or newer
- npm (bundled with Node.js)

## Getting Started

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd test-app
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

   > This project does not declare external dependencies, but running `npm install` will create a lockfile if needed and prepares the workspace in a standard Node.js workflow.

3. Start the quiz:

   ```bash
   npm start
   ```

## Running the Project

### Development / local run

```bash
npm start
```

This executes:

```bash
node index.js
```

### Direct execution

Because `index.js` includes a shebang, you can also run it directly in a Unix-like shell after making it executable:

```bash
./index.js
```

## Usage

When the app starts, it will:

1. Display a welcome banner
2. Ask you to choose a category
3. Ask how many questions you want to answer
4. Present questions one by one with numbered options
5. Show whether each answer was correct or incorrect
6. Display explanations when available
7. Show your final score and a performance message
8. Offer to play again

### Example flow

```text
Choose a category:
  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

How many questions?
  1. All questions
  2. 3 questions
  3. 5 questions
```

For each question, enter the number of the answer you want to select.

## Testing & Quality

The project includes a test script in `package.json`:

```bash
npm test
```

This runs Node's built-in test runner:

```bash
node --test
```

**Note:** No test files are present in the repository at the moment, so the test command may not execute any tests until they are added.

There are currently no lint or format scripts defined in `package.json`.

## Configuration Reference

This project does not use environment variables or external config files.

### Data file

- `data/questions.json` — contains all quiz categories and questions

#### Data structure

```json
{
  "categories": {
    "category-id": {
      "name": "Display Name",
      "questions": [
        {
          "question": "Question text",
          "options": ["Option 1", "Option 2", "Option 3", "Option 4"],
          "answer": 0,
          "explanation": "Optional explanation"
        }
      ]
    }
  }
}
```

## Deployment

This project is a local terminal application and does not include Docker, Kubernetes, serverless, or cloud deployment files.

To distribute or run it elsewhere:

- ensure Node.js 18+ is installed
- copy the repository contents
- run `npm start`

## Troubleshooting

### The app exits with a file read error

- Confirm `data/questions.json` exists
- Run the app from the repository root so relative paths resolve correctly

### Invalid menu selection keeps repeating

- Enter the number shown in the menu, not the text of the answer
- If the prompt does not accept input, check that your terminal is attached to stdin/stdout

### Colors do not appear correctly

- Some terminals have limited ANSI support
- Try using a modern terminal emulator

## Contributing

1. Create a feature branch
2. Make your changes
3. Update or add tests if applicable
4. Run `npm test`
5. Open a pull request

### Code style notes

- The codebase uses modern JavaScript ES Modules
- Built-in Node APIs are preferred over external packages
- Source files are organized under `src/`

## License

- License declared in `package.json`: **MIT**
- `LICENSE` file: **not found** in the repository

## Documentation Confidence

High confidence for the commands, structure, and behavior documented here because they were verified from:

- `package.json`
- `index.js`
- `src/quiz.js`
- `src/input.js`
- `src/colors.js`
- `data/questions.json`

Unknowns / assumptions:

- No `LICENSE` file was present, so license text could not be linked
- No test files were found, so `npm test` is documented as configured but not currently backed by visible test cases
- No Docker, CI, or deployment configuration files were present in the repository