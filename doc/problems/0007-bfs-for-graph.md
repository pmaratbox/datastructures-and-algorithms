### [0007] Breadth First Search for a Graph

Tags:
- [Queue](../14-queue.md)
- [Graph](../18-graph.md)

[Approach 1] - BFS from a Given Source
```java
class Solution {
    ArrayList<Integer> bfs(ArrayList<ArrayList<Integer>> adj) {
        int V = adj.size();
        int s = 0;
        ArrayList<Integer> res = new ArrayList<>();
        
        Queue<Integer> q = new LinkedList<>();
        boolean[] visited = new boolean[V];
        
        visited[s] = true;
        q.add(s);
        
        while (!q.isEmpty()) {
            int curr = q.poll();
            res.add(curr);
            
            for (int x : adj.get(curr)) {
                if (!visited[x]) {
                    visited[x] = true;
                    q.add(x);
                }
            }
        }
        return res;
    }
}
```

[Approach 2] - BFS of the Disconnected Graph
```java
class Solution {
    ArrayList<Integer> bfsOfGraph(
            ArrayList<ArrayList<Integer>> adj, int s, boolean[] visited, ArrayList<Integer> res) {
        
        Queue<Integer> q = new LinkedList<>();
        
        visited[s] = true;
        q.add(s);
        
        while (!q.isEmpty()) {
            int curr = q.poll();
            res.add(curr);
            
            for (int x : adj.get(curr)) {
                if (!visited[x]) {
                    visited[x] = true;
                    q.add(x);
                }
            }
        }
        return res;
    }
    
    ArrayList<Integer> bfsDisconnected(
                ArrayList<ArrayList<Integer>> adj) {
        int V = adj.size();
        ArrayList<Integer> res = new ArrayList<>();
        boolean[] visited = new boolean[V];
        
        for (int i = 0; i < V; i++) {
            if (!visited[i]) {
                bfsOfGraph(adj, i, visited, res);
            }
        }
        return res;
    }
}
```
