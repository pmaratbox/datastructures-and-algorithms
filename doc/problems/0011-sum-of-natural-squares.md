### [0011] Sum of Squares of First n Natural Numbers

#### `Tags`
- [Basics](../01-basics.md)

#### `Solution 1 - Using Loop`
```java
class Solution {
    int summation(int n)
    {
        int sum = 0;
        for (int i = 1; i <= n; i++)
            sum += (i * i);

        return sum;
    }
}
```
- Time complexity: O(n)
- Space complexity: O(1)

#### `Solution 2 - Using Formula`
```java
class Solution {
    int summation(int n) {
        return (n * (n + 1) * (2 * n + 1)) / 6;
    }
}
```
- Time complexity: O(1)
- Space complexity: O(1)
