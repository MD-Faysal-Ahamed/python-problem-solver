# Python-Based Problem Solving Application

This is a simple Python application that solves math/logic problems entered by the user.  
It uses the `sympy` library to process and solve expressions.

## 🚀 How to Run

git clone https://github.com/Faysal/python-problem-solver.git
# Python-Based Problem Solving Application
# Author: Your Name
# Description: A simple problem solver that takes user input,
# validates it, processes the input, and returns a solution.

from sympy import sympify, solve, Symbol

# Function to get user input
def get_input():
    return input("Enter a math/logic problem (or type 'exit' to quit): ")

# Function to validate input
def validate_input(problem):
    try:
        sympify(problem)  # Check if input can be turned into a valid expression
        return True
    except:
        return False

# Function to process input and generate a solution
def process_input(problem):
    x = Symbol('x')
    try:
        expr = sympify(problem)
        solution = solve(expr, x)  # Solve for x
        return solution if solution else "No solution found"
    except:
        return "Error while solving"

# Function to display solution
def display_solution(solution):
    print("Solution:", solution)

# Main program flow
def main():
    print("=== Python-Based Problem Solving Application ===")
    while True:
        problem = get_input()

        # Exit condition
        if problem.lower() == "exit":
            print("Thank you for using the program. Goodbye!")
            break

        # Validate input
        if validate_input(problem):
            solution = process_input(problem)
            display_solution(solution)
        else:
            print("Invalid Input. Please try again.")

if __name__ == "__main__":
    main()

