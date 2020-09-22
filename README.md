<div align="center">

## Basic TicTacToe


</div>

### Description

Just another simple TicTacToe Game
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Dan R](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/dan-r.md)
**Level**          |Beginner
**User Rating**    |4.0 (20 globes from 5 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Games](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/games__3-13.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/dan-r-basic-tictactoe__3-10094/archive/master.zip)





### Source Code

```
//Program: Basic TicTacToe
//Author: Dan R (NoName)
//Date: 12/07/2005
#include <iostream>
using namespace::std;
#include <stdlib.h>
void displayBoard();
bool checkWin();
void move(bool);
bool isLegal(int);
char board[9] = {'1','2','3','4','5','6','7','8','9'};
void main()
{
	bool player = false; // true = X false = O
	displayBoard();
	while(!checkWin())
	{
		if(player == true)
			player = false;
		else
			player = true;
		move(player);
	}
	if(player == true)
		cout << "Player 1 WINS" << endl;
	else
		cout << "Player 2 WINS" << endl;
}
void displayBoard()
{
	system("cls");
	cout << "\n " << board[0] << " | " << board[1] << " | " << board[2] << endl
		 << " ---------" << endl
		 << " " << board[3] << " | " << board[4] << " | " << board[5] << endl
		 << " ---------" << endl
		 << " " << board[6] << " | " << board[7] << " | " << board[8] << endl;
}
bool checkWin()
{
	if(board[0] == board[1] && board[2] == board[0] )
		return true;
	else if(board[3] == board[4] && board[5] == board[3])
		return true;
	else if(board[6] == board[7] && board[8] == board[6])
		return true;
	else if(board[0] == board[3] && board[6] == board[0])
		return true;
	else if(board[1] == board[4] && board[7] == board[1])
		return true;
	else if(board[2] == board[5] && board[8] == board[2])
		return true;
	else if(board[0] == board[4] && board[8] == board[0])
		return true;
	else if(board[2] == board[4] && board[6] == board[2])
		return true;
	else
		return false;
}
void move(bool who)
{
	int spot;
	if(who == true)
		cout << "\nEnter your move Player 1: ";
	else
		cout << "\nEnter your move Player 2: ";
	cin >> spot;
	if(isLegal(spot))
	{
		if(who == true)
			board[spot-1] = 'X';
		else
			board[spot-1] = 'O';
	}
	else
		move(who);
	displayBoard();
}
bool isLegal(int spot)
{
	if(board[spot-1] == 'X' || board[spot-1] == 'O')
		return false;
	else
		return true;
}
```

