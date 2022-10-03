---
title: SUDOKU SOLVER
tags: Recursion/Backtraking
expertise: intermediate to advanced 
---

Explain briefly what the snippet does.

- A sudoku is generally a 9 by 9 row column grid in which 9, 3 cross 3 sub grids are there. It has some properties associated with it.
- Each 3 cross 3 sub grid has exactly numbers from 1 to 9.
- Each horizontal row has exactly numbers from 1 to 9.
- Each vertical column has exactly numbers from 1 to 9.
- This program uses recursion and backtracking concept to solve partially filled sudoku and finds the correct fully filled sudoku.
- I hope this will be new for you. Just try it.

- Time complexity : O(N ^ (N ^ 2))
- Space complexity : SC : O(1) 


``` CPP

#include<bits/stdc++.h>
using namespace std

bool isValid(vector < vector < char >> & board, int row, int col, char c) {
  for (int i = 0; i < 9; i++) {
    if (board[i][col] == c)
      return false;

    if (board[row][i] == c)
      return false;

    if (board[3 * (row / 3) + i / 3][3 * (col / 3) + i % 3] == c)
      return false;
  }
  return true;
}

bool solveSudoku(vector < vector < char >> & board) {
  for (int i = 0; i < board.size(); i++) {
    for (int j = 0; j < board[0].size(); j++) {
      if (board[i][j] == '.') {
        for (char c = '1'; c <= '9'; c++) {
          if (isValid(board, i, j, c)) {
            board[i][j] = c;

            if (solveSudoku(board))
              return true;
            else
              board[i][j] = '.';
          }
        }

        return false;
      }
    }
  }
  return true;
}
int main() {
    vector<vector<char>>board{
        {'9', '5', '7', '.', '1', '3', '.', '8', '4'},
        {'4', '8', '3', '.', '5', '7', '1', '.', '6'},
        {'.', '1', '2', '.', '4', '9', '5', '3', '7'},
        {'1', '7', '.', '3', '.', '4', '9', '.', '2'},
        {'5', '.', '4', '9', '7', '.', '3', '6', '.'},
        {'3', '.', '9', '5', '.', '8', '7', '.', '1'},
        {'8', '4', '5', '7', '9', '.', '6', '1', '3'},
        {'.', '9', '1', '.', '3', '6', '.', '7', '5'},
        {'7', '.', '6', '1', '8', '5', '4', '.', '9'}
    };
   
    solveSudoku(board);
        	
    for(int i= 0; i< 9; i++){
        for(int j= 0; j< 9; j++)
            cout<<board[i][j]<<" ";
            cout<<"\n";
    }
    return 0;
}

```





