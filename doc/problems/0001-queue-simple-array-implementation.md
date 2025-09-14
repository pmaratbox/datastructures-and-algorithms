### [0001] Queue - Simple Array Implementation

#### `Task`
Implement queue using array.

#### `Tags`
- [`Array`](../02-array.md)
- [`Queue`](../14-queue.md)

#### `Solution`
```java
public class Queue {
    private int[] array;
    private int size;
    private int capacity;

    public Queue() {
        capacity = 10; // initial capacity
        array = new int[capacity];
        size = 0;
    }

    public boolean isEmpty() {
        return size == 0;
    }

    public void enqueue(int x) {
        if (size == capacity) {
            throw new IllegalArgumentException();
        }
        array[size++] = x;
    }

    public void dequeue() {
        if (!isEmpty()) {
            for (int i = 1; i < size; i++) {
                array[i - 1] = array[i];
            }
            size--;
        }
    }

    public int getFront() {
        return isEmpty() ? -1 : array[0];
    }
}
```
- Time complexity: O(1)
- Space complexity: O(n)
