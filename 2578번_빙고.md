### 문제 풀이 핵심 아이디어 또는 새롭게 알게 된 내용 :
        빙고가 되는 경우 
        1) 가로, 2) 세로, 3) 대각선 (왼쪽 위, 오른쪽 위)
        MC의 숫자와 본인의 숫자를 하나씩 비교해 MC와 숫자가 동일한 내 빙고판의 숫자는 0으로 바꿔줌.
        check 함수로 가로, 세로, 대각선의 경우를 하나씩 비교함.

### 코드의 시간복잡도와 그 이유 :
        O(5 * 5 * 5 * 5) : main의 for문으로 MC의 숫자와 본인의 숫자를 비교함.
        0(5 * 5) : 가로, 세로가 빙고인지 확인하기 위해 원소를 하나씩 확인함.
        0(5) : 대각선이 빙고인지 확인하기 위해 대각선의 원소를 하나씩 확인함.

### 코드 :
```python
a = []
for i in range(5):
    a.append(list(map(int, input().split())))

b = []
for i in range(5):
    b += list(map(int, input().split()))

def check():
    bingo = 0

    # 가로 확인
    for x in a :
        if x.count(0) == 5 :
            bingo += 1

    # 세로 확인
    for i in range(5) :
        y = 0
        for j in range(5) :
            if a[j][i] == 0 :
                y += 1
        if y == 5 :
            bingo += 1

    # 왼쪽 위 대각선 확인
    d1 = 0
    for i in range(5) :
        if a[i][i] == 0 :
            d1 += 1
    if d1 == 5 :
        bingo += 1

    # 오른쪽 위 대각선 확인
    d2 = 0
    for i in range(5) :
        if a[i][4 - i] == 0:
            d2 += 1
    if d2 == 5 :
        bingo += 1

    return bingo

for i in range(25) :
    for x in range(5) :
        for y in range(5) :
            if b[i] == a[x][y] :
                a[x][y] = 0

    result = check()
    if result >= 3 :
        print(i + 1)
        break
```
