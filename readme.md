# 有道词典命令行版

这是一个ruby脚本，用来在命令行中直接查询单词含义，免去打开软件或浏览器的麻烦。
支持英译中、中译英。

## 安装

```console
curl https://raw.githubusercontent.com/qhwa/Command-Line-Youdao-Dictionary/master/dict -O dict
chmod a+x dict
mv dict /usr/local/dict # 如果希望全局可以使用
```

## 使用方法

~~~console
dict <要查询的单词>
~~~

例如：

~~~console
dict cake
dict 蛋糕
~~~

## 截图

![image](https://user-images.githubusercontent.com/43009/29802165-4153d614-8ca6-11e7-823a-08f89553afdd.png)
