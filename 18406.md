### 문제 풀이 핵심 아이디어 또는 새롭게 알게 된 내용 :
        자릿수를 기준으로 반으로 나눠 좌, 우 합이 같은지를 확인하는 문제
        점수 N의 길이를 반으로 나눠 문자열의 인덱스를 활용해 
        원소가 해당하는 위치에 맞게 좌, 우 합을 각각 더해줌.

### 코드의 시간복잡도와 그 이유 :
        O(N/2) : N의 길이에서 절반을 나눠 합을 구해주므로

### 코드 :
```python
N = input()
sum1 = 0
sum2 = 0

for i in range(len(N)//2) :
    sum1 += int(N[i])
    sum2 += int(N[len(N) // 2 + i])

if sum1 == sum2 :
    print("LUCKY")
else :
    print("READY")
```
