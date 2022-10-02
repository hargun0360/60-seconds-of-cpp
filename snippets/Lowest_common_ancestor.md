---
title: Lowest Common Ancestor in a Binary Tree
tags: binary tree
expertise: intermediate
---

The lowest common ancestor is the lowest node in the tree that has both n1 and n2 as descendants, where n1 and n2 are the nodes for which we wish to find the LCA. Hence, the LCA of a binary tree with nodes n1 and n2 is the shared ancestor of n1 and n2 that is located farthest from the root.

-  We pass the root to a helper function and check if the value of the root matches any of n1 and n2. 
If YES, return the root
else recursive call on the left and right subtree

```cpp
TreeNode *helper(TreeNode *root, int x, int y){
    if(!root)
        return NULL;
    if(root->data==x||root->data==y)
        return root;
      TreeNode * l=helper(root->left,x,y);
        TreeNode * r=helper(root->right,x,y);
    if(l&&r)
        return root;
    if(l)
        return l;
    if(r)
        return r;
    return NULL;

}
int lowestCommonAncestor(TreeNode *root, int x, int y)
{
	//    Write your code here
    return helper(root,x,y)->data;


}
```
