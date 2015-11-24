---
layout: post
title: Markdown
---
 
## 区块  
### 段落和换行  
    两个以上空格 ＋ 回车 ＝ 换行
### 标题  
`＃`控制标题`H1~H6`  

```
# H1
```


### 列表  
无序使用`*`、`+`或`-`加空格  

```
* Red
* Green
* Blue
```

* Red
* Green
* Blue

有序直接使用数字

```
1. Red
2. Green
3. Blue
```
1. Red
2. Green
3. Blue

### 代码块 
\`\`\` 来表示一段代码，`Github`支持代码高亮

<pre><code>   
```java  
package main

import "fmt"

func main() {
    fmt.Println("Hello, Markdown!")
}
```
</code></pre>

```java
package main

import "fmt"

func main() {
    fmt.Println("Hello, Markdown!")
}
```  

### 分割线
三个以上的`*`、`-`、`_`代表分隔线 


```
***
---
___
```
___

## 区段
### 链接
`[]`后面跟着`()`,括号中加`"title"`来表示`title`  
`[@Github](https://github.com "github")`  

[@Github](https://github.com/ "Github")
### 图片
```
![Github](/public/img/github.gif "Github")
```
![Github](/public/img/github.gif "Github")


### 代码
\` \`包含一段来表示小段代码 

```
`Golang`
```

`Golang`

## 其他
### 转义
特殊符号需要转义前面追加`\`

```
\   反斜线
`   反引号
*   星号
_   底线
{}  花括号
[]  方括号
()  括弧
#   井号
+   加号
-   减号
.   英文句点
!   惊叹号
```
### 自动连接
简短的URL和邮件可以通过`<>`自动识别  

```
<https://github.com>
```
<https://github.com>

###  Tips
1. \`\`\` 引用代码`code`需要空出一行

## 参考
1. <http://wowubuntu.com/markdown>
2. [Github Markdown](https://help.github.com/articles/github-flavored-markdown/)

