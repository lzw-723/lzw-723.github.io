---
layout:     post                    # 使用的布局（不需要改）
title:      Markdown语法总结              # 标题 
subtitle:   我们坚信写作写的是内容，所思所想，而不是花样格式 #副标题
date:       2020-2-4           # 时间
author:     lzw-723                      # 作者
catalog:    true                       # 是否归档
img:        https://s1.ax1x.com/2020/03/21/8fCDHA.jpg
tags:                               #标签
    - Markdown
    - 写作
---

## Markdow简介

**Markdown** 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档。

**Markdown** 语言在 2004 由约翰·格鲁伯（英语：John Gruber）创建。

**Markdown** 编写的文档可以导出 `HTML` 、`Word`、图像、`PDF`、`Epub` 等多种格式的文档。

**Markdown** 编写的文档后缀为 `.md`, `.markdown`

### 基本语法

#### 标题

```md
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```

#### 段落

**Markdown** 段落没有特殊的格式，直接编写文字就好，段落的换行是使用两个以上`空格`加上回车。  
也可以在段落后面使用一个`空行`来表示重新开始一个段落。

#### 字体

```md
*斜体文本*
_斜体文本_
**粗体文本**
__粗体文本__
***粗斜体文本***
___粗斜体文本___
```

*斜体文本*  
_斜体文本_  
**粗体文本**  
__粗体文本__  
***粗斜体文本***  
___粗斜体文本___

#### 分隔线

```md
***
```

***

#### 删除线

```md
百度
~~谷歌~~
```

百度  
~~谷歌~~

#### 列表

##### 无序列表

```md
* 第一项
* 第二项
* 第三项
```

* 第一项
* 第二项
* 第三项

##### 有序列表

```md
1. 第一项
2. 第二项
3. 第三项
```

1. 第一项
2. 第二项
3. 第三项

##### 嵌套列表

两个`空格`

```md
* 第一项
  * 第一项嵌套的第一个元素
  * 第一项嵌套的第二个元素
```

* 第一项
  * 第一项嵌套的第一个元素
  * 第一项嵌套的第二个元素
  
#### 任务列表

```md
* [x] task list 1
* [x] task list 2
* [ ] task list 3
  * [ ] task list 3-1
  * [ ] task list 3-2
    * [ ] task list 3-2-1
* [ ] task list 4
  * [ ] task list 4-1
  * [ ] task list 4-2
```

* [x] task list 1
* [x] task list 2
* [ ] task list 3
  * [ ] task list 3-1
  * [ ] task list 3-2
    * [ ] task list 3-2-1
* [ ] task list 4
  * [ ] task list 4-1
  * [ ] task list 4-2

#### 区块

```md
> 区块
> 区块  
> 最外层
>> 第一层嵌套
>>> 第二层嵌套
```

> 区块  
> 区块  
> 最外层
>> 第一层嵌套
>>> 第二层嵌套

#### 代码

```md
`code`
```java
System.out.println("Hello World");
\```
```

`code`

```java
System.out.println("Hello World");
```

#### 链接

```md
[Pixiv搜索](https://pixivic.com/)
[我的博客](https://lzw-723.github.io)
```

[Pixiv搜索](https://pixivic.com/)  
[我的博客](https://lzw-723.github.io)

#### 图片

```md
![alt 属性文本](图片地址)
![alt 属性文本](图片地址 "可选标题")

![比企谷八幡](https://s2.ax1x.com/2020/02/22/3MhWfs.jpg)

![雪ノ下雪乃](https://s2.ax1x.com/2020/02/22/3MfbRI.jpg "雪ノ下雪乃")
```

![alt 属性文本](图片地址)

![alt 属性文本](图片地址 "可选标题")

![比企谷八幡](https://s2.ax1x.com/2020/02/22/3MhWfs.jpg)

![雪ノ下雪乃](https://s2.ax1x.com/2020/02/22/3MfbRI.jpg "雪ノ下雪乃")

#### 表格

**Markdown** 制作表格使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行。

```md
|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |
```

|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |

### 高级技巧

#### HTML

不在 **Markdown** 涵盖范围之内的标签，都可以直接在文档里面用 **HTML** 撰写。

目前支持的 HTML 元素有：`<kbd> <b> <i> <em> <sup> <sub> <br>`等

```md
使用 <kbd>Win</kbd>+<kbd>L</kbd> 锁屏
```

使用 <kbd>Win</kbd>+<kbd>L</kbd> 锁屏

#### 转义

**Markdown** 使用了很多特殊符号来表示特定的意义，如果需要显示特定的符号则需要使用反斜杠 `\` 转义特殊字符

```md
**文本加粗** 
\*\* 正常显示星号 \*\*
```

**文本加粗**  
\*\* 正常显示星号 \*\*

#### 公式

当你需要在编辑器中插入数学公式时，可以使用两个美元符 `$$` 包裹 `TeX` 或 `LaTeX` 格式的数学公式来实现。提交后，问答和文章页会根据需要加载 `Mathjax` 对数学公式进行渲染。

```md
$$x > y$$

$$E=mc^2$$

$$\sin(\alpha)^{\theta}=\sum_{i=0}^{n}(x^i + \cos(f))$$
```

$$x > y$$

$$E=mc^2$$

$$\sin(\alpha)^{\theta}=\sum_{i=0}^{n}(x^i + \cos(f))$$

### 资料引用

[菜鸟教程](https://www.runoob.com/markdown)  
[MdEditor](https://www.mdeditor.com/)
