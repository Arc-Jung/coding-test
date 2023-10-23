# coding-test

### 2022-04-15 Arc-Jung

## 프로그래머스

### 약수의 갯수와 덧셈

> https://programmers.co.kr/learn/courses/30/lessons/77884

```python
def solution(left, right):
    cal(left)
    result = 0
    
    for i in range(left, right + 1):
        number = cal(i)
        length = len(number) 
        if length % 2 == 0 :
            result = result + i
        else :
            result = result - i
        print("result : ", result)
    
    return result
            
                
    
def cal(left):
    left_num = []
    
    for i in range(1, left + 1):
        if left % i == 0 or left / i == 1 :
                left_num.append(i)
    
    return left_num
```

### 모의고사

> https://programmers.co.kr/learn/courses/30/lessons/42840

```python
def solution(answers):
    first = [1, 2, 3, 4, 5] * 2000
    second = [2, 1, 2, 3, 2, 4, 2, 5] * 2000
    third = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5] * 2000
    
    first_rank = 0
    second_rank = 0
    third_rank = 0
    top = 0
    result = []
    
    for i in range(0, len(answers)):
        
        if first[i] == answers[i] :
            first_rank = first_rank + 1
        if second[i] == answers[i] :
            second_rank = second_rank + 1
        if third[i] == answers[i] :
            third_rank = third_rank + 1
        
    print(first_rank, second_rank, third_rank)
    
    max_list = []
    max_list.append(first_rank)
    max_list.append(second_rank)
    max_list.append(third_rank)
    top = max(max_list)
        
    print("top : ", top)
        
    if top == first_rank :
        result.append(1)
    if top == second_rank :
        result.append(2)
    if top == third_rank :
        result.append(3)
    
    result = list(set(result))
    result.sort
    print(result)
    
    
    return result
```

### K번째수

> https://programmers.co.kr/learn/courses/30/lessons/42748

```python
def solution(array, commands):
    answer = []
    
    for i in range(0, len(commands)):
        array_index = commands[i]
        sli = array[array_index[0]-1:array_index[1]]
        sli.sort()
        pop = array_index[2]
        result = sli[pop - 1]
        answer.append(result)
        
    return answer
```

### 가장 가까운 같은 글자

> https://school.programmers.co.kr/learn/courses/30/lessons/142086
```python
def solution(s):
    answer = []
    for i in range(len(s)):
        for j in range(i):
            if s[i] == s[j] and s[i] not in s[j+1:i]:
                answer.append(i-j)
                break
        else:
            answer.append(-1)
    return answer
```
