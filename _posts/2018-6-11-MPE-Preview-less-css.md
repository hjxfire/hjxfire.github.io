---
layout: post
title:  "VSCode中Markdown Preview Enhanced的预览样式设置(MAC下)"
categories: VSCode
tags:  VSCode "MPE Preview" Markdown MAC
author: hjxfire
---

* content
{:toc}
在使用VSCode编写Markdown时,对Markdown Preview Enhanced预览显示出来的效果不太满意,官方文档中说是在命令行下输入Markdown Preview Enhanced: Customize Css即可在出现的style.less文件中进行自定义,也可以直接去~/.mume/style.less修改.  
但是我对这个不太熟悉,所以我直接去寻找预览样式的源配置文件,然后通过在浏览器中预览并查看元素的方法找到我要修改的元素名,再进行修改即可.





## 配置文件地址
1. 主配置文件
>~/.vscode/extensions/shd101wyy.markdown-preview-enhanced-0.3.5/node_modules/@shd101wyy/mume/styles/preview_theme/github-light.css
2. 代码段配置文件
>~/.vscode/extensions/shd101wyy.markdown-preview-enhanced-0.3.5/node_modules/@shd101wyy/mume/styles/prism_theme/github.css

<hr style="background-color: rgb(25, 172, 230);height: 1px;">
styles文件下面还有很多样式配置文件,但暂时没找到怎么直接切换,作者放了那么多配置文件应该是有用的...
