### [0002] Queue - Circular Array Implementation

#### `Task`
Implement queue using circular array.

#### `Tags` 
- [Array](../02-array.md)
- [Queue](../14-queue.md) 

#### `Solution`
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
