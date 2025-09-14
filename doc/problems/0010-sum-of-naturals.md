### [0010] Find Sum

#### `Tags`
- [Basics](../01-basics.md)

#### `Solution`
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
