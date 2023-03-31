### 문제 풀이 핵심 아이디어 또는 새롭게 알게 된 내용 :
        규칙성 파악하기 !
        1) 휴가 일수를 주기로 나누어 L일 만큼 곱해줌.
        2) 휴가 일수를 주기로 나눈 나머지를 더해줌.
            2-1) 나머지가 L보다 큰 경우는 L을 더해줌.
            2-2) 나머지가 L보다 작은 경우는 나머지를 더해줌.

### 코드의 시간복잡도와 그 이유 :
        O(N) 
        T : case의 개수, case의 횟수만큼 연산을 반복하므로

### 코드 :
```python
num = 1

while True :
    L, P, V = map(int, input().split())
    if L == 0 and P == 0 and V == 0 :
        break
    D = V % P
    if D > L :
        D = L
    print("Case %d: %d" % (num, V // P * L + D))
    num += 1
```
