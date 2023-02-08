155. Min Stack
232. Implement Queue using Stacks
225. Implement Stack using Queues
150. Evaluate Reverse Polish Notation
71. Simplify Path
394. Decode String
224. Basic Calculator
227. Basic Calculator II
385. Mini Parser
496. Next Greater Element I
503. Next Greater Element II
402. Remove K Digits
739. Daily Temperatures
735. Asteroid Collision
1673. Find the Most Competitive Subsequence
456. 132 Pattern
84. Largest Rectangle in Histogram
1130. Minimum Cost Tree From Leaf Values
341. Flatten Nested List Iterator
1291. Sequential Digits

__155. Min Stack__
```java
class MinStack {
  private Stack < Integer > stack;
  private Stack < Integer > minStack;

  public MinStack() {
    stack = new Stack < > ();
    minStack = new Stack < > ();
  }

  public void push(int x) {
    stack.push(x);
    if (minStack.isEmpty())
      minStack.push(x);
    else if (x <= minStack.peek()) {
      minStack.push(x);
    }
  }

  public void pop() {
    if (stack.isEmpty())
      return;
    int num = stack.pop();
    if (num == minStack.peek())
      minStack.pop();
  }

  public int top() {
    if (stack.isEmpty())
      return -1;

    return stack.peek();
  }

  public int getMin() {
    if (minStack.isEmpty())
      return -1;

    return minStack.peek();
  }

}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(val);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();
 */
 ```
