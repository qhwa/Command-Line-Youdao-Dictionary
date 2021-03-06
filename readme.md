# 有道词典命令行版

这是一个ruby脚本，用来在命令行中直接查询单词含义，免去打开软件或浏览器的麻烦。
支持英译中、中译英。

## 安装

```shell
# 你可能需要一个代理服务器
wget https://raw.githubusercontent.com/qhwa/Command-Line-Youdao-Dictionary/master/dict
chmod a+x dict
mv dict /usr/local/bin/dict # 如果希望全局可以使用
```

可选: 发音功能需要安装 [mpg123](https://www.mpg123.de/)
<br/><small>(可以通过 [homebrew](https://brew.sh/), [apt-get](https://linux.die.net/man/8/apt-get) 等包管理工具安装)</small>

## 使用方法

1. 简单用法

    ```shell
    dict <要查询的单词>
    ```

    例如：

    ```shell
    dict cake
    dict 蛋糕
    ```

2. 发音

    英文的单词和词组可以发音，支持美式/英式发音。
    如需发音，需要先安装 [mpg123](https://www.mpg123.de/)

    ```shell
    dict -v give birth to
    ```

    ```shell
    # 英式发音 (default)
    dict -v -a 1 microscope

    # 美式发音
    dict -v -a 2 microscope
    ```

3. 完整命令行参数

    ```sh
    dict <word> [options]
        -v, --voice         play voice
        -a, --accent=acent  accent of voice, can either be `1` (UK) or `2` (US)
    ```

## demo

<img src="https://user-images.githubusercontent.com/43009/29802165-4153d614-8ca6-11e7-823a-08f89553afdd.png" width="500" />
