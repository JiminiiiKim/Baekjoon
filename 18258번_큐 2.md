### 문제 풀이 핵심 아이디어 :
        queue의 현재 위치를 알려주는 cnt 변수를 만들어줌.
        push : append 해줌.
        pop : 가장 앞에 있는 거 출력해주고 cnt를 한 칸 뒤로 함.
        size : 리스트의 길이에서 현재 위치 빼줌.
        empty : 리스트의 길이와 현재 위치 같은지 체크함.
        front : cnt 위치의 원소 출력함.
        back : 리스트의 가장 마지막 원소 출력함.

### 코드 :
```python
from sys import stdin

input()
command = stdin.readlines()
queue = []
cnt = 0

for i in command :
    com = i.split()
    if com[0] == 'push' :
        queue.append(com[1])
    elif com[0] == 'pop' :
        if len(queue) > cnt :
            print(queue[cnt])
            cnt += 1
        else :
            print(-1)
    elif com[0] == 'size' :
        print(len(queue) - cnt)
    elif com[0] == 'empty' :
        if len(queue) == cnt :
            print(1)
        else :
            print(0)
    elif com[0] == 'front' :
        if len(queue) > cnt :
            print(queue[cnt])
        else :
            print(-1)
    elif com[0] == 'back' :
        if len(queue) > cnt :
            print(queue[-1])
        else :
            print(-1)
```
