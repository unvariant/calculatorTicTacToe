# calculatorTicTacToe
This is a tic tac toe game written for the Casio fx-6300 graphing calculator. It requires two player to play and is able to detect invalid input (e.g. a space that has already been taken or a space that does not exist), but is unable to tell if a player has won the game or not. It automatically ends tha game after 9 valid moves.

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
|?                |?→V              |prompts the user for input and restores the result in variable V |
|Dsz              |Dsz V:G:G        |decrements variable V, if V is not zero evalutes the first expression, if V is zero evaluates the second expression |

there are also basic arithmetic operators +, -, ×, ÷.
