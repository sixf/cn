---
title: EndNote转换成BibTeX格式
tags: [R,R语言,文献,标签,LaTeX]
categories: [学习笔记,学术]
layout: post
comments: yes
---

用Word写小文档，有天生的优势。可是对于长篇大论，既有章节又要编排目录的情况下，格式的问题会非常头疼。此时LaTeX的优势便逐渐显现出来(LaTeX和BibTeX都是免费软件)。正如下图所示(图片来源于[Marko Pinteric](http://www.pinteric.com/))，随着写作文档变大变复杂，若用Word来编写，真是令人几乎抓狂。

![](http://sixf.org/files/images/2014/03/word-latex.gif)

之前我把所有的文献存储在EndNote中，发现转换格式时，刚开始可以把文献通过EndNote导出为一个文本文件，但是文本文件中的各个文献缺少各自的标签(Label or key)，无法被LaTeX读取。虽然网上有人在Linux系统下已经用Shell脚本完成了[格式的转换](http://blog.sciencenet.cn/blog-47991-537062.html)，而我作为一个R语言的依赖者，只能自己操刀写个小程序，给各个文献添加标签。该小程序的代码保管在GitHub Gist上，可以点击[这里(51KB)](https://gist.github.com/sixf/9826050/download)下载。

好记性不如烂笔头，以防遗忘，参考[前人经验](http://blog.sciencenet.cn/blog-47991-537062.html)，在此作个备忘录。从EndNote转成BibTeX的具体步骤为：

1.	在EndNote界面中，选择 Edit -> Output Styles -> Open Style Manager，并找到BibTeX Export这一行，在前面的方框打勾。如果之前你存放在EndNote中的文献信息非常全，甚至包括各论文的摘要和关键字等信息，那么当全部输出时，这些信息将过于累赘。此时，可以在Open Style Manager界面给BibTeX Export打勾后，点击右下角的Edit，再找到Bibliography-Templates，对各种文献类型，只保留你需要输出的信息，比如作者(author)、题目(title)、刊物名称(journal)、卷号(volumn)、页码(page)和发表年份(year)等。

2.	选择File -> Export，输入一个文件名，比如 "oldbib.txt"。注意此时Output Style是BibTeX Export，保存类型为Text File (\*.txt)，然后保存(可以查看代码压缩包中的"oldbib.txt"示例文件)。打开该文本文件会发现每篇文献都以`@article{`开始，以`}`结束，但是`@article{`之后并没有Lable/Key，所以得用我编写的R脚本添加各个文献标签。
	
3.	解压缩[已下载](https://gist.github.com/sixf/9826050/download)的压缩包，其中有一个名为"endnote2bibtex.r"的R脚本(如果无法显示文件类型，请直接用纯文本编辑器打开再拷贝代码到R运行界面即可)。运行该代码，即可得到一个名为"newbib.bib"的bibtex文件，即已经分别在各个文献的`@article{`之后加上了文献标签。如压缩包中"newbib.txt"文件所示。

其中，标签的格式是"James:2010"。如果是两位作者，则为"James-White:2010"。如果是三位及其以上作者，则为"James-etal:2010"。若刚好碰到文献的标签有重复，如某一作者在同一年不同杂志上发表了多篇论文，则用后缀a,b,c来区分，即"James:2010a","James:2010b"和"James:2010c"。

在转换文献前请确保每条文献的信息完整性。比如下载刚刊出的文献，年份和页码还没导入EndNote中，此时需要手动检查各条文献的信息，否则R代码运行时会报错。由于BibTeX读取文献标签的时候只支持英文，所以通过上述R代码转换的中文文献标签需要把中文换成英文。当然，如果你不用BibTeX进行改动文献信息，而是直接用纯文本编辑软件修改，那么也不会有问题，因为LaTeX`natbib`包中的命令`\citep{}`或`\citet{}`均支持中文的标签。