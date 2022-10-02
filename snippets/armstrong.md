---
title: Armstrong Number
tags: Math
expertise: beginner
---

- This program takes a positive integer from an user and checks whether the given number is Armstrong or not.
- An Armstrong number of three digits is an integer such that the sum of the cubes of its digits is equal to the number itself. 
- Ex : 371 is an Armstrong number since 3^3 + 7^3 + 1^3 = 371.

```cpp
#include <cmath>
#include <iostream>

using namespace std;

int main() {
   int num, originalNum, remainder, n = 0, result = 0, power;
   cout << "Enter an integer: ";
   cin >> num;

   originalNum = num;

   while (originalNum != 0) {
      originalNum /= 10;
      ++n;
   }
   originalNum = num;

   while (originalNum != 0) {
      remainder = originalNum % 10;

      // pow() returns a double value
      // round() returns the equivalent int
      power = round(pow(remainder, n));
      result += power;
      originalNum /= 10;
   }

   if (result == num)
      cout << num << " is an Armstrong number.";
   else
      cout << num << " is not an Armstrong number.";
   return 0;
}
