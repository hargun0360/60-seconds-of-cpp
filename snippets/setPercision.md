---
title: SetPrecision Function
tags: Math
expertise: beginner
---

By using the setprecision function, we can get the desired precise value of a floating-point or a double value by providing the exact number of decimal places.
The syntax of the setprecision() function in C++ is as follows:

setprecision(argument)

Argument: This is the integer type parameter that specifies the number of significant digits needed in a floating-point or double value.

cout << setprecision(n) << float_variable;


```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {

  // initialize a floating-point 
  float num = 2.81928;
  cout << "Original number is: " << num;
  cout << "\n";

  // print 3 significant figures
  cout << "The number with 3 significant figures is: ";
  cout << setprecision(4) <<num;
  cout << "\n\n";
  return 0; 
}
/*  Output
Original number is: 2.81928
The number with 3 significant figures is: 2.819

*/

```

