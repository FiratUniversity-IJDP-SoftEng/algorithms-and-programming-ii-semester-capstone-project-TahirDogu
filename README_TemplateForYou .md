# Chess Queen Solver - Interactive Visualization

## Project Overview

This project is an interactive Streamlit web application that implements and visualizes the **N-Queens Problem** solution using a backtracking algorithm. It was developed as part of the Algorithms and Programming II course at Fırat University, Software Engineering Department.

## Algorithm Description

### Problem Definition

The N-Queens problem is a classic combinatorial problem: Place N chess queens on an N×N chessboard so that no two queens threaten each other. This means that no two queens share the same row, column, or diagonal.

### Mathematical Background

The solution requires understanding:
- Recursion and backtracking
- Matrix indexing
- Diagonal conflict checking (`row - col` and `row + col`)

### Algorithm Steps

1. Start with an empty board.
2. Try placing a queen in the first row.
3. Move to the next row and place a queen in a safe column.
4. If no safe column is found, backtrack to the previous row and move the queen.
5. Repeat until all queens are placed or all options are exhausted.

### Pseudocode

```
function solveNQueens(n):
    result = []
    board = [0] * n
    placeQueen(row=0, board, result)
    return result

function placeQueen(row, board, result):
    if row == n:
        result.append(copy of board)
        return
    for col in 0 to n-1:
        if isSafe(row, col, board):
            board[row] = col
            placeQueen(row + 1, board, result)

function isSafe(row, col, board):
    for i in 0 to row-1:
        if board[i] == col or
           abs(board[i] - col) == abs(i - row):
            return False
    return True
```

## Complexity Analysis

### Time Complexity

- **Best Case:** O(N!) – The algorithm explores each row and backtracks.
- **Average Case:** O(N!) – Similar to worst case in absence of heuristics.
- **Worst Case:** O(N!) – Exponential due to recursive backtracking.

### Space Complexity

- O(N²) – For storing the board and results.

## Features

- Interactive Streamlit interface to select board size
- Dynamic board generation and queen placement
- Visual demonstration of solution
- Step-by-step placement logging

## Screenshots

![Main Interface](https://private-user-images.githubusercontent.com/185914165/457661022-0250f421-6fe7-4fb0-a06c-ef61ff7dce6f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTA2MDgwNzgsIm5iZiI6MTc1MDYwNzc3OCwicGF0aCI6Ii8xODU5MTQxNjUvNDU3NjYxMDIyLTAyNTBmNDIxLTZmZTctNGZiMC1hMDZjLWVmNjFmZjdkY2U2Zi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNjIyJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDYyMlQxNTU2MThaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1iNWY3MzE5NTA2NGYzMGZmNzJhZDJjMTMyODYyZjc4MjE5NGZkMWRlNDg1YTlmZTVjODM0M2FjY2NhNTk4OGZhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.xzc-8fetc4hUJB3vj-3dXApdgCc7f-zTt2n3Kjrw-XY)


![Algorithm in Action](https://private-user-images.githubusercontent.com/185914165/457661166-05bfddce-4aee-46a0-ac75-208e67837ffa.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NTA2MDgwOTcsIm5iZiI6MTc1MDYwNzc5NywicGF0aCI6Ii8xODU5MTQxNjUvNDU3NjYxMTY2LTA1YmZkZGNlLTRhZWUtNDZhMC1hYzc1LTIwOGU2NzgzN2ZmYS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwNjIyJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDYyMlQxNTU2MzdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT03ODM5ZWFhMWRkZWIzZTk4Mjc3YTY1NDc2MGMzYjRlOTRlNzk1YjFjMjA4ODQwYTcxOThlYTY5NTY3Yzc0MjI3JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.ZW2SxtAc81vNcIMQjtCYJxt3E6dzdKnUHjGIwhuqsvA)
*Queens being placed on the board interactively*

## Installation

### Prerequisites

- Python 3.8 or higher
- Git

### Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/chess-queen-solver.git
   cd chess-queen-solver
   ```

2. Create a virtual environment:
   ```bash
   # On Windows
   python -m venv venv
   venv\Scripts\activate

   # On macOS/Linux
   python3 -m venv venv
   source venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the application:
   ```bash
   streamlit run main.py
   ```

## Usage Guide

1. Launch the app using `streamlit run main.py`
2. Use the sidebar slider to select the board size (e.g., N = 8)
3. Click "Solve" to visualize the solution
4. View the board updates and solution log

### Example Inputs

- N = 4 ➔ Output: 2 valid board configurations
- N = 8 ➔ Output: 92 valid configurations (only one visualized)
- N = 3 ➔ Output: No valid configuration

## Implementation Details

### Key Components

- `main.py`: Streamlit app and UI
- `queen_solver.py`: Core algorithm logic using backtracking
- `utils.py`: Board rendering and helper functions

### Code Highlights

```python
def solve_n_queens(n):
    solutions = []
    board = [-1] * n

    def is_safe(row, col):
        for i in range(row):
            if board[i] == col or \
               abs(board[i] - col) == abs(i - row):
                return False
        return True

    def place_queen(row):
        if row == n:
            solutions.append(board[:])
            return
        for col in range(n):
            if is_safe(row, col):
                board[row] = col
                place_queen(row + 1)

    place_queen(0)
    return solutions
```

## Testing

This project includes a test file for verifying the correctness of the algorithm.

```bash
python -m unittest test_queen_solver.py
```

### Test Cases

- Board size N=4: Verify that 2 valid configurations are found
- Board size N=1: Should return one configuration
- Board size N=3: Should return zero configurations

## Live Demo

A live demo of this application is available at: *[https://algorithms-and-programming-ii-semester-capstone-project-tahird.streamlit.app]*

## Limitations and Future Improvements

### Current Limitations

- Displays only the first found solution
- No animation of backtracking process
- Not optimized for very large N (>12)

### Planned Improvements

- Add animation to show recursive backtracking steps
- Show multiple or all valid configurations
- Add option to highlight conflict zones

## References and Resources

### Academic References

1. D.E. Knuth, *The Art of Computer Programming*
2. Sedgewick & Wayne, *Algorithms (Princeton)*

### Online Resources

- https://en.wikipedia.org/wiki/Eight_queens_puzzle
- https://www.geeksforgeeks.org/n-queen-problem-backtracking-3/
- https://streamlit.io/

## Author

- **Name:** Mehmet Tahir Dogu
- **Student ID:** [230543009]
- **GitHub:** [itahapinar]([https://github.com/itahapinar](https://github.com/TahirDogu))

## Acknowledgements

I would like to thank Assoc. Prof. Ferhat UÇAR for guidance throughout this project, and all classmates and contributors who shared insights.

---

*This project was developed as part of the Algorithms and Programming II course at Fırat University, Technology Faculty, Software Engineering Department.*

