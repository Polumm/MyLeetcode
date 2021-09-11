```c++
class CQueue {
private:
stack<int> stack1, stack2;
public:
    CQueue() {  
    }
    void appendTail(int value) {
        stack1.push(value);
    }
    int deleteHead() {
        if(stack2.empty()){//.empty栈空返回真
            while(!stack1.empty()){
                stack2.push(stack1.top());
                stack1.pop();
                //为什么不pop stack1就会超出时间限制？不清理，每次pop返回的都是stack1栈底元素
            }
        }
        if(stack2.empty()){
            return -1;
        }
        int pop = stack2.top();
        stack2.pop();
        return pop;
    }
};
//.pop只负责删除，返回类型为void，应该先.top记录一下
//reference binding to misaligned address：数组访问越界
/**
 * Your CQueue object will be instantiated and called as such:
 * CQueue* obj = new CQueue();
 * obj->appendTail(value);
 * int param_2 = obj->deleteHead();
 */
```

对于栈而言每次出栈的只能是栈顶，要想pop()出栈底元素，可以用另一个栈中转一下，顺序就反过来了。
