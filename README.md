# MIN-STACK-Leetcode

private:
    stack<int> minStack;
    stack<int> values;
public:
    /** initialize your data structure here. */
    MinStack() {
        
    }
    
    void push(int val) {
        values.push(val);

        if(minStack.empty()) {
            minStack.push(val);
            return;
        }
        
        minStack.push(min(minStack.top(), val));      
    }
    
    void pop() {
        if(values.empty()) return;
        
        minStack.pop();
        
        values.pop();
    }
    
    int top() {
        return !values.empty() ? values.top() : -1;
    }
    
    int getMin() {
        return !minStack.empty() ? minStack.top() : -1;
    }
};
