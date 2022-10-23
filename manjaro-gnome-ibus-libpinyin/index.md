# Manjaro gnome下安装ibus拼音输入法

在ubuntu下使用习惯了IBUS输入法，换成manjaro之后，还是习惯性的希望继续使用，毕竟在Gnome桌面下，IBUS输入法使用起来更方便。配合上ibus-libpinyin，开启云词库之后，是用来真的很爽很爽。
<!--more-->


但是设置半天，托盘里总是出现不了ibus的图标。不得已换成fcitx5。这个输入法其实也可以，只不过有如下的毛病。

第一，在gnome的查询框里输入中文，不显示候选的词语，
第二，在某些个别的程序中无法输入中文，表现为切换成中文后，程序闪退。
经过一番的折腾，看wiki等，终于是把这个输入法整好了，记录以下折腾的过程。

## 首先安装输入法

```bash
$ pacman -S ibus
$ pacman -S ibus-libpinyin
```
然后，设置-键盘-输入源 把libpinyin添加进去。重启，托盘有图标了吧？
![截图-2022-10-05-17-09-55](https://cdn.staticaly.com/gh/ewader/img@master/20221022/截图-2022-10-05-17-09-55.2qffux8w2i40.webp)

## 第二种方法 

这种方法更简单一些，打开，**Manjaro hello**,选择，**Applications**。在选择**额外的语言支持**。点击升级。安装玩就可以了。

![截图-2022-10-05-17-10-53](https://cdn.staticaly.com/gh/ewader/img@master/20221022/截图-2022-10-05-17-10-53.3hm9rgsdxie0.webp)

