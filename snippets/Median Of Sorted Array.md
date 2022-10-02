---
title: Median Of A Sorted Array If Number Of Elements are Even.
tags: Array
expertise: beginner
---

-Given a Array, Find the Median(Average Of Middle Of Two Numbers) Of THe Array If Length Of Array Is Even.

-Input: int arr[] = { 2, 5, 6, 8, 14, 20 };

-Output: 7.0

```cpp
#include <iostream>
using namespace std;
class Solution
{
public:
//Function to find the median of the given array
double medianofarr(int *arr, int n)
{
// code start
int i=0,j=n-1;
while(i+1 != j)
{
i++;
j--;
}
double ans = (arr[i] + arr[j])/2;
return ans;
}
};
int main()
{
int t;
cin >> t;
while (t--)
{
int n;
cin >> n;
int *arr = new int[n];
for(int i=0; i<n; i++) cin>>arr[i];
Solution obj;
if(n >= 2) cout<<obj.medianofarr(arr, n)<<endl;
else cout<<"0"<<endl;
delete arr;
}
}
```
