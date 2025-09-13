### [0003] Queue - Linked List Implementation

Tags:
- [Linked List](../12-linked-list.md)
- [Queue](../14-queue.md)

```java
class Node {
    int data;
    Node next;
    Node(int new_data) {
        data = new_data;
        next = null;
    }
}

class Queue {
    private Node front;
    private Node rear;
    public Queue() {
        front = rear = null;
    }
    
    public boolean isEmpty() {
        return front == null;
    }
    
    public void enqueue(int newData) {
        Node newNode = new Node(newData);
        if (isEmpty()) {
            front = rear = newNode;
            return;
        }
        rear.next = newNode;
        rear = newNode;
    }
    
    public void dequeue() {
        if (isEmpty()) {
            return;
        }
        Node temp = front;
        front = front.next;
        if (front == null) rear = null;
    }
}
```
