---
layout: post
title:  "使用python3的docx模块修改word表格中单个单元格内的字体样式"
categories: Python3
tags:  Python3
author: hjxfire
---

* content
{:toc}
通过查看相关资料,发现docx中只有修改整个表格样式的方法,没有修改单个单元格内字体样式的相关函数.所以暂时可以用游程对象"曲线救国",但是使用游程对象的话,是添加,不是覆盖,就需要将原来的删除再添加.





##示例
``` python
from docx import Document
from docx.shared import Pt
from docx.enum.text import WD_PARAGRAPH_ALIGNMENT
from docx.shared import RGBColor

document = Document('test.docx')
table = document.tables[0]

run=table.cell(0,0).paragraphs[0].add_run('test')   #填入的内容
run.font.name='宋体'      #设置字体
run.font.size=Pt(11)    #设置字号
run.font.bold=1         #设置是否加粗
run.font.color.rgb=RGBColor.from_string('00BFFF')   #设置文字颜色
table.cell(0,0).paragraphs[0].alignment = WD_PARAGRAPH_ALIGNMENT.CENTER #设置居中

document.save('test.docx')
```