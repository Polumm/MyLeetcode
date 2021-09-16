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
    vector<vector<int>> levelOrder(TreeNode* root) {
        vector<vector<int>> vec;
        if(!root) return vec;
        queue<TreeNode*> que;
        que.push(root);//根节点入队，再循环，循环条件就是队列非空
        while(que.size()){
            vector<int> v;//创建一维数组
            int sz = que.size();//.size()得到队列长度
            for(int i = 0; i < sz; i++){//处理当前层，循环次数为该层结点数
                TreeNode* temp = que.front();//记录队头指针
                v.push_back(temp->val);//压入该行的数组
                que.pop();//出队
                if(temp->left) que.push(temp->left);//入队
                if(temp->right) que.push(temp->right);//调函数用. 调数据成员用->
            }
            vec.push_back(v);
        }  
        return vec;
    }
};
```

