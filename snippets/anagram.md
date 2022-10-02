---
title: anagram
tags: String
expertise: intermediate
---

Explain briefly what the snippet does.

- An anagram of a string is another string that contains the same characters, only the order of characters can be different.
- Use `anagram()` to check if the provided `args` are anagram.
- Provided `args` should be strings.
- Use `#include<bits/stdc++.h>` as header.

```cpp
bool anagram(string s1, string s2)
{
    int n1 = s1.length();
    int n2 = s2.length();

    if (n1 != n2)
        return false;

    sort(s1.begin(), s1.end());
    sort(s2.begin(), s2.end());

    for (int i = 0; i < n1; i++)
        if (s1[i] != s2[i])
            return false;

    return true;
}
```

```cpp
int main(){
    string str1 = "test";
    string str2 = "rest";

    if (anagram(str1, str2))
        cout <<"The two strings are anagram."<<endl;
    else
        cout << "The two strings are not anagram."<<endl;
    return 0;
}

#### result : The two strings are not anagram.

```

```cpp
int main(){
    string str1 = "elbow";
    string str2 = "below";

    if (anagram(str1, str2))
        cout <<"The two strings are anagram."<<endl;
    else
        cout << "The two strings are not anagram."<<endl;
    return 0;
}

#### result : The two strings are anagram.

```
