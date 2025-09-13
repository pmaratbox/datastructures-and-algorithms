### Queue - Circular Array Implementation

[_Back to Queue_](../14-queue.md)

```java
class Queue {
    private int[] arr;
    private int front, size;
    private int capacity;
    
    public Queue(int c) {
        arr = new int[c];
        capacity = c;
        size = 0;
        front = 0;
    }
    
    public int getFront() {
        if (size == 0)
            return -1;
        return arr[front];
    }
    
    public int getRear() {
        if (size == 0)
            return -1;
        int rear = (front + size - 1) % capacity;
        return arr[rear];
    }
    
    public void enqueue(int x) {
        if (size == capacity)
            return;
        int rear = (front + size) % capacity;
        arr[rear] = x;
        size++;
    }
    
    public int dequeue() {
        if (size == 0)
            return -1;
        int res = arr[front];
        front = (front + 1) % capacity;
        size--;
        return res;
    }
}
```
