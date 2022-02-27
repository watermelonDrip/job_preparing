1. SGD
2. SGD with momentum
3. Adagrad: learning rate 加分母，越迭代越小
4. RMSProp
5. Adam

## 为什么做Optimization
找到一个theta,可以让training data所有的数据里算出来的loss function 最小。

on-line learning: 每个time step 只看到一个（x,y)
off-line learning: 每个time step 用所有的都(x,y)

## 帮助optimzation (增加随机性）（鼓励model 做exploration)
1. shuffling
2. dropput
3. gradient noise
4. normalization
5. regularization
6. 
