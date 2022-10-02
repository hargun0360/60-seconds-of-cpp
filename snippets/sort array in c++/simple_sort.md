---
title: Sorting Using  double for loop
tags: Sorting Algorithm
expertise: beginner
---

```cpp
// CPP Program to demonstrate different sorting methods for array

#include <iostream>
using namespace std;
int main()
{
    int  s;
    cout << " Define the size of the array: " << endl;
    cin >> s;
    int* arr = new int[s];
    for (int i = 0; i < s; i++) {
        int x;
        cout << "Enter " << i+1<<" value ";
        cin >> x;
        arr[i] = x;
    }
    for (int i = 0; i < s - 1; i++) {
        for (int j = i+1; j < s; j++) {
            if (arr[i] > arr[j]) {
                swap(arr[i], arr[j]);
            }
        }
    }
    for (int i = 0; i < s; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}

```