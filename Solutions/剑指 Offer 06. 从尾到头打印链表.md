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
    vector<int> reversePrint(ListNode* head) {
        int count = 0;
        ListNode* T = head;
        while(T!=nullptr){
            ++count;
            T = T->next;
        }
        vector<int> vet(count);
        for(int i = count-1; i > -1; i--,head = head->next){
            vet[i] = head->val;
        }
    return vet;
    }
};
```

