---
layout:     post
title:      "pytorch 安装及激励函数"
subtitle:   " \"pytorch installation and activate function\""
date:       2019-07-06 8:33:00
author:     "张凡"
header-img: "https://aerozf.oss-cn-beijing.aliyuncs.com/images/pytorch/Artificial_network.jpg"
catalog: true
tags:
    - pyorch
    - 神经网络
    - python
---

## 1、pytorch的安装
 
#### 1.1、首先进入pytorch官网

pytorch 官网网址：https://pytorch.org/，或者直接[点击我](https://pytorch.org/)进入官网

![](https://aerozf.oss-cn-beijing.aliyuncs.com/images/pytorch/20190706091452.png)
<div align="center" markdown="0"><font size="2">图1 pytorch官网首页</font> </div>

在该网页滚动鼠标向下移动，找到图中所示的pytorch安装辅助界面

![](https://aerozf.oss-cn-beijing.aliyuncs.com/images/pytorch/20190706091511.png)
<div align="center" markdown="0"><font size="2">图2 pytorch安装辅助界面</font> </div>

如图二所示：
   - 1、pytorch build 选择Stable（稳定版本）
   - 2、your OS 即选择你所安装的操作系统，一般都是Windows系统。请按照你实际所使用的系统选择。
   - 3、package 即选择要安装的方式，这里选择pip安装方式（因为据测试，这个安装速度最快）。
   - 4、language 即选择你所使用的python版本（我使用的是python3.6)
   - 5、cuda即显卡支持的版本，若无显卡，则选None
   
#### 1.2 查看显卡支持的版本
   - 1、打开电脑控制面板，找到 **NAVID控制面板**
   ![](https://aerozf.oss-cn-beijing.aliyuncs.com/images/pytorch/20190706101628.png)
   <div align="center" markdown="0"><font size="2">图3 控制面板页面</font> </div>
   
   - 2、双击打开 **NAVID控制面板**
   ![](https://aerozf.oss-cn-beijing.aliyuncs.com/images/pytorch/20190706101640.png)
   <div align="center" markdown="0"><font size="2">图4 NAVID面板首页</font> </div>

   - 3、在 **NAVID控制面板** 上部导航栏找到帮助 > 系统信息 ，在组件中找到NAVID.dll，cuda 后面显示数字的整数位即为cuda支持的版本（我的是9）
   
   ![](https://aerozf.oss-cn-beijing.aliyuncs.com/images/pytorch/QQ%E5%9B%BE%E7%89%8720190706101758.png)
   <div align="center" markdown="0"><font size="2">图5 NAVID cuda信息</font> </div>
   - 4、
   
#### 1.3 通过链接下载pytorch的.wheel文件

如上面提到的，选择好所有项目后，如图6所示，分别复制pip3 后面的两个链接，下载pytorch的.wheel文件（下载时间可能有点长，请耐心等待）。

![](https://aerozf.oss-cn-beijing.aliyuncs.com/images/pytorch/QQ%E5%9B%BE%E7%89%8720190706093805.png)
<div align="center" markdown="0"><font size="2">图6 pytorch下载链接</font> </div>

#### 1.4、pip安装pytorch

下载好两个wheel文件后，打开系统命令行（cmd），分别复制两个wheel文件的保存地址,在系统命令行中输入如下命令安装：
```
pip3 install wheel文件保存地址.wheel

例如：pip3 install F:\firefox_doenload\torch-1.1.0-cp36-cp36m-win_amd64.whl
```

把两个wheel文件分别进行如上操作后，pytorch就安装成功了

最后，来import测试一下是否成功。

![](https://aerozf.oss-cn-beijing.aliyuncs.com/images/pytorch/QQ%E5%9B%BE%E7%89%8720190706095229.png)
<div align="center" markdown="0"><font size="2">图7 测试pytorch是否安装成功</font> </div>

如果如图7所示，没有出现报错，那么恭喜你，pytorch安装成功。

## 2、pytorch常用的激励函数

#### 2.1、何为激励函数
   神经网络中的每个节点接受输入值，并将输入值传递给下一层。输入节点会将输入属性值直接传递给下一层（隐层或输出层）。在神经网络中，隐层和输出层节点的输入和输出之间具有函数关系，这个函数称为激励函数（Activation Function）[^1]。常见的激励函数有：
[^1]:[激励函数](https://baike.baidu.com/item/%E6%BF%80%E5%8A%B1%E5%87%BD%E6%95%B0/6477658?fr=aladdin)
   - relu
   - sigmoid
   - tanh
   - softplus
   
#### 2.2、为什么要引入激励函数
因为不使用激励函数的话，神经网络的每层都只是做线性变换，多层输入叠加后也还是线性变换。因为线性模型的表达能力不够，而激励函数可以引入非线性因素，这也是神经网络为什么这么智能的原因。

事实上，我们所处的现实世界就是非线性的。例如你要和朋友去外面看电影，并不是说了就能去的，至少由以下几个因素所影响：
   - 1、今天的天气
   - 2、你今天是否有空
   - 3、你朋友是否也有空
   - 4、电影票的价格
   - 5、是否有充足的电影票
   - 等等等等
  
但以上的几个因素对去看电影这个事件的影响程度是不同的（权重），对每个人而言，以上几个因素的权重值是不一样的，例如电影票价格对一些人来说影响不是很大（除非特别贵），但对另一些人影响比较大（例如手头刚好没多少钱了）。只有以上所有因素的影响乘于权重大于阈值（不同人阈值也不同）看电影这个时间才会发生。
> 例如你去看电影的阈值为12。以上五个因素对你而言权重分别为：0.1，0.3，0.3，0.2，0.1
> 影响值若分别为：10，20，20，15，10
> 则最后的影响值为：10x0.1+20x0.3+20x0.3+15x0.2+10x0.1=17 > 12
> 所以你今天可以去看电影（你朋友去不去不一定，若要考虑你和朋友一起去，那这个神经网络比这个更复杂一些）

#### 2.3、激励函数的图像
为了刚开始对激励函数有个直观的影响，我们先放出激励函数的图像。生成图像我们用 python中的matplotlib库。代码如下所示：
```python
import torch
import torch.nn.functional as F
from torch.autograd import Variable
import matplotlib.pyplot as plt

# fake data
x = torch.linspace(-5, 5, 200)  # x data (tensor), shape=(100, 1)
x = Variable(x)
x_np = x.data.numpy()   # numpy array for plotting

# following are popular activation functions
y_relu = torch.relu(x).data.numpy()
y_sigmoid = torch.sigmoid(x).data.numpy()
y_tanh = torch.tanh(x).data.numpy()
y_softplus = F.softplus(x).data.numpy() # there's no softplus in torch
# y_softmax = torch.softmax(x, dim=0).data.numpy() softmax is a special kind of activation function, it is about probability

# plt to visualize these activation function
plt.figure(1, figsize=(8, 6))
plt.subplot(221)
plt.plot(x_np, y_relu, c='red', label='relu')
plt.ylim((-1, 5))
plt.legend(loc='best')

plt.subplot(222)
plt.plot(x_np, y_sigmoid, c='red', label='sigmoid')
plt.ylim((-0.2, 1.2))
plt.legend(loc='best')

plt.subplot(223)
plt.plot(x_np, y_tanh, c='red', label='tanh')
plt.ylim((-1.2, 1.2))
plt.legend(loc='best')

plt.subplot(224)
plt.plot(x_np, y_softplus, c='red', label='softplus')
plt.ylim((-0.2, 6))
plt.legend(loc='best')

plt.show()
```

生成的图像如下所示：

![](https://morvanzhou.github.io/static/results/torch/2-3-1.png)
<div align="center" markdown="0"><font size="2">图8 常见激励函数图像</font> </div>

