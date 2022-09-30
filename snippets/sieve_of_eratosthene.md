---
title: Sieve Of Eratosthenes
tags: math, primes
expertise: intermediate
cover: [blog_images/digital-nomad-15.jpg](https://upload.wikimedia.org/wikipedia/commons/b/b9/Sieve_of_Eratosthenes_animation.gif)
---

Calculates the prime from 1 to N.

```cpp

#include <bits/stdc++.h>

using namespace std;
const int N = 100006;
int prime[N];
vector<int> pr;

void sieve(int n){
	int i, j;
	memset(prime, 0, sizeof(prime));
	prime[0] = 1; prime[1] = 1;
	for(i = 2; i * i <= n; i++){
		if(prime[i] == 0){
			for(j = i * i; j <= n; j += i){
				prime[j] = 1;
			}
		}
	}
	for(i = 2; i <= n; i++){
		if(prime[i] == 0){
			pr.push_back(i);
		}
	}
}

int main()
{
    int n;
    cin>>n;
    
    sieve(n);
    for(int i = 0; i<pr.size(); ++i){
        cout<<pr[i]<<" ";
    }

    return 0;
}
```

