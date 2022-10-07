---
title: Custom Comparator
tags: Sorting
expertise: beginner
---

By using custom Comparator, we can sort the linear data according to our own choice comparision. for example, we can sort using number of factor in Number. 

// Inbuilt sort function takes three parameter, third parameter is optional.  
// Third paramter is boolean type comparision function. 
sort(Vec.begin() , Vec.end() , compare);


Example: 
Sort the given array in increasing order of number of distinct factors of each element, i.e., 
element having the least number of factors should be the first to be displayed and the number having highest number of factors should be the last one. 
```cpp
#include <bits/stdc++.h>
using namespace std;

int countFactors(int n){
    int count = 0;
    for(int i = 1 ; i * i <= n ; i++){
		if(n % i == 0){
			count++;
			if(i * i != n){
				count++;
			}
		}
	}
    return count;
}
bool compare(int val1, int val2){
	int count1 = countFactors(val1);
	int count2 = countFactors(val2);
    if (count1 == count2){
        return val1 <= val2;
	}
    return count1 < count2;
}
vector<int> solve(vector<int> &A) {
	sort(A.begin() , A.end() , compare);
	return A;
}

int main() {
	
	vector<int> v;
	v.push_back(6);
	v.push_back(8);
	v.push_back(9);
	solve(v);
	
	for(int ele:v) cout<<ele<<" "; // 9 6 8

 
}

```

