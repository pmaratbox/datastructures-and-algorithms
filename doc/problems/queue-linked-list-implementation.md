### Queue - Linked List Implementation

[_Back to Queue_](../14-queue.md)

```java
class Node {
    int data;
    Node next;
    Node(int new_data) {
        data = new_data;
        next = null;
    }
}

// Queue class definition
class Queue {
    private Node front;
    private Node rear;
    public Queue() {
        front = rear = null;
    }
    
    public boolean isEmpty() {
        return front == null;
    }
    
    public void enqueue(int new_data) {
        Node new_node = new Node(new_data);
        if (isEmpty()) {
            front = rear = new_node;
            printQueue();
            return;
        }
        rear.next = new_node;
        rear = new_node;
        printQueue();
    }
    
    public void dequeue() {
        if (isEmpty()) {
            return;
        }
        Node temp = front;
        front = front.next;
        if (front == null) rear = null;
        printQueue();
    }
}
```
