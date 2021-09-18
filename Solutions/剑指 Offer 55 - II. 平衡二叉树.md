#### [剑指 Offer 55 - II. 平衡二叉树](https://leetcode-cn.com/problems/ping-heng-er-cha-shu-lcof/)

输入一棵二叉树的根节点，判断该树是不是平衡二叉树。如果某二叉树中任意节点的左右子树的深度相差不超过1，那么它就是一棵平衡二叉树。

```c++
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
    int differ(TreeNode* root){
        if(!root) return 0;
        int left = differ(root->left);
        if(left == -1) return  -1;
        int right = differ(root->right);
        if(right == -1) return  -1;
        return abs(right-left) < 2 ? max(left,right) + 1:-1;//+1不能少
    }
    bool isBalanced(TreeNode* root) {
       if(differ(root) == -1) return false;
       return true;
    }
};
```

