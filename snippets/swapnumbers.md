---
title: Swap Numbers 
tags: Maths
expertise: beginner
---

Let us see how this program works:

Initially, a = 5 and b = 10.
Then, we add a and b and store it in a with the code a = a + b. This means a = 5 + 10. So, a = 15 now.
Then we use the code b = a - b. This means b = 15 - 10. So, b = 5 now.
Again, we use the code a = a - b. This means a = 15 - 5. So finally, a = 10.
Hence, the numbers have been swapped.

```cpp
#include <iostream>
using namespace std;

int main()
{
    int a = 5, b = 10;
    cout << "Before swapping." << endl;
    cout << "a = " << a << ", b = " << b << endl;
    a = a + b;
    b = a - b;
    a = a - b;
    cout << "\nAfter swapping." << endl;
    cout << "a = " << a << ", b = " << b << endl;
    return 0;
}