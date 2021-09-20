#### [剑指 Offer 28. 对称的二叉树](https://leetcode-cn.com/problems/dui-cheng-de-er-cha-shu-lcof/)

请实现一个函数，用来判断一棵二叉树是不是对称的。如果一棵二叉树和它的镜像一样，那么它是对称的。

例如，二叉树 [1,2,2,3,4,4,3] 是对称的。

`  1  / \ 2  2 / \ / \3  4 4  3`
但是下面这个 [1,2,2,null,3,null,3] 则不是镜像对称的:

```
  1  / \ 2  2  \  \  3   3
```



```C++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    bool isSymmetric(TreeNode* root) {
        int flag = 1;
        if(!root) return 1;
        visit(root->left, root->right, flag);
        return flag;
    }
    void visit(TreeNode* l, TreeNode* r, int & flag){
        if(flag == 0) return;
        if((!l && r )||(!r && l)) flag = 0;
        if(!l) return;
        if(!r) return;
        visit(l->left, r->right, flag);
        if(l->val != r->val) flag = 0;
        if(l == r) return;
        visit(l->right, r->left, flag);
    }
};/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    bool isSymmetric(TreeNode* root) {
        if(visit(root->left, root->right)) return true;
        return false;
    }
    int visit(TreeNode* lroot, TreeNode* rroot){
        if(!lroot && !rroot) return 1;
        if(!lroot) return 0;
        if(!rroot) return 0;
        visit(lroot->left, rroot->right);
        if(lroot->val != rroot->val) return 0;
        visit(lroot->right, rroot->left);C++
        return 1;
    }
};
```

