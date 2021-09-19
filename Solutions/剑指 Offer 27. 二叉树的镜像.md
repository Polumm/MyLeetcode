#### [剑指 Offer 27. 二叉树的镜像](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)

难度简单175收藏分享切换为英文接收动态反馈

请完成一个函数，输入一个二叉树，该函数输出它的镜像。

例如输入：

`   4  /  \ 2   7 / \  / \1  3 6  9`
镜像输出：

```
   4  /  \ 7   2 / \  / \9  6 3  1
```

 

**示例 1：**

```
输入：root = [4,2,7,1,3,6,9]
输出：[4,7,2,9,6,3,1]
```

 

**限制：**

```
0 <= 节点个数 <= 1000
```



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
    TreeNode* mirrorTree(TreeNode* root) {
        if(!root) return NULL;
        mirrorTree(root->left);
        rootSwap(root);
        mirrorTree(root->left);
        return root; 
    }
    void rootSwap(TreeNode* root){
        TreeNode* temp = root->left;
        root->left = root->right;
        root->right = temp;
    }
};
```

