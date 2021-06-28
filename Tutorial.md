# Turorial



# requirement

软件：node.js + docsify

代码：Markdown 语法

# docsfy 安装和使用

* docsify 官网

    

    * GitHub <https://github.com/docsifyjs/docsify/>

        

    * documentation <https://docsify.js.org/#/>



## 安装步骤

1. win 下安装 `node.js`

    下载地址： <https://nodejs.org/>

    国内地址：<http://nodejs.cn/download/>

    安装成功后，命令行 `node -v` 显示版本号即安装成功

2. 安装 `docsify-cli`

    命令行 `npm i docsify-cli -g`

3. 使用 docsify

    ```
    第一次创建：
    docsify init
    
    启动 ：
    docsify serve
    
    特定端口启动
    docsify serve --port=8080
    可以在 http://127.0.0.1:8080/ 访问
    ```



## docsify 使用

详细的使用可以参考官网。



### 运行本项目

下载本项目后，直接项目根目录运行 `docsify serve` 即可。

```
或者特定端口
docsify serve --port=8080
浏览器 http://127.0.0.1:8080/ 访问
```



### 基本文件解释

*  `index.html`

    docsify 的配置文件，包括一些文档基本设置，引入的 CSS JS 文件等，如果在本项目上使用，可以忽略

* `SUMMARY.md`

    目录文件，新建的 md 文件需要在该文件内添加目录才能显示



# 本项目使用规约

见 [Specification](./Specification.md)

# docsify 语法

见 [syntax](/Syntax.md)



# 软件推荐

* Markdown 编辑器：

    typora <https://typora.io/>

    typora 上传图片：https://support.typora.io/Upload-Image/ 

    win 下可以 PicGo + gitee 上传图片

    

* GitHub Desktop：

    <https://desktop.github.com/>

