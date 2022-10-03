---
title: Matrix Multiplication
tags: matrix
expertise: beginner
---

Explain briefly what the snippet does.

- C programming language supports matrix as a data type and offers more flexibility. And also it consumes less memory while processing.
- By storing values in a matrix rather than as individual variables, C program can access and perform operations on the data more efficiently.
- It is easier to extract information about object rotation, and also easy to manipulate in the C program. 

```cpp
include<iostream> 
using namespace std;
int main()
{
    int a[10][10], b[10][10], mul[10][10], m, c, p, j, k;
    cout << " Enter the number of printing the rows=";
    cin >> m;
    cout << "Enter the number of printing the column=";
    cin >> c;
    cout << "Enter the first matrix of element=\n";
    for (p = 0; p < m; p++)
    {
        for (j = 0; j < c; j++)
        {
            cin >> a[p][j];
        }
    }
    cout << "Enter the second matrix of element=\n";
    for (p = 0; p < m; p++)
    {
        for (j = 0; j < c; j++)
        {
            cin >> b[p][j];
        }
    }
    cout << "multiply of the matrix=\n";
    for (p = 0; p < m; p++)
    {
        for (j = 0; j < c; j++)
        {
            mul[p][j] = 0;
            for (k = 0; k < c; k++)
            {
                mul[p][j] += a[p][k] * b[k][j];
            }
        }
    }
    // for printing result
    for (p = 0; p < m; p++)
    {
        for (j = 0; j < c; j++)
        {
            cout << mul[p][j] << " ";
        }
        cout << "\n";
    }
    return 0;
}

