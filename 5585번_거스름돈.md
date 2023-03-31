### 문제 풀이 핵심아이디어 또는 새롭게 알게 된 내용:
        greedy algorithm 
        큰 수부터 차례대로 나누어 잔돈을 최소화하도록 한다.

### 코드의 시간복잡도와 그 이유:
        O(T) 
        T : list의 길이, T번 만큼 for문 반복

### 코드:
```python
money = 1000 - int(input())

money_list = [500, 100, 50, 10, 5, 1]
money_count = 0
for i in money_list:
    money_count += (money // i)
    money %= i

print(money_count)
```
