---
title: Sorting Using  algorithm header file
tags: Sorting inbuilt function
expertise: beginner
---

```cpp
// CPP Program to demonstrate different sorting methods for array
    #include <iostream>
    #include <algorithm>
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

        sort(arr,arr+s);
        
        for (int i = 0; i < s; i++) {
            cout << arr[i] << " ";
        }
        cout << endl;

        return 0;
    }
```