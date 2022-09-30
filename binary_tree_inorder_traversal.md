---
title: Binary Tree Inorder Traversal
tags: Stack Tree Binary Tree Depth-First Search
expertise: beginner
---

-Given: Given the root of a binary tree, return the inorder traversal of its nodes' values.
-Input: root = [1,null,2,3]
-Output: [1,3,2]

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    vector<int> vec;
    vector<int> inorderTraversal(TreeNode* root) {
        if(root==NULL){
            return vec;
        }else{
            inorderTraversal(root->left);
            vec.push_back(root->val);
            inorderTraversal(root->right);
        }
        return vec;
    }
};
```
