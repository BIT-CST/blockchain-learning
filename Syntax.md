# Syntax

## 普通 markdown 语法

。。。

## 自定义 CSS 语法

目前已有的的 CSS 语法如下，使用的 CSS 文件是我自己写的：<https://github.com/baicaihenxiao/js/blob/master/cserclub-common.css>

如果要自己定义 CSS，可以在 `/assets/css/` 下新建 CSS 文件，然后在这里补充使用方式。

### Label

<p class="check" markdown="1">这种方法能在html tag中法</p>

<p class="icon tips" markdown="1">这种方法能在h能方法能在</p>

<p class="icon question" markdown="1">这种方法能方法能在h</p>

<p class="icon notice" markdown="1">这种方法能在法</p>

<p class="icon todo" markdown="1">这种方法能在rkdown语法</p>

<p class="icon label" markdown="1">这种方法能arkdown语法</p>

<p class="icon star" markdown="1">这种方法能rkdown语法</p>





```html
<p class="check" markdown="1">这种方法能在html tag中法</p>

<p class="icon tips" markdown="1">这种方法能在h能方法能在</p>

<p class="icon question" markdown="1">这种方法能方法能在h</p>

<p class="icon notice" markdown="1">这种方法能在法</p>

<p class="icon todo" markdown="1">这种方法能在rkdown语法</p>

<p class="icon label" markdown="1">这种方法能arkdown语法</p>

<p class="icon star" markdown="1">这种方法能rkdown语法</p>

```



### tag

<span class="cser-tag" markdown="1"> LeetCode </span>

```html
<span class="cser-tag" markdown="1"> LeetCode </span>
```



### summary

<details open>
<summary> ccc </summary>

aaa

</details>

```html
<details open>
<summary> ccc </summary>

aaa

</details>
```



可以去掉 `open` 默认折叠。

