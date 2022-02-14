# calculatorTicTacToe
This is a tic tac toe game written for the Casio fx-6300 graphing calculator. It requires two player to play and is able to detect invalid input (e.g. a space that has already been taken or a space that does not exist), but is unable to tell if a player has won the game or not. It automatically ends tha game after 9 valid moves.

## Explanation of programs
Programs are functions that are callable from other programs, the fx-6300 supports up to 10 nested program calls.
The fx-6300 has 26 global general use registers named A through Z.
### Prog 0
Prog 0 is the main program of the game. It sets up the board in memory by zeroing A[0] through A[8] and drawing the tic tac toe grid on the screen. The main game loop consists of asking for user input, plotting 'X' or 'O' in the corresponding spot, and looping nine times.

### Prog 1
Prog 1 accepts one argument in the X register, and plots a vertical line from (X, -22) to (X, 0).

### Prog 2
Prog 2 draws the tic tac toe grid by plotting three horizontal lines using the Graph function and three vertical lines using Prog 1.

### Prog 3
Prog 3 gets input from the user and checks whether or not that number is in the range 0..=8 and that the spot on the board is not already taken. If the input is invalid it prompt that user for input again. Once it recieves valid input it plots 'X' or 'O' in the corresponding spot in the grid.

### Prog 4
Prog 4 accepts two arguments, the x position in the X register and the y position in the Y register. It then plots an 'X' centered at the given coordinates.

### Prog 5
Prog 5 accepts two arguments, the x position in the X register and the y position in the Y register. It then plots an 'O' centered at the given coordinates.

### Prog 6
Prog 6 accepts on argument in register J, then checks if spot J in the board is already taken. It sets register K to 1 if the position is not taken and sets register K to 0 otherwise.

# Formula Programming
According to [http://www.rskey.org/fx6300g](http://www.rskey.org/fx6300g), the fx-6300 has a formula programming model (I have no idea what formula programming means).

## Basic Syntax
I represents an integer<br>
F represents a float<br>
N represents a number (integer or float)<br>
V represents a variable<br>
G represents a number or variable or expression<br>

NOTE: this table is not exhaustive and only lists the symbols used in the tic tac toe program
| Symbol          | Usage           | Description                                                 |
|:----------------|:----------------|:------------------------------------------------------------|
|→                |G→V              |sets V to the value of G                                     |
|Lbl              |Lbl I            |defines a label referred to by the number I, where 0 ≤ I ≤ 9 |
|Goto             |Goto I           |jumps to label I, where 0 ≤ I ≤ 9                            |
|Graph Y=         |Graph Y=G        |graphs the equation Y=G                                      |
|Plot             |Plot G,G         |plots the point G,G                                          |
|=, <, >, ≤, ≥, ≠ |G operator G⇒G   |if the expression G operator G evaluates to true, the third argument is evaluated |
|Int              |Int G            |converts G into an integer                                   |
|Prog I           |Prog I           |performs a subroutine call to the program I, where 0 ≤ I ≤ 9 |
|?                |?→V              |prompts the user for input and restores the result in V      |
|Dsz              |Dsz V:G:G        |decrements variable V, if V is not zero evalute the first expression, if V is zero evaluate the second expression |

There are also basic arithmetic operators +, -, ×, ÷.
