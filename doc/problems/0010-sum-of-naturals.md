### [0010] Find Sum

#### `Tags`
- [Basics](../01-basics.md)
- [Mathematical Algorithms](../27-mathematical-algorithms.md)

#### `Solution 1 - Using Loop`
```java
class Solution {
     int findSum(int n){
        int sum = 0;
        for (int i= 1; i <= n; i++) {
            sum = sum + i;
        }
        return sum;
    }
}
```
- Time complexity: O(n)
- Space complexity: O(1)

#### `Solution 2 - Using Recursion`
```java
class Solution {
     int findSumRecursively(int n){
        if (n==1) {
            return 1;
        }
        return n + findSum(n-1);
    }
    
    int findSumR(int n) {
         int sum = findSumRecursively(n);
    }
}
```
- Time complexity: O(n)
- Space complexity: O(n)

#### `Solution 3 - Using Formula`
```java
class Solution {
    int findSum(int n) {
        return (n * (n + 1)) / 2;
    }
}
```
- Time complexity: O(1)
- Space complexity: O(1)
