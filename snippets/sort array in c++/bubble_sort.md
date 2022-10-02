---
title: Sorting 
tags: Bubble Sort
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
    for (int i = 0; i < s-1; i++) {
        for (int j = 0; j <s-i-1; j++){
            if (arr[j] > arr[j+1]) {
                swap(arr[j], arr[j+1]);
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