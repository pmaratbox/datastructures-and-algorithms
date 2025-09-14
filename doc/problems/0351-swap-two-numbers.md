### [0351] Swap Two Numbers

#### `Tags`
- [Basics](../01-basics.md)
- [Bitwise Algorithms](../23-bitwise-algorithms.md)

#### `Solution 1 - Using Third Variable`
```java
class Solution {
    public static void main(String[] args) {
        int a = 5, b = 8;
        System.out.printf("a=%d, b=%d%n", a, b);
        int temp = a;
        a = b;
        b = temp;
        System.out.printf("a=%d, b=%d%n", a, b);
    }
}
```
- Time complexity: O(1)
- Space complexity: O(n)

#### `Solution 2 - Using Arithmetic Operator`
```java
class Solution {
    public static void main(String[] args) {
        int a = 5, b = 8;
        System.out.printf("a=%d, b=%d%n", a, b);
        a = a + b;
        b = a - b;
        a = a - b;
        System.out.printf("a=%d, b=%d%n", a, b);
    }
}
```
- Time complexity: O(1)
- Space complexity: O(1)

#### `Solution 3 - Using Bit Operator`
```java
class Solution {
    public static void main(String[] args) {
        int a = 5, b = 8;
        System.out.printf("a=%d, b=%d%n", a, b);
        a = a ^ b;
        b = a ^ b;
        a = a ^ b;
        System.out.printf("a=%d, b=%d%n", a, b);
    }
}
```
- Time complexity: O(1)
- Space complexity: O(1)