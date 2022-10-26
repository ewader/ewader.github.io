# ubuntu22.04安装gnome插件


ububtu22.04对gnome42进行了个性化的设置，好听点的话是个性化的设置，不好听的就是魔改。这样就导致用浏览器不能安装gnome插件。
<!--more-->
报一个莫名其妙的错误，大意就是没有安装什么服务，事实上是安装的了。

但是，虽然没法用浏览器安装，还是可以有别的方法的。 在google上搜索这个问题的时候，官方的论坛上有人给出的方法是下载一个应用商店，在那个应用商店里安装一个软件。 加上各种依赖等，都需要好几百M的空间了。

![apt-install-gnome-shell-extension-manager](https://cdn.staticaly.com/gh/ewader/img@master/20221022/apt-install-gnome-shell-extension-manager.1bh4yyxm6u8.webp)

后来又发现了其他的更简洁的方法，只需一行代码就搞定。
```
sudo apt install gnome-shell-extension-manager
```


打开这个软件，在搜索栏里搜索你要的插件安装即可。



