# 输入包括两个正整数a,b(1 <= a, b <= 1000),输入数据包括多组。输出a+b的结果

```python
def sum_(a, b):
    return a + b


if __name__ == '__main__':
    while(1):
        try:
            input_ = [int(x) for x in input().strip().split()]
            print(sum_(input_[0], input_[1]))
        except:
            break
```

#  输入第一行包括一个数据组数t(1 <= t <= 100), 接下来每行包括两个正整数a,b(1 <= a, b <= 1000)


```python
def sum_(a, b):
    return a + b


if __name__ == '__main__':
    while(1):
        try:
            t = int(input().strip())
            for _ in range(t):
                [a,b] = [int(x) for x in input().strip().split()]
                print(sum_(a, b))
        except:
            break

```


#
```python
while True:
    a,b=map(int,input().split())
    if a==0 and b==0:
        break
    print(a+b)
```


# 输入数据包括多组。每组数据一行,每行的第一个整数为整数的个数n(1 <= n <= 100), n为0的时候结束输入。接下来n个正整数,即需要求和的每个正整数。


```python
while True:
    num_array = list(map(int, input().split()))
    if num_array[0] != 0:
        sum = 0
        for i in range(1, len(num_array)):
            sum += num_array[i]
    else:
        break
    print(sum)
```
