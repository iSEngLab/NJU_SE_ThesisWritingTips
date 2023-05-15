1. 英文摘要中， 本文是thesis不是paper
2. 中文中，一些英文的专有名词需要查阅确定，不要自己翻译，例如mutation testing叫变异测试，不叫突变测试

图表严禁跨页

留白太多

大小写 GitHub Github

英文关键词不要自己翻译，如Software Test，应是Software Testing

一些符号使用公式环境编辑，如P(t)和$P(t)$

中文关键词应是你的方向，你的技术体现

参考文献注意事项：

# 毕业设计写作建议

## 说明

个人经验仅供参考。
本项目仅供参考，以当年的论文实际要求为准。

## 开始之前

- 请简要了解 latex 语法，[参考链接](https://www.google.com/search?q=latex+%E6%95%99%E7%A8%8B)。
- 为本项目和[论文模板项目](https://github.com/nju-lug/NJUThesis) 或者https://git.nju.edu.cn/nju-lug/nju-latex-templates/njuthesis。
- 登录或者注册两个 latex 平台：[overleaf](https://www.overleaf.com/)、[tex.nju](https://tex.nju.edu.cn)。

## 模板创建

1. 在[这里](https://www.ctan.org/pkg/njuthesis)下载模板；或者直接[在线选择](https://tex.nju.edu.cn/template)南京大学学位论文模板。
2. 将模板上传到在线平台，推荐使用 tex.nju，在左上角设置中将编译器修改为 XeLaTex 。
    ![修改编译器](IMG/%E4%BF%AE%E6%94%B9%E7%BC%96%E8%AF%91%E5%99%A8.png)
3. ctrl+s 编译项目，验证能否输出 PDF。
4. 在使用中有任何问题请优先参考项目中的 [wiki](https://github.com/nju-lug/NJUThesis/wiki) 和[手册](http://mirrors.ctan.org/macros/unicodetex/latex/njuthesis/njuthesis.pdf)。

## 撰写文章

该部分是论文主体的编写。
建议通过 `\include{chapters/chap1}` 的方式将每一章分为子文件。

### 第一章

本章主要是绪论，通常分为三部分。

1. `1.1` 是项目背景，该节需要完成以下内容：
   1. 项目问题介绍：简要介绍背景，解释相关名词 (例如什么叫**测试用例排序**)。
   2. 当前方法概述与问题引出：为了完成上述任务，介绍当前业界常用的技术方案，以及其中存在的问题。注意这里的问题**需要能被项目中的技术解决**。
   3. 简要本文给出的解决方案。注意这里如果谈及技术意义，尽量不要“能够解决xxx” (例如：本系统可以动化地提取特征...，进而帮助报告审核者大大提升检测缺陷的效率...)，而是使用期望类词语（例如：以图提高报告审核者工作效率）。
2. `1.2` 是相关技术概论，也是引用数量的重要来源。本节需要完成的内容有：
   1. 介绍文章使用技术的发展情况，尽量仅对工具说明而不包含对工具优缺点的评论，通常说法：
      1. A[cite]技术规约借助不同的代码合成方法。
      2. B 等人[cite] 借助某方法完成了某任务。
   2. 介绍该技术在文章中**如何使用**。例如：由于X技术有较好的泛化能力，因此本文借助它完成Z任务，并在Y方面上对该方法进行了改进。
3. `1.3` 本文贡献，通常分为两部分：
   1. 系统实现细节，**需要具体说明本文使用的技术栈**，例如：本文使用 Java 语言，使用 Springboot 框架、JUnit 技术实现了一个Z系统，该系统有A、B、C功能。
   2. 本文的主要贡献。通常是 1.方案设计、2.实现了系统、3.对系统进行了测试。
4. `1.4` 文章其他部分介绍。

### 第二章

本章需要介绍文章使用的技术、工具细节。请注意每一个技术的最后需要说明该技术**如何在文章中使用**。

1. 技术细节：尽量使用一些文献引用。如果文章基于某文献、模型，可以对其展开详细的介绍。
2. 工具细节：不要介绍 Java、Springboot 等大路货，这类工具没有新意且查重时很容易重复。不要直接从官网 copy 内容，官网和自己论文是站在不同角度的。

### 第三章

本章是需求分析。撰写过程中注意一下几点：

1. `3.1` 通常是整体概述，需要提供一个整体流程图。该图中需要展示系统的结构 (例如服务端、客户端的划分、模块的划分等)。
2. 4+1 视图注意缩放，不宜过于稀疏 (图片空隙过多)。<br/>
   ![比较稀疏的用例图](IMG/%E8%BE%83%E7%A8%80%E7%96%8F%E7%9A%84%E7%94%A8%E4%BE%8B%E5%9B%BE.png)
   ![明显稀疏的用例图](IMG/%E6%98%8E%E6%98%BE%E7%A8%80%E7%96%8F%E7%9A%84%E7%94%A8%E4%BE%8B%E5%9B%BE.png)
3. 项目如果使用了数据库，除了给出表结构外，尽量给出对应的 ER 图。

### 第四章

本章是系统详细实现的描述。

1. 如果有技术方案的相关内容，请放在 `4.1`，小节名为“技术方案介绍”等。该步骤如果需要附图，注意和 `3.1` 图片的区别：这里的图片仅体现技术部分，不包括任何系统模块划分等工程组件。
2. 类图中注意各种线条的使用，[参考链接](https://www.google.com/search?q=%E7%B1%BB%E5%9B%BE+%E7%BA%BF%E6%9D%A1)。
3. 顺序图中注意同步、异步消息箭头不同，[参考链接](https://www.google.com/search?q=%E9%A1%BA%E5%BA%8F%E5%9B%BE+%E8%99%9A%E7%BA%BF)。
4. 贴代码时，如果使用图片，请 PPT -> 导出 PDF -> 剪裁 PDF 的形式，不要使用 png 等图片。注意图片中，中英文字体需要全程保持一致。代码高亮推荐使用[网站](https://highlightcode.com/)。

### 第五章

本章是系统测试与技术评估。

- 对系统测试，至少需要体现：测试环境、功能需求测试、非功能性测试。
- 如果提出了新技术，需要使用数据集对技术进行验证，如果是非 SOTA 数据，请给出对应说明 (例如：尽管该技术在A数据集上的B指标上表现不好，但是...)。
- 技术评估建议包含：测试环境、测试数据集、模型训练参数与训练步骤、评估指标、基线选择、实验研究的问题、实验数据与分析。
- 如果有技术评估，建议最后给出效度威胁 (THREATS TO VALIDITY) 小节。

### 第六章

本章是总结和展望。

- 总结部分不要过分的重复摘要或者第一章内容。
- 展望不要数量太多、问题太过严重 (会导致别人认为你没有做出任何贡献)。

## 撰写其他部分

### 中文摘要

通常是 3-4 部分：

1. 介绍背景 -> 介绍当前解决方案 -> 介绍当前方案的问题。
2. [OPT]本文提出的解决上述问题的方案。
3. [OPT]本文设计的系统 (具体说明本文使用的技术栈)。
4. 本文进行的测试及测试的意义 (系统能够有效提示B的效率，xxx)。

### 英文摘要

不必是中文摘要的翻译。由于中文用语和英文用语习惯不同，句对句翻译可能会导致英文逻辑奇怪，建议按照中文摘要的思路**重写**英文摘要。

英文摘要的第一部分可以参考、借鉴 CCF-A 的一些英文论文。

### 标题与关键词

- 工程性论文建议标题为**Y系统的设计与实现**。
- 英文标题注意虚词小写，其他词首字母大写。
- 关键词不要过于宽泛 (例如：软件工程)，建议关键词从左到右依次精确。
- 英文关键词注意拼写和大小写。

### 参考文献

参考文献分为期刊和会议论文，注意：

- 期刊必须的属性：
  1. 期刊名 (缩写)
  2. 文章标题 (title case)
  3. 作者
  4. 年号
  5. 卷号
  6. 页面范围
- 会议论文必须的内容：
  1. 会议名 (缩写’年份)
  2. 论文标题 (title case)
  3. 作者
  4. 年份
  5. 页面范围

如果没有找到卷号，则用 `1` 代替，如果没有找到页码，则用 `1--总页数` 代替。
**一定要二次确认所有在 arXiv 上的文章是否有正式发表。**

```latex
@Article{liu2019roberta,
  author  = {Liu, Yinhan and Ott, Myle and Goyal, Naman and Du, Jingfei and Joshi, Mandar and Chen, Danqi and Levy, Omer and Lewis, Mike and Zettlemoyer, Luke and Stoyanov, Veselin},
  journal = {arXiv preprint arXiv:1907.11692},
  title   = {RoBERTa: A Robustly Optimized BERT Pretraining Approach},
  year    = {2019},
  pages   = {1--13},
  volume  = {1},
}

@InProceedings{de2008z3,
  author       = {De Moura, Leonardo and Bj{\o}rner, Nikolaj},
  booktitle    = {Proceedings of the 14th International Conference on Tools and Algorithms for the Construction and Analysis of Systems (TACAS'08)},
  title        = {Z3: An Efficient SMT Solver},
  year         = {2008},
  pages        = {337--340},
}
```

引用中不要引用本硕博学位论文！
文章中需要有 5 篇及以上的中文 CCF-A 参考文献。

## 文章内容撰写注意

### 避免使用 “我们”

在文章中代称自己尽量使用“本文”、“本节”、“本系统”，不要使用“我们”。
英文中代称使用“this thesis”。

### 括号

有两种括号：

- 中文括号且前后不空格。
- 英文括号且前后空格。

请在文章中统一使用一种空格， 不要混合使用。

### 缩写

所有的英文缩写第一次出现请给出英文全称，如。

### 序号

由于当前模板标题采用了 `1.2` 的形式，因此正文的有序序号避免采用 `1.` 的形式，建议使用 `1)` 的形式。

```latex
这里狗哥简单说三点：

\begin{enumerate}[label=\arabic*)]
    \item 第一点。
    \item 第二点。
    \item 没了。
\end{enumerate}
```

### 引用

文章中所有引用 (提到文章其他部分) 请使用 `\ref{label}` 标记，不要自己写数字。这里包括：

- 1.2.2 节
- 图 4-3
- 表 2-1
- 算法 3

### 图片

- 图片统一为白底，不要为黑底白色 (特别是截图的暗色模式)，会严重影响打印效果。
- 所有的图片都需要有对应的说明文字。
- 所有的图片都需要自己完成 (说明性图片需要自己重新画；展示性图片展示的是自己编写的内容)。
- 图片不要和对应的说明文字间隔太多页。
- 图片尽量使用矢量图 (例如 PDF)，而避免使用 JPG、PNG 等。
- 图片颜色不要过于丰富。
- 

这里给出图片的参考 latex，请自行查找 `!htb` 含义；width 根据实际情况修改大小。

```latex
\begin{figure}[!htb]
    \centering
    \includegraphics[width=5.6in]{figure/chap.2/1.name.pdf}
    \caption{说明}
    \label{figure:2-1.name}
\end{figure}
```

### 表格

表格推荐使用 `tabularray` 包。具体的使用请查找相关文档。
这里提供一个表格的参考代码：

```latex
\begin{table}[htpb]
   \centering
   \caption{软工社区常用预训练任务}
   \label{tblr:2-1.PretrainTasks}
   \begin{tblr}{
      colspec = {Q[l,m]|Q[c,m]|Q[l,m]},
      hlines,
      hline{1,2,Z} = {1pt},
      hline{3,5,6,8,9} = {dashed},
      cell{1}{1,3} = {c}
         }
      名称                        & 参考文献                                                                & 任务描述                      \\
      Masked Span Prediction    & \cite{raffel2020exploring, chakraborty2021multi, gao2021automating} & {遮掩一定比例的标记，要求模型根据上下文 \\信息复原标记对应的内容。}                  \\
      Next Sentence Prediction  & \cite{zafar2019towards, henkel2021shipwright}                       & 给定两个句子，判断两句话是否紧接。         \\
      Code-AST Prediction       & \cite{niu2022spt}                                                   & {判断给定代码和 AST 是否匹配。}       \\
      Code Contrastive Learning & \cite{peng2021could,}                                               & {最小化相似代码片段距离，最大化不同代码      \\片段距离。}                \\
      Identifiers Masking       & \cite{liu2020multi}                                                 & {遮掩代码中的标记符 (变量名、函数名等)，     \\要求模型根据上下文信息还原标记。}                     \\
      Method Name Generation    & \cite{niu2022spt}                                                   & {遮掩函数名称，要求模型根据函数的实现       \\猜测函数名称。 }                        \\
      Review Comment Generation & \cite{li2022automating}                                             & {根据代码改动生成代码审查评论。}         \\
      Code Summarization        & \cite{wei2019code}                                                  & {给定模型代码，要求模型生成对应的自然       \\语言总结。}                          \\
   \end{tblr}
\end{table}
```

![示例表格的编译结果](IMG/%E8%A1%A8%E6%A0%BC%E7%A4%BA%E4%BE%8B.png)

### 其他内容

- 每段最后一行不易过短 (少于5个字)，尽量扩充或者删减到长度为半行以上。
- 中英文之间用一个空格隔开 (尽管模板会自动加上空格，建议写的时候自己也在源码加上)。
- 建议每行是一句话。
- 如果同一个参考文献在文章多次使用，间隔较远时建议同样加上引用。 (例如: [第二章]B 等人 [\cite] 提出了一个数据集，该数据集... [第五章]本文在B等人 [\cite] 提供的数据集对所提出方法进行了测试...)
- 多段之间是并列结构时，可以更换首局+加粗的形式突出。注意首局一定要概况本段。
  ```latex
  A 技术有 b，c，d 三种架构。

  \textbf {\kaishu b 架构：} ...

  \textbf {\kaishu c 架构：} ...
  
  \textbf {\kaishu d 架构：} ...
  ```
