#### `[0004] Stack Using Queues`

`Tags`:
- [`Stack`](../13-stack.md)
- [`Queue`](../14-queue.md)

`[Approach 1] - Using Two Queue - Push in O(n) and Pop() in O(1)`
```java
class MyStack {
    Queue<Integer> q1 = new LinkedList<>();
    Queue<Integer> q2 = new LinkedList<>();

    public void push(int x) {
        q2.add(x);
        
        while (!q1.isEmpty()) {
            q2.add(q1.peek());
            q1.remove();
        }
        
        Queue<Integer> t = q1;
        q1 = q2;
        q2 = t;
    }

    public void pop() {
        if (q1.isEmpty())
            return;
        q1.remove();
    }

    public int top() {
        if (q1.isEmpty())
            return -1;
        return q1.peek();
    }

    public int size() { return q1.size(); }
}
```

`[Approach 2] - Using Two Queue - Push in O(1) and Pop() in O(n)`
```java
class MyStack {
    Queue<Integer> q1 = new LinkedList<>();
    Queue<Integer> q2 = new LinkedList<>();
    
    public void push(int x) {
        q2.add(x);
        
        while (!q1.isEmpty()) {
            q2.add(q1.peek());
            q1.remove();
        }
        
        Queue<Integer> t = q1;
        q1 = q2;
        q2 = t;
    }
    
    public void pop() {
        if (q1.isEmpty())
            return;
        q1.remove();
    }
    
    public int top() {
        if (q1.isEmpty())
            return -1;
        return q1.peek();
    }
    
    public int size() { return q1.size(); }
}
```

`[Approach 3] - Using Single Queue - Push in O(n) and Pop() in O(1)`
```java
class MyStack {
    Queue<Integer> q1 = new LinkedList<>();
    Queue<Integer> q2 = new LinkedList<>();
    
    public void push(int x) {
        q2.add(x);
        
        while (!q1.isEmpty()) {
            q2.add(q1.peek());
            q1.remove();
        }
        
        Queue<Integer> t = q1;
        q1 = q2;
        q2 = t;
    }
    
    public void pop() {
        if (q1.isEmpty())
            return;
        q1.remove();
    }
    
    public int top() {
        if (q1.isEmpty())
            return -1;
        return q1.peek();
    }
    
    public int size() { return q1.size(); }
}
```

