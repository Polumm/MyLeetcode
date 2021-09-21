#### [剑指 Offer 25. 合并两个排序的链表](https://leetcode-cn.com/problems/he-bing-liang-ge-pai-xu-de-lian-biao-lcof/)

难度简单166收藏分享切换为英文接收动态反馈

输入两个递增排序的链表，合并这两个链表并使新链表中的节点仍然是递增排序的。

**示例1：**

```
输入：1->2->4, 1->3->4
输出：1->1->2->3->4->4
```

**限制：**

```
0 <= 链表长度 <= 1000
```

注意：本题与主站 21 题相同：https://leetcode-cn.com/problems/merge-two-sorted-lists/

```c++
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        ListNode* dum = new ListNode(0), *cur = dum;
        //辅助结点和当前指针,一定要new构造一下，不然就是NULL
        while(l1 && l2){
            l1->val > l2->val ? (cur->next = l2, l2 = l2->next) : (cur->next =l1, l1=l1->next);
            cur = cur->next;//新链表的当前指针得往前移动
        }
        !l1 ? cur->next = l2 : cur->next = l1;
        return dum->next;
    }
};
```

