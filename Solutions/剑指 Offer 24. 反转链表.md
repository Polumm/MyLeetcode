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
    ListNode* reverseList(ListNode* head) {
        ListNode* fast, * slow;
        if(!head) return head;
        fast = head->next;
        slow = head; slow->next = NULL;
        while(fast){
            head = fast->next;
            fast->next = slow;
            slow = fast;
            fast = head;
        }    
        return slow;
    }
};

```

