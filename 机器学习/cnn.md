使用Pytorch 搭建cnn
# 基本流程
加载数据->搭建模型->训练->测试
## 加载数据
```python
from torch.utils.data import DataLoader, Sampler
from torchvision import datasets,transforms
```
