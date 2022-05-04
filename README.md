# algorithm-assignment

### 선택 정렬

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

파이썬의 내장되어있는 sort함수는 오름차순으로 정렬을 한다. 이 코드는 오름차순으로 정렬돼 있는 것을 내림차순으로 정렬하는 것이다.

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

역으로 정렬했기 때문에 이미 내림차순으로 정렬 돼있다. 시간이 0초가 걸린다.

