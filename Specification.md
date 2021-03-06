# 项目开发规约

```
Changelog

2021-06-28
初版

2021-06-30
增加文件命名规则

2021-07-20
git commit log 增加格式说明

2021-7-21
添加 git 科普文供参考
```







# 目录使用

## 笔记文件夹

<p class="icon notice" markdown="1"> 强制：根目录下每个用户新建自己的文件夹，每个人把自己的笔记放在自己的文件夹里。 </p>

```
- root/
  - cody/
  - user1/
  - user2/
```

## 图片文件夹

<p class="icon tips" markdown="1"> 建议：图片放在 /assets/img/user1 下。如果嫌麻烦也可以放在自己的笔记文件夹里。 </p>

```
- root/
  - assets/
    - img/
      - cody/
      - user1/
      - user2/
```

win 下可以用 gitee 当作图床，typora + PicGo + gitee 解决 markdown 插入图片的痛点。

## `SUMMARY.md`

目前打算的是这样使用，个人把自己的笔记放在各自的用户名下，不同用户使用了 `<hr>` 分割。

如果是公共资源可以写在前面。

```
- <hr>
- **Codyyy**
- [《Mastering Bitcoin 2nd Edition - Programming the Open Blockchain》](/cody/Mastering-Bitcoin-2nd-Edition-Programming-the-Open-Blockchain.md)



- <hr>
- **user1**



- <hr>
- **user2**
```

## 文件命名规则



<p class="icon notice" markdown="1"> 强制：正常情况下，文件夹和文件名都只允许使用：大小写字母，数字，横杠(-)。不要使用其他符号，也不允许有空白。 </p>



# git 使用

科普文参考

> [Git 看这一篇就够了](https://mp.weixin.qq.com/s/H6nNvvfvrPMJtnMV0JhsMg)
>
> [图解Git](http://marklodato.github.io/visual-git-guide/index-zh-cn.html?no-svg)


## commit log

commit 写的消息格式目前**不做强制要求**，写了这个 commit 做了什么就行。

规范的写法参考 <http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html>

格式： `feat: do sth`

注意**英文冒号**后跟**空格**。

```
feat：新功能（feature）

fix：修补bug

docs：文档（documentation）

style： 格式（不影响代码运行的变动）

refactor：重构（即不是新增功能，也不是修改bug的代码变动）

test：增加测试

chore：构建过程或辅助工具的变动
```

## branch

<p class="icon notice" markdown="1"> 强制：使用 main-dev-feature 分支的开发方式。 </p>

参考 <https://nvie.com/posts/a-successful-git-branching-model/>

但是我们只使用 3 种分支：

* **main**

    主分支，**不直接**在该分支下写代码，所有的代码都从 dev 分支合并

* **dev**

    开发分支，**正常情况下也不直接**在该分支下写代码，所有代码都从 feat 合并

* **feat**

    在该分支下写代码。

    每次需要添加自己的文件时，从**最新**的 dev 分支新建 feat 分支，分支命名为 `名字-日期-做了啥`（如    `cody-20210628-Algorand_Notes` ）格式，写完后从 feat 分支向 dev 分支**提 pull requests** 等待 @Cody 合并（**尽量不要自己合并**）。
    
    举例：<https://github.com/BIT-CST/blockchain-learning/pull/4>



用 git 操作时可能会遇到很多问题，先尝试百度解决，无法解决即时沟通。（**注意不要在尝试解决问题时把自己的笔记弄没了**）

因为是协作开发，所以在运行命令时确定自己知道在干什么，尤其是上传命令。



<p class="icon notice" markdown="1"> 强制：不要在 main 上开发，尽量不在 dev 上开发。不要在 main 和 dev 上使用 `git push -f`。 </p>





# 文字书写排版

**不做强制要求**，可以参考 <https://github.com/mzlogin/chinese-copywriting-guidelines>，书写更漂亮。