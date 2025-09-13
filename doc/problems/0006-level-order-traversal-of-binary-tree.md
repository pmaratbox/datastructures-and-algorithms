### [0006] Level Order Traversal (Breadth First Search) of Binary Tree

Tags:
- [Queue](../14-queue.md)
- [Tree](../16-tree.md)

[Approach 1] - Using Recursion - O(n) time and O(n) space
```java
class Node {
    int data;
    Node left, right;
    
    Node(int value) {
        data = value;
        left = null;
        right = null;
    }
}

class Solution {
    void levelOrderRec(Node root, int level, List<List<Integer>> res) {
        if (root == null) return;
        
        if (res.size() <= level)
            res.add(new ArrayList<>());
        
        res.get(level).add(root.data);
        
        levelOrderRec(root.left, level + 1, res);
        levelOrderRec(root.right, level + 1, res);
    }
    
    List<List<Integer>> levelOrder(Node root) {
        List<List<Integer>> res = new ArrayList<>();
        levelOrderRec(root, 0, res);
        return res;
    }
}
```

[Approach 2] - Using Queue (Iterative) - O(n) time and O(n) space
```java
class Node {
    int data;
    Node left, right;
    
    Node(int value) {
        data = value;
        left = null;
        right = null;
    }
}

class Solution {
    static List<List<Integer>> levelOrder(Node root) {
        if (root == null)
            return new ArrayList<>();
        
        Queue<Node> q = new LinkedList<>();
        List<List<Integer>> res = new ArrayList<>();
        
        q.offer(root);
        int currLevel = 0;

        while (!q.isEmpty()) {
            int len = q.size();
            res.add(new ArrayList<>());

            for (int i = 0; i < len; i++) {
                Node node = q.poll();
                res.get(currLevel).add(node.data);
                
                if (node.left != null)
                    q.offer(node.left);
                
                if (node.right != null)
                    q.offer(node.right);
            }
            currLevel++;
        }
        return res;
    }
}
```
