---
title: Decimal To Binary
tags: Binary Conversion
expertise: beginner
---

>>> CPP program to Decimal to binary conversion
>>> using bitwise operator
>>> Size of an integer is assumed to be 32 bits

```cpp
int decToBinary(int NUM)
{
    for (int i = 31; i >= 0; i--) {
        int k = NUM >> i;
        if (k & 1)
            cout << "1";
        else
            cout << "0";
    }
}

```

```cpp
int NUM = 10;
// Function call
cout << decToBinary(NUM) << endl;
```
