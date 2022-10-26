# Matplotlib图表中文乱码的解决方案

不说很多废话了，直接上解决方案：

## 下载中文字体

其实不下载也没事，因为系统自带的也有中文字体，我只是没有操作最后一步，导致出来的还是乱码，以为没有中文字体呢。代码如下：
```bash
sudo pacman -S noto-fonts-cjk adobe-source-han-sans-cn-fonts adobe-source-han-serif-cn-fonts
```
系统安装一个思源字体也是很不错的，这个字体还是很漂亮的。

## 在代码中引入

```bash
import matplotlib.pyplot as plt
plt.rcParams["font.sans-serif"]=["Source Han Serif CN"] 
plt.rcParams["axes.unicode_minus"]=False
```
现在试一下，是不是中文了？

![Figure_1](https://cdn.staticaly.com/gh/ewader/img@master/20221023/Figure_1.qkhuhiv1jao.webp)

如果还不是中文，清除一下缓存即可，代码：
```bash
rm -r ~/.cache/matplotlib
```

