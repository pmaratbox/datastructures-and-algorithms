### [0009] Multiplication Table

#### `Tags`
- [Basics](../01-basics.md)

#### `Solution`
```java
class Solution {
    void printTable(int n) {
        for (int i = 1; i <= 10; ++i) {
            System.out.printf("%d * %d = %d%n", n, i, n * i);
        }
    }
}
```
- Time complexity: O(1)
- Space complexity: O(1)
