### [0011] Sum of Squares of First n Natural Numbers

Tags:
- [Basics](../01-basics.md)

[Approach 1] - Adding One By One - O(n) Time and O(1) Space
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

[Approach 2] - Using Mathematical Formulae - O(1) Time and O(1) Space
```java
class Solution 
{
    int summation(int n)
    {
        return (n * (n + 1) * (2 * n + 1)) / 6;
    }
}
```
