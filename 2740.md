### 문제 풀이 핵심 아이디어 또는 새롭게 알게 된 내용 :
        리스트를 활용해 A, B를 행렬 형태로 바꾸어주고,
        행, 열을 고정시켜 위치에 맞게 원소들의 곱을 더해줘 
        새로운 행렬의 원소가 만들어지면 하나씩 출력함.

### 코드의 시간복잡도와 그 이유 :
        O(N*K*M) : 삼중 for문을 돌면서 모든 원소들을 한 번씩 거쳐야 하기 때문

### 코드 :
```python
N, M = map(int, input().split())
A = []
for i in range(N) :
    A.append(list(map(int, input().split())))
    
M, K = map(int, input().split())
B = []
for i in range(M) :
    B.append(list(map(int, input().split())))

element = 0

for i in range(N) :
    for j in range(K) :
        for k in range(M) :
            element += (A[i][k] * B[k][j])
        print(str(element), end=' ')
        element = 0
    print('')
```
