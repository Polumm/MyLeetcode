```c++
class MinStack {
    stack<int> A;//主栈，所有元素都会存入A中
    stack<int> B;//只存当前最小值
public:
    /** initialize your data structure here. */
    MinStack() {
        B.push(INT_MAX);//B一开始为空，防止数组越界
    }

void push(int x) {
    A.push(x);
    B.push(std::min(B.top(), x));//占用命名空间后用std::访问标准函数
    //一方面保证B栈顶一直是最小值，一方面使得A，B相对同步，进而保留了较小值的历史记录，可回溯
}
void pop() {
    A.pop();
    B.pop();
}

int top() {
    return A.top();
}

int min() {
    return B.top();
}
};

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack* obj = new MinStack();
 * obj->push(x);
 * obj->pop();
 * int param_3 = obj->top();
 * int param_4 = obj->min();
 */
```

