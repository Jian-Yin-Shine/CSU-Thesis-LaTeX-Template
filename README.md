# 中南大学学位论文Tex模版

Forked from GuoDaXia, thx.

## 项目起源

LaTeX利用设置好的模板，可以编译为格式统一的pdf。

目前国内大多出版社与高校仍在使用word，word由于其强大的功能与灵活性，在新手面对形式固定的论文时，排版、编号、参考文献等简单事务反而会带来很多困难与麻烦，对于一些需要通篇修改的问题，要想达到LaTeX的效率，对word使用者来说需要具有较高的技能水平。

为了能把主要精力放在论文撰写上，许多国际期刊和高校都支持LaTeX的撰写与提交，新手不需要关心格式问题，只需要按部就班的使用少数符号标签，即可得到符合要求的文档。且在需要全篇格式修改时，更换或修改模板文件，即可直接重新编译为新的样式文档，这对于word新手使用word的感受来说是不可思议的。

本项目的目的是为了创建一个符合中南大学研究生学位论文（博士）撰写规范的TeX模板，解决学位论文撰写时格式调整的痛点。

本模板依照《中南大学研究生学位论文撰写规范》中大研字【2020】30号编写。

## 主要内容

![cover](images/cover.png)

0. 封面（无效，需使用学校要求的彩色版、铜版纸打印）；
1. 扉页；
2. 学位论文原创性声明和版权使用授权书；
3. 中文摘要；
4. 英文摘要；
5. 目录；
6. 图表索引（必要时）；
7. 论文正文；
8. 参考文献；
9. 附录（必要时）；
10. 攻读博（硕）士学位期间主要研究成果；
11. 致谢。

## 版本状况

完整支持学术学位博士、硕士论文。

其他涉密、定向等可能需要修改封面的情况，需要自行修改`CSUthesis.cls`文件。

## 文件介绍

### `CSUthesis.cls`

样式文件，如果是标准的普通学术型博士，不需要管这个文件。

其他如涉密、定向之类的，目前本版本没有设计特定的设置功能，需要修改该文件。

对LaTeX有所了解的同学，也可按需修改这个文件。如果这个文件的样式设计有什么bug，欢迎在issue里提出。


### `gbt7714-unsrt.bst`和`gbt7714.sty`两个文件

来自项目[CTeX-org/gbt7714-bibtex-style](https://github.com/CTeX-org/gbt7714-bibtex-style)，是参考文献的样式，与学校论文撰写规范一致。


### `content`目录

所有论文的编辑内容在这里。

0. `config.tex`：论文的基本配置，包含标题、姓名、学院等各种信息。可根据需要启用盲审格式、图表索引：其中注释/保留 `\blindreviewtrue`和 `\blindreviewfalse`，输出盲审送审版本和正式版本；注释/保留 `\needfoltoltrue`和 `\needfoltolfalse`，输出含图表索引及不含图表索引的版本。
1. `abstactcn.tex`和`abstracten.tex`：顾名思义。
2. `content.tex`：从绪论到总结的全部正文内容。`\cite`的时候可能因为tex文件与主文件分离，LaTeX环境配置不到位，会有找不到bib的提示（Texlive+sublime会这样），没关系，照常插入需要的bibkey即可。
3. `additional.tex`：成果、致谢、附录之类的。


### `csuthesis_main.tex`

论文主文件，正常情况下不用修改这个文件，以这个文件编译论文即可。

在content目录提供的页面不足以保证所需内容时，可以修改主文件，引入其他自定义content文件。

### `images`目录

放图片，模板已经配置了相对路径，所以在文中插图片时，直接用images目录下的相对路径即可，比如`images/csu.png`，在正文中插入只需要`csu.png`。

## 编译

测试环境：TexMaker & TexLive in Linux & Windows, xelatex is used to compile.

编译步骤：安装`TexLive`支持包，使用`TexMaker`、`TexStudio`等IDE，选中`xelatex`编译器进行编译。

注意：
1. 除`TexMaker`等IDE外，请使用如sublime等高级编辑器，否则可能因为ANSI、UTF-8等编码格式问题编译失败；
2. 使用MiKTex包而不是TexLive时，图片请`不要使用` eps 格式，MiKTex包的xelatex编译器“has no Encapsulated PostScript (EPS) graphics are supported”。


## 一些毕业流程上与word差异的考虑

想到多少补充多少吧。

### 知网查重
知网查重有识别参考文献的功能，但是不怎么成熟。一般word编译的pdf能识别出来，但是有的识别不出来。这个latex模板的pdf，知网查重会把参考文献标红。

不过不用担心，目前中南查重规则是要去掉参考文献的pdf。参考[`official_documents/中南大学研究生学位论文“学术不端文献检测系统”使用管理办法.mht`](http://gra.its.csu.edu.cn/yjsy/pygl/wjtzxq54863_3_6.html)



