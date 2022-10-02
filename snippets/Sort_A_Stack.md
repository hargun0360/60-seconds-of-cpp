---
title: Sort A Stack
tags: stack, sorting
expertise: intermediate
---

The approach to sort a stack using another temporary stack is very simple. We will loop over the main stack until the underflow condition occurs. Here we will use .isEmpty() function of stack container class which tells whether the stack is empty or not. Then, we will pop out the element out of the stack and compares it will element in the temporary stack. If the top element of the temporary stack is greater than the popped element of the main stack, we will pop it out of the temporary stack and push into the main stack, meanwhile, we will push the popped element of the main stack into the temporary stack.
At the end of the loop, the main stack gets empty and elements are stored in the temporary stack in a decreasing sorted order. If we want the order to be increasing, we have to push all the elements back to the main stack.

```cpp
#include <bits/stdc++.h> 
using namespace std; 

stack<int> sortFunction(stack<int> &mainStack) { 
  
    stack<int> AuxStack; 

    while (!mainStack.empty()) { 
        // pop out the first element 
        int temp = mainStack.top(); 
        mainStack.pop(); 

        while (!AuxStack.empty() && AuxStack.top() > temp) { 
            // pop from Auxstack and push it to the mainstack 
            mainStack.push(AuxStack.top()); 
            AuxStack.pop(); 
        } 

        // push temp in end 
        AuxStack.push(temp); 
    }     
  return AuxStack; 
} 

// main function 
int main() { 
  stack<int> mainStack; 
    mainStack.push(78); 
    mainStack.push(103); 
    mainStack.push(31); 
    mainStack.push(19); 
    mainStack.push(67); 
    mainStack.push(83); 
    mainStack.push(47);

    // Declaring AuxStack
    stack<int> AuxStack = sortFunction(mainStack); 
    cout << "Sorted numbers in decreasing order are:" << endl; 
    while (!AuxStack.empty()) { 
        cout << AuxStack.top() << " "; 
        mainStack.push(AuxStack.top());
        AuxStack.pop(); 
    } 
    cout << endl;
    cout << "Sorted numbers in increasing order are:" << endl;
    while(!mainStack.empty()) {
        cout << mainStack.top() << " ";
        mainStack.pop();
    }
} 
```
