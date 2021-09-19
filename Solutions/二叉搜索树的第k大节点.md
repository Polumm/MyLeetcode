[二叉搜索树的第k大节点](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-di-kda-jie-dian-lcof/)


给定一棵二叉搜索树，请找出其中第k大的节点。

 

**示例 1:**

```
输入: root = [3,1,4,null,2], k = 1
   3
  / \
 1   4
  \
   2
输出: 4
```

**示例 2:**

```
输入: root = [5,3,6,2,4,null,null,1], k = 3
       5
      / \
     3   6
    / \
   2   4
  /
 1
输出: 4
```

 

**限制：**

1 ≤ k ≤ 二叉搜索树元素个数

**第一种高时空开销**

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
    int kthLargest(TreeNode* root, int k) {
        vector<int> vec;
        inorder(root, vec);
        return vec[vec.size()-k];
    }
    void inorder(TreeNode* root, vector<int> & vec){
        if(!root) return;//又忘写边界条件了
        inorder(root->left, vec);
        vec.push_back(root->val);
        inorder(root->right, vec);
    }
};
```

**第二种方法待续，逻辑错误，GG**

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
    int kthLargest(TreeNode* root, int k) {
        int m;
        inorder(root, k, m);
        return m;
    }
    void inorder(TreeNode* root, int k, int & m){
        if(!root) return ;//又忘写边界条件了
        inorder(root->left, k, m);
        if(k = 1) m = root->val;
        k--;
        inorder(root->right, k, m);
    }
};

```

