---
layout: page
title: "使用[Markdown]+[Mathjax] 进行科技文档写作、交流与讨论"
description: ""
---

# 使用[Markdown]+[Mathjax] 进行科技文档写作、交流与讨论

## 为什么?

工欲善其事，必先利其器。

很长一段时间，大家常用来写作文档的软件都是Microsoft Word, 因为简单易用，所见即所得，容易上手，几乎没有门槛。

但是，科技文档的写作不可回避的一个问题是数学公式的输入和显示。

Microsoft Word在这方面的表现实在是惨不忍睹。MathType部分地缓解了这个问题，但是数学公式的输入效率仍然很低，而且动不动就遇到在他人的电脑上或者另一个版本的软件上公式显示为乱码，对象打不开等等问题。 

LaTeX 用来排版数学公式倒是很完美，输入效率高，显示效果也非常棒。但是LaTeX太笨重了，语法的学习，软件的安装和配置都太麻烦了，门槛太高。
基本上 LaTeX 只能用来写论文，用它进行一般文档写作可谓是高射炮打蚊子，杀鸡用牛刀了。

[Markdown]和[Mathjax]的出现完美地解决了这个问题。 [Markdown]是一种专门为写作设计的非常简洁的标记语言，学习门槛极低，不需要任何软件也能看懂。
[Mathjax]是一个javascript库，它的作用在于提供对LaTeX语法的数学公式代码的渲染能力，以html网页的形式非常美观地显示数学公式。

> 话说，在这里简单补充一句，[Markdown]凭借其简单的语法，更易于学习和输入的特性，近年来赢得了大量专业写作人士的喜爱，如果写作是你生活中不可缺少的一部分，而你却尚不了解[Markdown]，那现在就是时候去了解一下了。

## 如何做？

我需要安装什么软件?

不，不需要安装任何软件就可以开始动手用Markdown写作了。 你可以选用任何你喜欢的编辑器来编辑Markdown源文件，比如[Vim], UtlraEdit, 甚至是记事本(NotePad)也可以。

但是，如果想要看到美观的数学公式，建议安装Chrome浏览器的一个名叫[Markdown Preview Plus]的扩展。 添加扩展以后在地址栏上右侧可以看到多了一个M状的图标，单击后打开菜单点击options设置选项，勾选最上面的Enable Mathjax，就可以启用Mathjax渲染。 一般我们在本地写作保存为*.md文件，用chrome浏览器打开，其访问地址一般是 file:///C:/path/to/file.md，这种情况需要在Chrome浏览器扩展设置中允许对应的插件(Markdown Preview Plus)访问本地文件，

写好[Markdown]文件以后可以直接将.md文件发送给他人。如果对方也安装了[Markdown Preview Plus]或其它类似功能的软件，他就可以阅读到数学公式展示效果很棒的文档;如果对方什么软件没有安装，他至少可以很容易读懂你写的文档。如果担心对方是否能正确显示的问题，更简单的办法是直接发送导出的html文件。

> Tips: 一个小技巧是Markdown里的数学公式latex代码中如果需要出现下划线_，与Markdown语法中表示斜体的下划线冲突，需要在前面加\\进行转义。


如果进一步还想把写好的[Markdown]文件转成其它html以外的格式保存，如PDF等，就需要安装额外的工具了。推荐[Pandoc]，这是一把文件格式转换的瑞士军刀。


[Markdown]: http://pandoc.org/README.html#pandocs-markdown
[Mathjax]: https://www.mathjax.org/
[Vim]: http://www.vim.org/
[Pandoc]: http://pandoc.org/
[Markdown Preview Plus]: https://chrome.google.com/webstore/detail/markdown-preview-plus/febilkbfcbhebfnokafefeacimjdckgl

