---
layout:     post
title:      "博客发文教程"
subtitle:   " \"Blog post tutorial\""
date:       2019-07-02 18:33:00
author:     "张凡"
header-img: "/img/post-bg-2015.jpg"
catalog: true
tags:
    - 教程
    - markdown
---

> Hello world,hello blog. 


## 1、前言

今天花了一天的时间，博客就这样开通了

该博客的成功搭建，离不开[Hux](https://github.com/huxpro) Github Pages教程的帮助，在此感谢Hux和为了开源而努力的人们，正是因为你们的存在，才使得有更多的人能享受到计算机和互联网带来的便利。


## 2、如何发表自己的博客文章

- 1、在项目首页找到_post文件夹
![](https://chunlioss.oss-cn-beijing.aliyuncs.com/images/post.jpg)
找到_post文件夹后，点击进入

- 2、点击左上角Creat new file建立新文件夹
为了熟悉文件规则，先以已经发表的博文为例，如下图所示，点击打开已发表博文.md文件。
![](https://chunlioss.oss-cn-beijing.aliyuncs.com/images/openpost.jpg)
如下图所示为打开的博文.md文件展示出的效果，如图中红框所示为博文发文的基本框架，包含了博文的很多信息，红框所示表格必不可少。表格下方为博文的正文
![](https://chunlioss.oss-cn-beijing.aliyuncs.com/images/mdfile.jpg)
如下图所示为上图中.md文件在编辑状态下的截图
![](https://chunlioss.oss-cn-beijing.aliyuncs.com/images/editmdfile.jpg)

总之，新建的博文按照第一篇所示的博文的格式来编辑就可以了

## 3、本博客支持的博文格式
### 3.1、段落引用
段落语法如下所示：
```
> 这句话将被引用
```
效果如下所示

> 这句话将被引用

### 3.2、插入图片
插入图片的语法如下所示
```
![图片名称——这部分可留空](图片的网络地址)
例如：![嘿嘿](https://chunlioss.oss-cn-beijing.aliyuncs.com/images/5af27f751eedd9c0.gif)
```
显示效果如下所示：

![嘿嘿](https://chunlioss.oss-cn-beijing.aliyuncs.com/images/5af27f751eedd9c0.gif)

### 3.3、文本链接
如果你想在某段文本中插入链接，就可以使用文本链接。语法如下所示
```
[文本](文本中插入的链接)
例如：[去流浪](https://music.163.com/#/song?id=1344340338)
```

你听过周笔畅唱的流浪地球的主题曲《[去流浪](https://music.163.com/#/song?id=1344340338)》吗？可好听了

### 3.4、插入代码
如果你的博文中需要插入代码，可以使用如下语法使你的代码高亮，显示更美观
```
使用连续的三个反引号把代码包在中间，其中第一个连续的反引号后面加上所使用的代码语言，如下所示
    ```所使用的代码语言
    你的代码放在这里
    ```
    举个python代码的例子
    ```python
    import requests   #导入requests模块
    
    headers={"user-agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/74.0.3729.131 Safari/537.36"}
    url='http://www.baidu.com'
    req=rwquests.get(url,headers=headers)
    req.encoding=req.apparent_encoding
    if req.status==200:
        text=req.text
    else:
        text=''
        pass
    print(text)
    ```
```
上面所举例的代码高亮显示效果如下所示
~~~python
    import requests   #导入requests模块
    
    headers={"user-agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/74.0.3729.131 Safari/537.36"}
    url='http://www.baidu.com'
    req=rwquests.get(url,headers=headers)
    req.encoding=req.apparent_encoding
    if req.status==200:
        text=req.text
    else:
        text=''
        pass
    print(text)
~~~

### 3.5、插入无序列表
插入无序列表的语法如下所示
```
无序列表使用*或+或-标识
例如：
- 我是第一个无序列表
- 我是第二个无序列表
- 我是第三个无序列表
```
效果如下所示：
- 我是第一个无序列表
- 我是第二个无序列表
- 我是第三个无序列表

### 3.6、插入有序列表
插入有序列表的语法如下所示
```
有序列表为数字+小数点
例如：
1. 我是第一个有序列表
2. 我是第二个有序列表
3. 我是第三个有序列表
```
效果如下所示：
1. 我是第一个有序列表
2. 我是第二个有序列表
3. 我是第三个有序列表

### 3.7、插入表格
插入表格的语法如下所示：
```
| 左对齐 | 中间对齐 | 右对齐 |
| :---   |  :---:   |   ---: |
| 左1    |  中1     |  右1   |
| 左2    |  中2     |  右3   |
```
显示效果如下所示：


| 左对齐 | 中间对齐 | 右对齐 |
| :---   |  :---:   |   ---: |
| 左1    |  中1     |  右1   |
| 左2    |  中2     |  右3   |

### 3.8、插入视频
由于markdown没有插入视频的语法，故需要直接插入html代码来实现插入视频的效果了（很简单的），如下所示

```
插入视频的html代码如下所示
<div markdown="0">
<video id="video" controls="" width="400" height="300" preload="none" poster="视频封面图片地址">
<source id="mp4" src="视频地址">
</video>
</div>
```
效果如下所示：

<div markdown="0">
<video id="video" controls="" width="320" height="240" preload="none" poster="http://p2.music.126.net/tC1MuCpUBvJKzlIsxr2VbQ==/109951163841662048.jpg">
<source id="mp4" src="https://chunliblog.oss-cn-beijing.aliyuncs.com/videos/%E5%8E%BB%E6%B5%81%E6%B5%AA.mp4">
</video>
</div>

### 3.9、插入音频
由于markdown没有插入音频的语法，故需要直接插入html代码来实现插入音频的效果了（很简单的），如下所示

```
插入音频的html代码如下所示
<div markdown="0">
<audio id="audio" controls="" preload="none">
      <source id="mp3" src="音频地址" >
</audio></div>
```
效果如下所示：
<div markdown="0">
<audio id="audio" controls="" preload="none">
      <source id="mp3" src="https://chunliblog.oss-cn-beijing.aliyuncs.com/audios/%E5%8E%BB%E6%B5%81%E6%B5%AA.mp3">
</audio></div>

### 3.10、插入公式
插入公式要借助在线公式编辑器[LaTeX](https://www.codecogs.com/latex/eqneditor.php),该编辑区下方有公式链接，可以直接粘贴在markdown中。具体方法如下所示
```
1.打开LaTeX公式在线编辑网站
2.编辑好公示后，把生成的代码复制下来
3.代码按以下格式写到markdown编辑器中
<div markdown="0">+复制到生成的代码+</div>

以显示三行四列的矩阵为例：
<div markdown="0">
<a href="https://www.codecogs.com/eqnedit.php?latex=\begin{bmatrix}&space;1&space;&&space;2&space;&&space;3&space;&&space;\\&space;2&&space;0&&space;2&space;&&space;\\&space;3&&space;9&&space;4&&space;\end{bmatrix}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\begin{bmatrix}&space;1&space;&&space;2&space;&&space;3&space;&&space;\\&space;2&&space;0&&space;2&space;&&space;\\&space;3&&space;9&&space;4&&space;\end{bmatrix}" title="\begin{bmatrix} 1 & 2 & 3 & \\ 2& 0& 2 & \\ 3& 9& 4& \end{bmatrix}" /></a></div>
```

#### 3.10.1 矩阵示例
<div markdown="0">
<a href="https://www.codecogs.com/eqnedit.php?latex=\begin{bmatrix}&space;1&space;&&space;2&space;&&space;3&space;&&space;\\&space;2&&space;0&&space;2&space;&&space;\\&space;3&&space;9&&space;4&&space;\end{bmatrix}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\begin{bmatrix}&space;1&space;&&space;2&space;&&space;3&space;&&space;\\&space;2&&space;0&&space;2&space;&&space;\\&space;3&&space;9&&space;4&&space;\end{bmatrix}" title="\begin{bmatrix} 1 & 2 & 3 & \\ 2& 0& 2 & \\ 3& 9& 4& \end{bmatrix}" /></a></div>

#### 3.10.2 微积分示例
<div markdown="0">
<a href="https://www.codecogs.com/eqnedit.php?latex=\int_{0}^{20}\sin&space;3x&plus;\arctan&space;\frac{1}{x}dx" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\int_{0}^{20}\sin&space;3x&plus;\arctan&space;\frac{1}{x}dx" title="\int_{0}^{20}\sin 3x+\arctan \frac{1}{x}dx" /></a></div>

#### 3.10.3 求极限
<div markdown="0">
<a href="https://www.codecogs.com/eqnedit.php?latex=\lim_{x\rightarrow&space;0}\frac{x}{\sin&space;x}=1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\lim_{x\rightarrow&space;0}\frac{x}{\sin&space;x}=1" title="\lim_{x\rightarrow 0}\frac{x}{\sin x}=1" /></a></div>

#### 3.10.4 公式组
纳维-斯托克斯方程（大名鼎鼎的N-S方程）
<div markdown="0">
<a href="https://www.codecogs.com/eqnedit.php?latex=\begin{cases}&space;&&space;\rho&space;\frac{du}{dt}=-\frac{\partial&space;p}{\partial&space;x}&plus;\rho&space;X&plus;\mu&space;\Delta&space;u\\&space;&&space;\rho&space;\frac{d\nu&space;}{dt}=-\frac{\partial&space;p}{\partial&space;y}&plus;\rho&space;Y&plus;\mu&space;\Delta&space;\nu&space;\\&space;&&space;\rho&space;\frac{dw}{dt}=-\frac{\partial&space;p}{\partial&space;z}&plus;\rho&space;Z&plus;\mu&space;\Delta&space;w&space;\end{cases}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\begin{cases}&space;&&space;\rho&space;\frac{du}{dt}=-\frac{\partial&space;p}{\partial&space;x}&plus;\rho&space;X&plus;\mu&space;\Delta&space;u\\&space;&&space;\rho&space;\frac{d\nu&space;}{dt}=-\frac{\partial&space;p}{\partial&space;y}&plus;\rho&space;Y&plus;\mu&space;\Delta&space;\nu&space;\\&space;&&space;\rho&space;\frac{dw}{dt}=-\frac{\partial&space;p}{\partial&space;z}&plus;\rho&space;Z&plus;\mu&space;\Delta&space;w&space;\end{cases}" title="\begin{cases} & \rho \frac{du}{dt}=-\frac{\partial p}{\partial x}+\rho X+\mu \Delta u\\ & \rho \frac{d\nu }{dt}=-\frac{\partial p}{\partial y}+\rho Y+\mu \Delta \nu \\ & \rho \frac{dw}{dt}=-\frac{\partial p}{\partial z}+\rho Z+\mu \Delta w \end{cases}" /></a></div>
除这些数学公式之外，还可以书写很多类型的数学公式，限于篇幅就不在这里一一示范了。

### 3.11 文字处理
#### 3.11.1 普通文字处理
博文中可对文字进行处理，处理内容包含文字大小、格式、颜色、字体等等。
```
其中文字倾斜可以使用markdown自带语法，例如：
**这是加粗的文字**
*这是倾斜的文字*`
***这是斜体加粗的文字***
~~这是加删除线的文字~~等等。
但若要修改字体、文字大小、文字颜色，就要用到Html 代码了。
例如：
<div markdown="0"><font face="黑体">我是黑体字</font></div>
<div markdown="0"><font face="微软雅黑">我是微软雅黑</font> </div>
<div markdown="0"><font color="red">我是红色</font></div>
<div markdown="0"><font color="blue">我是蓝色</font></div>
<div markdown="0"><font size="5">我是文字尺寸</font> </div>
<div markdown="0"><font face="黑体" color="green" size="5">我是黑体，绿色，尺寸为5</font></div>
```
效果分别如下所示：
**这是加粗的文字**
*这是倾斜的文字*`
***这是斜体加粗的文字***
~~这是加删除线的文字~~
<div markdown="0"><font face="黑体">我是黑体字</font></div>
<div markdown="0"><font face="微软雅黑">我是微软雅黑</font> </div>
<div markdown="0"><font color="red">我是红色</font></div>
<div markdown="0"><font color="blue">我是蓝色</font></div>
<div markdown="0"><font size="5">我是文字尺寸</font> </div>
<div markdown="0"><font face="黑体" color="green" size="5">我是黑体，绿色，尺寸为5</font></div>

#### 3.11.2 特殊文字处理
###### 3.11.2.1 上标
```
例如：E = mc<sup>2</sup>
```
效果为：E = mc<sup>2</sup>

##### 3.11.2.2 下标
```
例如：Water: H<sub>2</sub>O
```
效果为：Water: H<sub>2</sub>O

##### 3.11.2.3 下划线
```
例如：<u>下划内容</u>

```
效果为：<u>下划内容</u>


### 3.12 脚注或引用
使用语法如下所示：
```
人有悲欢离合，月有阴晴圆缺.[^1]

[^1]: 《水调歌头》
```
效果如下所示：
人有悲欢离合，月有阴晴圆缺.[^1]

[^1]: 《水调歌头》

### 3.13 图片名称
使用语法如下所示：
```
<div align="center" markdown="0"><font size="字号大小">图片名称</font> </div>
例如：<div align="center" markdown="0"><font size="2">图片名称</font> </div>
```
效果如下所示：
<div align="center" markdown="0"><font size="2">图片名称</font> </div>

## 结语
记录生活，记录精彩

#### GFM task lists & Emoji & fontAwesome icon emoji & editormd logo emoji :editormd-logo-5x:

- [x] :smiley: @mentions, :smiley: #refs, [links](), **formatting**, and <del>tags</del> supported :editormd-logo:;
- [x] list syntax required (any unordered or ordered list supported) :editormd-logo-3x:;
- [x] [ ] :smiley: this is a complete item :smiley:;
- [ ] []this is an incomplete item [test link](#) :fa-star: @pandao;
- [ ] [ ]this is an incomplete item :fa-star: :fa-gear:;
    - [ ] :smiley: this is an incomplete item [test link](#) :fa-star: :fa-gear:;
    - [ ] :smiley: this is  :fa-star: :fa-gear: an incomplete item [test link](#);

#### 反斜杠 Escape

\*literal asterisks\*

[========]
### 科学公式 TeX(KaTeX)

$$E=mc^2$$

行内的公式$$E=mc^2$$行内的公式，行内的$$E=mc^2$$公式。

$$x > y$$

$$\(\sqrt{3x-1}+(1+x)^2\)$$

$$\sin(\alpha)^{\theta}=\sum_{i=0}^{n}(x^i + \cos(f))$$

多行公式：

```math
\displaystyle
\left( \sum\_{k=1}^n a\_k b\_k \right)^2
\leq
\left( \sum\_{k=1}^n a\_k^2 \right)
\left( \sum\_{k=1}^n b\_k^2 \right)
```
```katex
\displaystyle
    \frac{1}{
        \Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{
        \frac25 \pi}} = 1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {
        1+\frac{e^{-6\pi}}
        {1+\frac{e^{-8\pi}}
         {1+\cdots} }
        }
    }
```
```latex
f(x) = \int_{-\infty}^\infty
    \hat f(\xi)\,e^{2 \pi i \xi x}
    \,d\xi
```
### 分页符 Page break

> Print Test: Ctrl + P

[========]

### 绘制流程图 Flowchart

```flow
st=>start: 用户登陆
op=>operation: 登陆操作
cond=>condition: 登陆成功 Yes or No?
e=>end: 进入后台

st->op->cond
cond(yes)->e
cond(no)->op
```
[========]

### 绘制序列图 Sequence Diagram

```seq
Andrew->China: Says Hello
Note right of China: China thinks\nabout it
China-->Andrew: How are you?
Andrew->>China: I am good thanks!
```
### End
