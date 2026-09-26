# Visual Sudoku Solver

This project is meant to visualize the process of solving a Sudoku puzzle as a constraint satisfaction problem (CSP). It allows the user to follow step-by-step while backtracking and optional improvements, such as forward checking and arc consistency, are applied to the search. The user can also select two ordering improvements—minimum remaining values (MRV) and least constraining value (LSV)—to see how they affect the search.

The interface allows the user to select a Sudoku puzzle from a list of preloaded puzzles, generate a random puzzle, or to input their own puzzle. The user can also select which improvements to apply to the search, and can step through the search process one step at a time, or run the search to completion. 

During the search, each state being expanded is shown (at a rate dictated by a slider on the side, which indicate the number of seconds to display each state being expanded) and below, each candidate successor, with  those that pass the constraint checks that will be added to the fringe being highlighted and those that don't being dimmed. The state of the puzzle as well as the domains of each cell are displayed (if forward search or arc consistency is being used). A miniature search tree is displayed next to the expanded state/successors showing roughly where the current state is and how the search is progressing.

The user can choose to step through each step of the algorithm manually, run it automatically (displaying each expanded state for a given number of seconds), or run it to completion (displaying only the final solution). In addition, the user can choose to visualize the individual steps of the improvements (forward checking, arc consistency, MRV, and LSV) as they are applied during the expansion phase in the same manner (manually, automatically, or to completion).


## Implementation

The entire app is in a self-contained HTML file, with the JavaScript and CSS embedded in the HTML (no internet connection required). The app uses a simple backtracking search algorithm to solve the Sudoku puzzle, with optional improvements for forward checking and arc consistency. The search tree is displayed using a simple tree visualization library. 

## Saving

The initial puzzle can be saved as a PNG or text file (using the numbers 1—9 and spaces, with each row on a new line). The user can also upload a puzzle as a text file. The starting state may also be saved or loaded from localStorage. The user can also elect to make a link to the current puzzle, which simply encodes the starting state in the URL. 

Search runs are saved to localStorage, including the initial puzzle, the settings, the intermediate state being viewed, and the outcome (both the graphic showing the explored states and solution path, as well as the corresponding states). These saved runs can then be loaded and used to jump start a new version with different settings or a different puzzle. THe user can also elect to make a link to the current run, which encodes the initial puzzle, settings, and the current state in the URL.