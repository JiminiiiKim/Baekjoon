### 문제 풀이 핵심 아이디어 :
        dfs, bfs 구현하기 !
        dfs : stack을 사용해 하나 꺼내서 방문하지 않은 노드 출력 후, graph 원소들 stack에 넣기
        bfs : queue를 사용해 하나 꺼내서, graph 원소 중 방문하지 않은 원소 출력 후 queue에 넣기 
        같은 노드의 연결된 다수의 정점 중에서 작은 정점부터 출력하기 위해 dfs는 내림차순으로, bfs는 오름차순으로 graph를 정렬함. 

### 시간복잡도 :
        0(n + e) : 인접 리스트로 구현하여 정점에 연결된 간선의 개수만큼 연산이 추가됨.

### 코드 :
```python
from collections import deque

n, m, v = map(int, input().split())

graph = [[] for _ in range(n+1)]

for i in range(m) :
    a, b = map(int, input().split())
    graph[a].append(b)
    graph[b].append(a)

for i in range(1, n+1) :
    graph[i].sort(reverse=True)

stack = []
visited = [False] * (n+1)
stack.append(v)

while len(stack) != 0 :
    element = stack.pop()
    if visited[element] == False :
        print(element, end=' ')
        visited[element] = True
        for i in graph[element]:
            stack.append(i)
print()

for i in range(1, n+1) :
    graph[i].sort()

visited = [False] * (n+1)
queue = deque([v])
visited[v] = True
print(v, end=' ')
while queue :
    element = queue.popleft()
    for i in graph[element] :
        if visited[i] == False :
            print(i, end=' ')
            queue.append(i)
            visited[i] = True
```