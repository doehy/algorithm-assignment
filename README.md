# algorithm-assignment

### 선택 정렬
선택 정렬이란 데이터가 무작위로 여러 개 있을 때, 이 중에서 가장 작은 데이터를 선택해 맨 앞에 있는 데이터와 바꾸고, 그다음 작은 데이터를 선택해 앞에서 두 번째 데이터와 바꾸는 과정을 반복하는 것이다.
선택정렬의 시간 복잡도는 O(N^2)이다. 간단하게 생각하면 소스코드에서 2중 반복문이 사용되기 때문이다.
#### 정렬된 데이터
```
import time

start = time.time()

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num = len(num_list)
num_list.sort()

for i in range(0,num-1):
    for j in range(i+1,num):
        if num_list[i] < num_list[j]:
            num_list[i],num_list[j] = num_list[j],num_list[i]

print(num_list)
print("time :", time.time()-start)
```
![선택정렬_정렬된](https://user-images.githubusercontent.com/87864025/166664538-eda159e5-a92c-4ad5-8231-3e6611fb06e5.PNG)

파이썬의 내장되어있는 sort함수는 오름차순으로 정렬을 합니다. 이 코드는 오름차순으로 정렬돼 있는 것을 내림차순으로 정렬하는 것입니다.

#### 역으로 정렬된 데이터
```
import time

start = time.time()

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num_list.sort(reverse=True)
num = len(num_list)

for i in range(0,num-1):
    for j in range(i+1,num):
        if num_list[i] < num_list[j]:
            num_list[i],num_list[j] = num_list[j],num_list[i]

print(num_list)
print("time :", time.time()-start)
```
![선택정렬_역정렬된](https://user-images.githubusercontent.com/87864025/166665352-7d29c330-7e23-4a6f-a762-21e241f777c7.PNG)

역으로 정렬했기 때문에 이미 내림차순으로 정렬 돼있습니다. 그러므로 시간이 0초가 걸립니다.

#### 랜덤 데이터
```
import time
import random

start = time.time()

num_list= [32,512 , 128, 131072, 64, 524288, 2048, 32768, 8192, 16384,4096 , 65536,256 , 262144,1024 , 1048576]

num = len(num_list) 

for i in range(0,num-1):
    for j in range(i+1,num):
        if num_list[i] < num_list[j]:
            num_list[i],num_list[j] = num_list[j],num_list[i]

print(num_list)

print("time :", time.time()-start)
```

![선택정렬_랜덤정렬](https://user-images.githubusercontent.com/87864025/166863961-9965a04b-82af-4742-9167-fc21cf7b0aea.PNG)

데이터는 제가 스스로 정렬한 것 입니다.

* * *

### 삽입 정렬
선택 정렬에 비해 구현 난이도가 높은 편이지만 선택 정렬에 비해 실행 시간 측면에서 더 효율적인 알고리즘이다. 특히 삽입 정렬은 필요할 때만 위치를 바꾸므로 데이터가 거의 정렬 되어 있을 때 훨씬 효율적이다. 선택 정렬과 마찬가리고 시간복잡도는 반복문이 2번 중첩되어 사용됐기 때문에 O(N^2)이다.

#### 정렬된 데이터
```
import time

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num = len(num_list)
num_list.sort()
start = time.time()
for i in range(1,num):
    for j in range(i,0,-1): #end+1까지 감소한다.
        if num_list[j] < num_list[j-1]:
            num_list[j],num_list[j-1] = num_list[j-1],num_list[j]
        else:
            break
print(num_list)
print("time :", time.time()-start)
```

![삽입정렬_정렬된](https://user-images.githubusercontent.com/87864025/166866071-5fa0f015-f29f-40af-aeac-d53abae3ee0a.PNG)

#### 역으로 정렬된 데이터
```
import time

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num = len(num_list)
num_list.sort(reverse=True)
start = time.time()
for i in range(1,num):
    for j in range(i,0,-1): #end+1까지 감소한다.
        if num_list[j] < num_list[j-1]:
            num_list[j],num_list[j-1] = num_list[j-1],num_list[j]
        else:
            break
print(num_list)
print("time :", time.time()-start)
```

![삽입정렬_역정렬](https://user-images.githubusercontent.com/87864025/166866220-f8cb3f52-ad99-4508-90e6-ed70000b4115.PNG)

#### 랜덤 데이터
```
import time

num_list= [32,512 , 128, 131072, 64, 524288, 2048, 32768, 8192, 16384,4096 , 65536,256 , 262144,1024 , 1048576]
num = len(num_list)

start = time.time()
for i in range(1,num):
    for j in range(i,0,-1): #end+1까지 감소한다.
        if num_list[j] < num_list[j-1]:
            num_list[j],num_list[j-1] = num_list[j-1],num_list[j]
        else:
            break
print(num_list)
print("time :", time.time()-start)
```

![삽입정렬_랜덤](https://user-images.githubusercontent.com/87864025/166866717-da811a49-4443-475e-9a39-335ed0af9c29.PNG)

* * *

### 퀵 정렬
정렬 알고리즘 중에서 가장 많이 사용되는 알고리즘이다. 데이터가 정렬되어 있다면 최악의 경우 시간 복잡도가 O(N^2)이 나오지만 데이터가 정렬되어 있지 않다면 O(NlogN)이 나오는 정렬이다.

#### 정렬된 데이터
```
import time

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num_list.sort()
start = time.time()

def quick_sort(array,start,end):
    if start >= end: #원소가 1개인 경우 종료
        return
    pivot = start #피벗은 첫 번째 원소
    left = start +1
    right = end
    while left <= right:
        # 피벗보다 큰 데이터를 찾을 때까지 반복
        while left <= end and array[left] <= array[pivot]:
            left += 1
        # 피벗보다 작은 데이터를 찾을 때까지 반복
        while right > start and array[right] >= array[pivot]:
            right -= 1
        if left > right:
            array[right], array[pivot] = array[pivot], array[right]
        else:
            array[left],array[right] = array[right],array[left]
    # 분할 이후 왼쪽 부분과 오른쪽 부분에서 각각 정렬 수행
    quick_sort(array,start,right-1)
    quick_sort(array,right+1,end)

quick_sort(num_list,0,len(num_list)-1)
print(num_list)
print("time :", time.time()-start)
```

![퀵정렬_정렬된](https://user-images.githubusercontent.com/87864025/166867995-8baff084-2651-4b84-b1da-054f13f03e78.PNG)

#### 역으로 정렬된 데이터

```
import time

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num_list.sort(reverse=True)
start = time.time()

def quick_sort(array,start,end):
    if start >= end: #원소가 1개인 경우 종료
        return
    pivot = start #피벗은 첫 번째 원소
    left = start +1
    right = end
    while left <= right:
        # 피벗보다 큰 데이터를 찾을 때까지 반복
        while left <= end and array[left] <= array[pivot]:
            left += 1
        # 피벗보다 작은 데이터를 찾을 때까지 반복
        while right > start and array[right] >= array[pivot]:
            right -= 1
        if left > right:
            array[right], array[pivot] = array[pivot], array[right]
        else:
            array[left],array[right] = array[right],array[left]
    # 분할 이후 왼쪽 부분과 오른쪽 부분에서 각각 정렬 수행
    quick_sort(array,start,right-1)
    quick_sort(array,right+1,end)

quick_sort(num_list,0,len(num_list)-1)
print(num_list)
print("time :", time.time()-start)
```

![퀵정렬_역으로정렬](https://user-images.githubusercontent.com/87864025/166868167-9f48d82a-bb46-4d2a-abef-6c448b1b5540.PNG)

#### 랜덤 데이터

```
import time

num_list= [32,512 , 128, 131072, 64, 524288, 2048, 32768, 8192, 16384,4096 , 65536,256 , 262144,1024 , 1048576]

start = time.time()

def quick_sort(array,start,end):
    if start >= end: #원소가 1개인 경우 종료
        return
    pivot = start #피벗은 첫 번째 원소
    left = start +1
    right = end
    while left <= right:
        # 피벗보다 큰 데이터를 찾을 때까지 반복
        while left <= end and array[left] <= array[pivot]:
            left += 1
        # 피벗보다 작은 데이터를 찾을 때까지 반복
        while right > start and array[right] >= array[pivot]:
            right -= 1
        if left > right:
            array[right], array[pivot] = array[pivot], array[right]
        else:
            array[left],array[right] = array[right],array[left]
    # 분할 이후 왼쪽 부분과 오른쪽 부분에서 각각 정렬 수행
    quick_sort(array,start,right-1)
    quick_sort(array,right+1,end)

quick_sort(num_list,0,len(num_list)-1)
print(num_list)
print("time :", time.time()-start)
```

![퀵정렬_랜덤](https://user-images.githubusercontent.com/87864025/166868574-d83f40ba-98cc-4636-a701-25f778eea172.PNG)

* * *
### 버블 정렬
선택정렬을 거꾸로 하는 것이라고 보면 된다. 그러므로 선택정렬과 똑같이 시간 복잡도는 O(N^2)이다.
#### 정렬된 데이터
```
import time

start = time.time()

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num = len(num_list)
num_list.sort()


for i in range(len(num_list) - 1, 0, -1):
        for j in range(i):
            if num_list[j] > num_list[j + 1]:
                num_list[j], num_list[j + 1] = num_list[j + 1], num_list[j]

print(num_list)
print("time :", time.time()-start)
```

![버블정렬_정렬된](https://user-images.githubusercontent.com/87864025/166870150-17e0a850-af52-49d5-b6fa-055d7ee367e7.PNG)

#### 역으로 정렬된
```
import time

start = time.time()

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num = len(num_list)
num_list.sort(reverse=True)


for i in range(len(num_list) - 1, 0, -1):
        for j in range(i):
            if num_list[j] > num_list[j + 1]:
                num_list[j], num_list[j + 1] = num_list[j + 1], num_list[j]

print(num_list)
print("time :", time.time()-start)
```

![버블정렬_역정렬](https://user-images.githubusercontent.com/87864025/166870266-64cd2e65-f84d-4963-945b-a8a0b575c816.PNG)

#### 랜덤 데이터
```
import time

start = time.time()

num_list= [32,512 , 128, 131072, 64, 524288, 2048, 32768, 8192, 16384,4096 , 65536,256 , 262144,1024 , 1048576]

for i in range(len(num_list) - 1, 0, -1):
        for j in range(i):
            if num_list[j] > num_list[j + 1]:
                num_list[j], num_list[j + 1] = num_list[j + 1], num_list[j]

print(num_list)
print("time :", time.time()-start)
```

![버블정렬_랜덤](https://user-images.githubusercontent.com/87864025/166870449-c5a90891-9982-482c-8ba6-928f62872287.PNG)

### 쉘정렬
일정 간격 떨어져 있는 원소들끼리 부분집합을 구성한 후 각 부분집합의 원소들에 대해서 삽입 정렬을 수행하되,간격을 줄여가며 삽입 정렬을 반복하여 전체 원소들을 정렬하는 방식의 정렬 알고리즘이다. 삽입 정렬을 보완한 알고리즘이기 때문에 최악의 경우의 시간 복잡도는 O(N^2)이 나오지만 평균적으로는 O(N^1.5)가 나온다.
#### 정렬된 데이터
```
import time

start = time.time()

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num_list.sort()

def shell_sort(arr):
    N = len(arr)
    h = N // 2
    while h > 0:
        for i in range(h, N):
            temp = arr[i]
            j = i - h
            while j >= 0 and arr[j] > temp:
                arr[j + h] = arr[j]
                j -= h
            arr[j + h] = temp
        h //= 2
 
    print(num_list)
 
shell_sort(num_list)
print("time :", time.time()-start)
```

![쉘정렬_정렬된](https://user-images.githubusercontent.com/87864025/166871609-ff620e00-32f1-4196-b190-28fcd8659693.PNG)

#### 역으로 정렬
```
import time

start = time.time()

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num_list.sort(reverse=True)

def shell_sort(arr):
    N = len(arr)
    h = N // 2
    while h > 0:
        for i in range(h, N):
            temp = arr[i]
            j = i - h
            while j >= 0 and arr[j] > temp:
                arr[j + h] = arr[j]
                j -= h
            arr[j + h] = temp
        h //= 2
 
    print(num_list)
 
shell_sort(num_list)
print("time :", time.time()-start)
```

![쉘정렬_역정렬](https://user-images.githubusercontent.com/87864025/166871703-c01e3d9d-b9c3-453e-a1c4-c1def734e6cc.PNG)

#### 랜덤 데이터
```
import time

start = time.time()

num_list= [32,512 , 128, 131072, 64, 524288, 2048, 32768, 8192, 16384,4096 , 65536,256 , 262144,1024 , 1048576]
def shell_sort(arr):
    N = len(arr)
    h = N // 2
    while h > 0:
        for i in range(h, N):
            temp = arr[i]
            j = i - h
            while j >= 0 and arr[j] > temp:
                arr[j + h] = arr[j]
                j -= h
            arr[j + h] = temp
        h //= 2
 
    print(num_list)
 
shell_sort(num_list)
print("time :", time.time()-start)
```
![쉘 정렬_랜덤](https://user-images.githubusercontent.com/87864025/166886549-e729829e-a21a-496b-82a3-52940caa6acb.PNG)

* * *

### 힙 정렬
최대 힙 트리나 최소 힙 트리를 구성해 정렬을 하는 방법이다.
시간 복잡도는 평균적으로 O(nlog밑2N)이 걸린다.
#### 정렬된 데이터
```
import time

start = time.time()

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num_list.sort()

def heap_sort(array):
    n = len(array)
    for i in range(n):
        c = i
        while c != 0:
            r = (c-1)//2
            if (array[r] < array[c]):
                array[r], array[c] = array[c], array[r]
            c = r
    for j in range(n-1, -1, -1):
        array[0] , array[j] = array[j], array[0]
        r = 0
        c = 1
        while c<j:
            c = 2*r +1
            
            if (c<j-1) and (array[c] < array[c+1]):
                c += 1
           
            if (c<j) and (array[r] < array[c]):
                array[r], array[c] = array[c], array[r]
            r=c
    print(array)
heap_sort(num_list)
print("time :", time.time()-start)
```
![힙정렬_정렬](https://user-images.githubusercontent.com/87864025/166887119-09330695-96cd-4ae7-b636-1561f9ff33dc.PNG)

#### 역으로 정렬된
```
import time

start = time.time()

num_list= []

for i in range(5,21):
    n = pow(2,i)
    num_list.append(n)

num_list.sort(reverse=True)

def heap_sort(array):
    n = len(array)
    for i in range(n):
        c = i
        while c != 0:
            r = (c-1)//2
            if (array[r] < array[c]):
                array[r], array[c] = array[c], array[r]
            c = r
    for j in range(n-1, -1, -1):
        array[0] , array[j] = array[j], array[0]
        r = 0
        c = 1
        while c<j:
            c = 2*r +1
            
            if (c<j-1) and (array[c] < array[c+1]):
                c += 1
           
            if (c<j) and (array[r] < array[c]):
                array[r], array[c] = array[c], array[r]
            r=c
    print(array)
heap_sort(num_list)
print("time :", time.time()-start)
```

![힙정렬_역정렬](https://user-images.githubusercontent.com/87864025/166887271-6c8f13b1-371d-42dd-9d6c-6a1fc0b1280d.PNG)

#### 랜덤 데이터
```
import time

start = time.time()

num_list= [32,512 , 128, 131072, 64, 524288, 2048, 32768, 8192, 16384,4096 , 65536,256 , 262144,1024 , 1048576]
def heap_sort(array):
    n = len(array)
    for i in range(n):
        c = i
        while c != 0:
            r = (c-1)//2
            if (array[r] < array[c]):
                array[r], array[c] = array[c], array[r]
            c = r
    for j in range(n-1, -1, -1):
        array[0] , array[j] = array[j], array[0]
        r = 0
        c = 1
        while c<j:
            c = 2*r +1
            
            if (c<j-1) and (array[c] < array[c+1]):
                c += 1
           
            if (c<j) and (array[r] < array[c]):
                array[r], array[c] = array[c], array[r]
            r=c
    print(array)
heap_sort(num_list)
print("time :", time.time()-start)
```
![힙정렬_랜덤](https://user-images.githubusercontent.com/87864025/166887429-605fa46b-8bc7-4fa9-8f40-dae82c35fc2e.PNG)






