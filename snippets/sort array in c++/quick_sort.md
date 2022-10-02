---
title: Sorting Using  
tags: Quick Sort Algorithm
expertise: beginner
---

```cpp
// CPP Program to demonstrate different sorting methods for array
#include <iostream>
using namespace std;
int parition(int l,int r,int arr[]) {
    int i = l - 1;
    int pivot = arr[r];
    for (int j = l; j < r; j++) {
        if (arr[j]<pivot) {
            i++;
            swap(arr[j],arr[i]);
        }
    }
    swap(arr[i+1],arr[r]);
    return i + 1;
}
void quicksort(int l, int r, int arr[]) {
    if (l<r-1) {
        int pivot = parition(l,r-1,arr);
        quicksort(l, pivot - 1, arr);
        quicksort(pivot + 1, r, arr);
    }
}
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
    quicksort(0,s,arr);
    for (int i = 0; i < s; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}


```