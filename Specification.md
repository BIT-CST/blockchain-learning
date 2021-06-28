# 项目开发规约



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





# git 使用



## commit log

commit 写的消息格式目前**不做强制要求**，写了这个 commit 做了什么就行。

规范的写法参考 <http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html>

## branch

<p class="icon notice" markdown="1"> 强制：使用 main-dev-feature 分支的开发方式。 </p>



# 文字书写排版

**不做强制要求**，可以参考 <https://github.com/mzlogin/chinese-copywriting-guidelines>，书写更漂亮。