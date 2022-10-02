---
title: Peak Element
tags: Interview Question
expertise: intermediate
firstSeen: 2022-10-3
---

An element is called a peak element if its value is not smaller than the value of its adjacent elements(if they exists).

```cpp
#include<bits/stdc++.h>
using namespace std;

class Solution
{
    public:
    int peakElement(int arr[], int n){
        
        int peak=0,b=0,c=0;
        for (int i=0;i<n;i++){
            if (arr[i]>arr[i-1] ){
                if (arr[i]>peak){
                    peak=arr[i];
                    b=i;
                }
            }
            else {
            c+=1;
            }
        }
        return b;
        if (c>1){
            return 0;
        }
    }
};

int main() {
	int t;
	cin>>t;
	while(t--)
	{
		int n;
		cin>>n;
		int a[n], tmp[n];
		for(int i=0;i<n;i++)
		{
			cin>>a[i];
			tmp[i] = a[i];
		}
		bool f=0;
		Solution ob;
		
		int A = ob. peakElement(tmp,n);
		
		if(A<0 and A>=n)
		    cout<<0<<endl;
		else
		{
    		if(n==1 and A==0)
    		    f=1;
    		else if(A==0 and a[0]>=a[1])
    		    f=1;
    		else if(A==n-1 and a[n-1]>=a[n-2])
    		    f=1;
    		else if(a[A]>=a[A+1] and a[A]>= a[A-1])
    		    f=1;
    		else
    		    f=0;
    		cout<<f<<endl;
		}
		
	}

	return 0;
}
```

