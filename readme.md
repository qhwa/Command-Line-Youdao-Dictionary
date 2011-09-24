# 有道词典命令行版

这是一个ruby脚本，用来在命令行中直接查询单词含义，免去打开软件或浏览器的麻烦。
支持英译中、中译英。

## 使用方法

  ~~~
  ./dict <要查询的单词>
  ~~~

例如：
  
  ~~~shell
  ./dict cake
  ./dict 蛋糕
  ~~~

建议用alias简化，例如在$HOME/.bashrc或$HOME/.profile中加入
~~~alias d="/path/to/dict"~~~

