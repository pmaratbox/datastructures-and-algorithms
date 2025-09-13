### [0005] Queue Using Stacks

Tags:
- [Stack](../13-stack.md)
- [Queue](../14-queue.md)

[Approach 1] - By Making Enqueue Operation Costly
```java
 static class Queue {
    Stack<Integer> s1 = new Stack<>();
    Stack<Integer> s2 = new Stack<>();

    void enqueue(int x) {
        while (!s1.empty()) {
            s2.push(s1.peek());
            s1.pop();
        }
        
        s1.push(x);
        
        while (!s2.empty()) {
            s1.push(s2.peek());
            s2.pop();
        }
    }
    
    int dequeue() {
        if (s1.empty()) {
            return -1;
        }
        
        int x = s1.peek();
        s1.pop();
        return x;
    }
}
```

[Approach 2] - By Making Dequeue Operation Costly
```java
 static class Queue {
    Stack<Integer> s1 = new Stack<>();
    Stack<Integer> s2 = new Stack<>();
    
    void enqueue(int x) {
        s1.push(x);
    }
    
    int dequeue() {
        if (s1.empty() && s2.empty()) {
            return -1;
        }
        
        if (s2.empty()) {
            while (!s1.empty()) {
                s2.push(s1.peek());
                s1.pop();
            }
        }
        
        int x = s2.peek();
        s2.pop();
        return x;
    }
}
```

[Approach 3] - Using One Stack and Recursion
```java
static class Queue {
    Stack<Integer> s = new Stack<>();
    
    void enqueue(int x) {
        s.push(x);
    }
    
    int dequeue() {
        if (s.empty()) {
            return -1;
        }
        
        int x = s.peek();
        s.pop();
        
        if (s.empty())
            return x;
        
        int item = dequeue();
        s.push(x);
        
        return item;
    }
}
```

