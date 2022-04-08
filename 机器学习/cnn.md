# pytorch

+ Pytorch 中最重要的就是variable模块，该模块集成了围绕一个张量所有的操作，包括前向传播、后向传播的各种求偏导数的数值
+ Pytorch 所有的网络在nn包里
+ Pytorch 计算GPU和CPU切换很快，直接使用x.cuda()即可


# 卷积神经网络

 使用Pytorch 搭建cnn

# 基本流程

导入包->数据预处理->加载数据->搭建模型->训练->测试

## 导入包
```python
import torch
from torch.autograd import Variable # 数据类型模块
import numpy as np
import torch.nn as nn #神经网络模块
from torchvision import datasets,transforms # 图像的各种功能函数
```

## 数据预处理

因为输入的图片尺寸不一的，需要将其调整到一个尺寸。
### train data
+ 图片随机裁剪再resize 到固定尺寸
+ 灰度范围0-255到0-1
+ 把灰度范围从0-1变换到[X1,X2]之间（这是对整个数据集的灰度分布进行统计后得到的灰度的上下限，这样一来就是能使灰度分布更均匀，差异更大）
+ 也可以添加一些数据增广的手段，用来提高训练集的泛化能力，比如水平/垂直翻转，旋转， 缩放，裁剪，剪切，平移，改变对比度，色彩抖动，添加噪声等。
```python
transforms.RandomResizedCrop(input_size, scale=(0.7, 1)),  # 图像进行随机裁剪后再resize成固定大小
transforms.ToTensor(),  # 把灰度范围从0-255变换到0-1之间
transforms.Normalize([0.4864, 0.4533, 0.4154], [0.2625, 0.2558, 0.2586])  # 把灰度范围从0-1变换到[X1,X2]之间
```
### validation data
缩放然后裁剪，调整灰度分布即可
```python
ransforms.Resize(input_size),  # 图像短边长度变为input_size
transforms.CenterCrop(input_size),  # 从正中间剪正方形
transforms.ToTensor(),
transforms.Normalize([0.4864, 0.4533, 0.4154], [0.2625, 0.2558, 0.2586])
```



## 加载数据
建立数据集迭代器：

```python
from torch.utils.data import DataLoader, Sampler
from torchvision import datasets,transforms
```
