### 문제 풀이 핵심 아이디어 :
        재귀함수로 ! 풀기
        리스트에 있는 원소의 개수가 입력받은 m과 같다면 출력하고,
        리스트에 있는 원소를 한 개씩 꺼내면서 새로운 경우를 찾음.
        ex) n = 5, m = 3
            1) dfs 1 -> dfs 2 -> dfs 3 : [1, 2, 3] 출력 (dfs 4)
            2) 3 리스트에서 꺼냄. (dfs 4 끝 !)
            3) dfs 3가 아직 끝나지 않아 for문에 걸려 dfs 4 : [1, 2, 4] 출력
            4) 4 리스트에서 꺼냄.
            5) dfs 3가 아직 끝나지 않아 for문에 걸려 dfs 5 : [1, 2, 5] 출력 (dfs 3 끝 !)
            6) 2 리스트에서 꺼냄. 
            7) dfs 2가 아직 끝나지 않아 for문에 걸려 dfs 3 호출
            8) 새로운 dfs 호출 ... 반복

### 코드 :
```python
n, m = list(map(int, input().split()))

com = []


def dfs():
    if len(com) == m:
        print(' '.join(map(str, com)))
        return

    for i in range(1, n + 1) :
        if i not in com :
            com.append(i)
            dfs()
            com.pop()

dfs()
```
