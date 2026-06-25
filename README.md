# Sudoku Game

A full-stack Sudoku game application built with HTML, CSS, JavaScript (frontend), Node.js/Express (backend), and Java utilities.

## Features

- **Interactive Sudoku Board**: 9x9 grid with real-time validation
- **Game Modes**: Easy, Medium, and Hard difficulty levels
- **Functionality**:
  - Generate new puzzles
  - Auto-solve feature
  - Check solution validation
  - Reset puzzle to original state
  - Timer to track gameplay
  - Visual highlighting of related cells

## Project Structure

```
suduko game/
├── public/                 # Frontend files
│   ├── index.html         # Main game interface
│   ├── style.css          # Game styling
│   └── script.js          # Client-side game logic
├── server/                # Backend files
│   ├── server.js          # Express server
│   └── sudokuLogic.js     # Game logic (solve, validate, generate)
├── java/                  # Java utilities
│   ├── SudokuSolver.java  # Advanced Sudoku solver
│   └── SudokuGenerator.java # Puzzle generator
├── package.json           # Node.js dependencies
└── README.md             # This file
```

## Installation

### Prerequisites
- Node.js (v14 or higher)
- npm (comes with Node.js)
- Java JDK (optional, for Java components)

### Setup

1. **Navigate to the project directory**:
   ```bash
   cd "Desktop/react projects/suduko game"
   ```

2. **Install Node.js dependencies**:
   ```bash
   npm install
   ```

3. **Start the server**:
   ```bash
   npm start
   ```

   The game will be available at `http://localhost:3000`

### Development Mode

To run with automatic restart on file changes:
```bash
npm install nodemon --save-dev
npm run dev
```

## API Endpoints

### GET `/api/generate`
Generates a new Sudoku puzzle.

**Query Parameters**:
- `difficulty` (optional): `easy`, `medium`, or `hard` (default: `medium`)

**Response**:
```json
{
  "board": [[...]], 
  "solution": [[...]],
  "difficulty": "medium"
}
```

### POST `/api/solve`
Solves a given Sudoku puzzle.

**Body**:
```json
{
  "board": [[...]]
}
```

**Response**:
```json
{
  "solution": [[...]]
}
```

### POST `/api/check`
Validates if the current board is a correct solution.

**Body**:
```json
{
  "board": [[...]]
}
```

**Response**:
```json
{
  "isValid": true/false
}
```

### POST `/api/hint`
Provides a hint for the current puzzle.

**Body**:
```json
{
  "board": [[...]]
}
```

**Response**:
```json
{
  "hint": {
    "row": 0,
    "col": 1,
    "value": 5
  }
}
```

## How to Play

1. **New Game**: Click "New Game" to start a fresh puzzle
2. **Fill Numbers**: Click on empty cells and type a number (1-9)
3. **Get Help**: 
   - Use "Solve" to see the solution
   - Use "Hint" to get a suggestion
4. **Check Progress**: Click "Check Solution" to validate your answers
5. **Reset**: Use "Reset" to start the puzzle over

## Highlighting Features

- **Yellow**: Currently selected cell
- **Light Green**: Cells in the same row, column, or 3x3 box
- **Light Red**: Invalid entries
- **Light Blue**: Given numbers (read-only)

## Java Components

### Compiling Java Files

```bash
# Navigate to java directory
cd java

# Compile
javac SudokuSolver.java
javac SudokuGenerator.java

# Run (optional - for testing)
java SudokuSolver
java SudokuGenerator
```

### SudokuSolver.java
- Advanced Sudoku solver using backtracking
- Validates board state
- Provides candidate numbers for each cell

### SudokuGenerator.java
- Generates complete Sudoku solutions
- Creates puzzles with varying difficulty levels
- 1-5 difficulty scale

## Technology Stack

### Frontend
- HTML5
- CSS3 (with gradients and animations)
- Vanilla JavaScript (ES6+)

### Backend
- Node.js
- Express.js
- CORS support

### Utilities
- Java (optional, for advanced solving)

## Performance

- **Board Generation**: ~100-500ms depending on difficulty
- **Solution Validation**: ~50-100ms
- **Auto-solve**: ~500ms-2s for complex puzzles
- **Supports**: Unlimited concurrent games

## Troubleshooting

### Port Already in Use
If port 3000 is busy, use:
```bash
PORT=3001 npm start
```

### Module Not Found Error
Make sure dependencies are installed:
```bash
npm install
```

### Java Compilation Issues
Ensure Java JDK is installed and added to PATH:
```bash
java -version
javac -version
```

## Browser Compatibility

- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Future Enhancements

- [ ] Multiplayer mode
- [ ] Leaderboard
- [ ] Statistics tracking
- [ ] Dark mode
- [ ] Mobile app version
- [ ] Database for puzzle storage
- [ ] User accounts and progress saving
- [ ] Multiple game boards simultaneously

## License

MIT

## Author

Sudoku Game Project

---

**Enjoy solving Sudoku puzzles! 🧩**
