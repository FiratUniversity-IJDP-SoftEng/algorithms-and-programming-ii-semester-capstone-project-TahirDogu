Chess Queen Solver - Interactive Visualization
Project Overview
This project is an interactive Streamlit web application that implements and visualizes the N-Queens Problem solution using a backtracking algorithm. It was developed as part of the Algorithms and Programming II course at Fırat University, Software Engineering Department.

Algorithm Description
Problem Definition
The N-Queens problem is a classic combinatorial problem: Place N chess queens on an N×N chessboard so that no two queens threaten each other. This means that no two queens share the same row, column, or diagonal.

Mathematical Background
The solution requires understanding:

Recursion and backtracking

Matrix indexing

Diagonal conflict checking (row - col and row + col)

Algorithm Steps
Start with an empty board.

Try placing a queen in the first row.

Move to the next row and place a queen in a safe column.

If no safe column is found, backtrack to the previous row and move the queen.

Repeat until all queens are placed or all options are exhausted.

Pseudocode
sql
Kopyala
Düzenle
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
Complexity Analysis
Time Complexity
Best Case: O(N!) – The algorithm explores each row and backtracks.

Average Case: O(N!) – Similar to worst case in absence of heuristics.

Worst Case: O(N!) – Exponential due to recursive backtracking.

Space Complexity
O(N²) – For storing the board and results.

Features
Interactive Streamlit interface to select board size

Dynamic board generation and queen placement

Visual demonstration of solution

Step-by-step placement logging

Screenshots

Main interface where board size is selected


Queens being placed on the board interactively

Installation
Prerequisites
Python 3.8 or higher

Git

Setup Instructions
Clone the repository:

bash
Kopyala
Düzenle
git clone https://github.com/yourusername/chess-queen-solver.git
cd chess-queen-solver
Create a virtual environment:

bash
Kopyala
Düzenle
# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate
Install dependencies:

bash
Kopyala
Düzenle
pip install -r requirements.txt
Run the application:

bash
Kopyala
Düzenle
streamlit run main.py
Usage Guide
Launch the app using streamlit run main.py

Use the sidebar slider to select the board size (e.g., N = 8)

Click "Solve" to visualize the solution

View the board updates and solution log

Example Inputs
N = 4 ➝ Output: 2 valid board configurations

N = 8 ➝ Output: 92 valid configurations (only one visualized)

N = 3 ➝ Output: No valid configuration

Implementation Details
Key Components
main.py: Streamlit app and UI

queen_solver.py: Core algorithm logic using backtracking

utils.py: Board rendering and helper functions

Code Highlights
python
Kopyala
Düzenle
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
Testing
This project includes a test file for verifying the correctness of the algorithm.

bash
Kopyala
Düzenle
python -m unittest test_queen_solver.py
Test Cases
Board size N=4: Verify that 2 valid configurations are found

Board size N=1: Should return one configuration

Board size N=3: Should return zero configurations

Live Demo
A live demo of this application is available at: [Insert Streamlit Cloud URL here]

Limitations and Future Improvements
Current Limitations
Displays only the first found solution

No animation of backtracking process

Not optimized for very large N (>12)

Planned Improvements
Add animation to show recursive backtracking steps

Show multiple or all valid configurations

Add option to highlight conflict zones

References and Resources
Academic References
D.E. Knuth, The Art of Computer Programming

Sedgewick & Wayne, Algorithms (Princeton)

Online Resources
https://en.wikipedia.org/wiki/Eight_queens_puzzle

https://www.geeksforgeeks.org/n-queen-problem-backtracking-3/

https://streamlit.io/

Author
Name: İbrahim Taha Pınar

Student ID: [Your Student ID]

GitHub: itahapinar

Acknowledgements
I would like to thank Assoc. Prof. Ferhat UÇAR for guidance throughout this project, and all classmates and contributors who shared insights.

This project was developed as part of the Algorithms and Programming II course at Fırat University, Technology Faculty, Software Engineering Department. 
