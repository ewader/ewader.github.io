# 使用Matplotlib画一个折线图

Matplotlib是python的一个第三方数学绘图库，通过它可以绘制出各种各样优美的，令人惊叹的图形。

## 首先，安装Matplotlib
```bash
python3 -m install --user matplotlib
```
## 绘制一个简单的折线图
我们来绘制这样一个图，x轴表示自然数，Y轴是这个自然数的平方数，折线代表的是坐标值。用matplotlib处理起来就很简单。
```python
import matplotlib.pylot as plt
s = [1, 4, 9, 16, 25]
fig, ax = plt.subplots()
ax.plot(s)
plt.show()
```
运行一下，是不是很激动，一个漂亮的图表就出现了。
![Figure_2](https://cdn.staticaly.com/gh/ewader/img@master/20221023/Figure_2.6ku0iu1nsgg0.webp)

变量fig表示的是整张图片，ax表示的图片中的各个图表。我们这么设计代码的好处在于，这个代码很容易修改，增加一些其他的项目来修饰图表，让图表的内容更加丰富，另外我们发现，这样绘制出来的图表的数据有些是不正确的，比如4.0的平方在图上指向的是25,因此我们还需要对图表进行修正，并增加图表的标签。
```python
import matplotlib.pylot as plt
plt.rcParams["font.sans-serif"]=["Source Han Serif CN"] 
plt.rcParams["axes.unicode_minus"]=False
i=[1,2,3,4,5]
s = [1, 4, 9, 16, 25]
fig, ax = plt.subplots()
ax.plot(i,s, linewidth=3)
ax.set_title("平方数", fontsize=24)
ax.set_xlabel("值",fontsize=14)
ax.set_ylabel("值的平方",fontsize=14)
plt.show()
```

代码的第二三行我们设置了显示标题标签等中文的设置，如果不设置的话，会显示方块乱码，详细的文章可以参考我之前的文章

较上面的两块代码，下面的代码我们仅仅是多了一些定义，比如x坐标，折线的尺寸，每个坐标显示的标题等。

