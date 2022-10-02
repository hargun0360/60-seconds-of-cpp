---
title: Check a tree is symmetric or not
tags: tree,recursion
expertise: easy
---

Given a binary tree, check whether it is a mirror of itself.
- recursively checks two roots and subtrees under the root.


```cpp
bool helper(Node* l,Node* r){
    if(r==NULL||l==NULL)
        return r==l;
    return (r->data==l->data&&helper(l->left,r->right)&&helper(l->right,r->left));
}

bool isSymmetric(Node* root)
{
    // Write your code here.  
    return helper(root,root);
}
```