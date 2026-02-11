# LaTeX 入门指南 / LaTeX Quick Start Guide

> 本指南面向初学者，介绍如何编写 `.tex` 文件及常用语法。适用于科研、论文、报告等场景。  
> This beginner-friendly guide introduces how to write `.tex` files and common syntax—ideal for academic papers, theses, reports, and more.

---

## 📄 什么是 LaTeX？ / What is LaTeX?

**LaTeX**（发音为 “Lah-tech” 或 “Lay-tech”）是一个基于 TeX 的高质量排版系统，特别擅长处理数学公式、参考文献和复杂文档结构。  
**LaTeX** (pronounced “Lah-tech” or “Lay-tech”) is a high-quality typesetting system built on TeX, especially powerful for mathematical formulas, bibliographies, and complex document structures.

它广泛用于学术界，是撰写科技论文、学位论文和书籍的标准工具之一。  
It is widely used in academia and is a standard tool for writing scientific papers, theses, and books.

---

## 🛠️ 安装与编译 / Installation and Compilation

### 安装 LaTeX 发行版 / Install a LaTeX Distribution

- **Windows**: [MiKTeX](https://miktex.org/) 或 [TeX Live](https://www.tug.org/texlive/)
- **macOS**: [MacTeX](https://www.tug.org/mactex/)
- **Linux**: `sudo apt install texlive-full`（Ubuntu/Debian）

> 💡 推荐使用 **Overleaf**（[overleaf.com](https://www.overleaf.com)）——无需安装，在线编写并实时预览。  
> 💡 We recommend **Overleaf** ([overleaf.com](https://www.overleaf.com)) — no installation needed; write and preview online in real time.

### 编译命令 / Compilation Commands

```bash
pdflatex yourfile.tex    # 生成 PDF（推荐）
xelatex yourfile.tex     # 支持中文和 Unicode（推荐用于中文）
```

---

## 🧱 基本文件结构 / Basic Document Structure

每个 LaTeX 文档都包含以下三部分：

Every LaTeX document has three essential parts:

```latex
\documentclass{article}        % 文档类型 / Document class

\usepackage[utf8]{inputenc}    % 输入编码（现代引擎通常不需要）  
\usepackage{ctex}              % 中文支持（使用 XeLaTeX 时推荐）  

\title{我的第一份 LaTeX 文档}   % 标题  
\author{张三}                  % 作者  
\date{\today}                 % 日期  

\begin{document}

\maketitle                    % 生成标题  

这是正文内容。  
This is the main content.

\end{document}
```

> ✅ 使用 `xelatex` + `ctex` 包可完美支持中文。  
> ✅ Use `xelatex` with the `ctex` package for full Chinese support.

---

## 🔤 常用语法 / Common Syntax

### 1. 章节与段落 / Sections and Paragraphs

```latex
\section{引言}          % 一级标题  
\subsection{背景}       % 二级标题  
\subsubsection{动机}    % 三级标题  

这是一个段落。LaTeX 会自动处理段间距和首行缩进。  
This is a paragraph. LaTeX automatically handles spacing and indentation.
```

> ⚠️ 不要手动换行！留空行表示新段落。  
> ⚠️ Don’t manually break lines! Leave a blank line to start a new paragraph.

---

### 2. 强调与字体 / Emphasis and Fonts

```latex
\textbf{粗体文本}        % Bold  
\textit{斜体文本}        % Italic  
\underline{下划线}      % Underline  
\emph{强调文本}          % Context-aware emphasis (italic in plain text)
```

效果：  
Result:  
**粗体文本**，*斜体文本*，，*强调文本*

---

### 3. 列表 / Lists

#### 无序列表 / Unordered List

```latex
\begin{itemize}
  \item 第一项
  \item 第二项
    \begin{itemize}
      \item 子项
    \end{itemize}
\end{itemize}
```

#### 有序列表 / Ordered List

```latex
\begin{enumerate}
  \item 第一步
  \item 第二步
\end{enumerate}
```

---

### 4. 数学公式 / Mathematical Formulas

#### 行内公式 / Inline Math

用 `$...$` 包裹：

Wrap with `$...$`:

```latex
爱因斯坦质能方程：$E = mc^2$。  
Einstein's equation: $E = mc^2$.
```

#### 独立公式 / Displayed Math

用 `$$ ... $$` 或 `equation` 环境：

Use `$$ ... $$` or `equation` environment:

```latex
$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$

\begin{equation}
  F = ma
\end{equation}
```

> 💡 推荐使用 `amsmath` 宏包增强数学功能：`\usepackage{amsmath}`  
> 💡 Use the `amsmath` package for advanced math: `\usepackage{amsmath}`

---

### 5. 插入图片 / Including Images

首先引入 `graphicx` 宏包：

First, load the `graphicx` package:

```latex
\usepackage{graphicx}
```

然后插入图片：

Then insert an image:

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.5\textwidth]{example.png}
  \caption{示例图片}
  \label{fig:example}
\end{figure}
```

> 📁 图片文件需放在项目目录中（如 `images/example.png`）。  
> 📁 Place image files in your project folder (e.g., `images/example.png`).

---

### 6. 表格 / Tables

使用 `tabular` 环境：

Use the `tabular` environment:

```latex
\begin{table}[htbp]
\centering
\begin{tabular}{|c|c|c|}
\hline
姓名 & 年龄 & 城市 \\
\hline
张三 & 28 & 北京 \\
李四 & 32 & 上海 \\
\hline
\end{tabular}
\caption{用户信息表}
\end{table}
```

> 💡 推荐使用 [TablesGenerator.com](https://www.tablesgenerator.com/) 可视化生成 LaTeX 表格。  
> 💡 Try [TablesGenerator.com](https://www.tablesgenerator.com/) to visually create LaTeX tables.

---

### 7. 参考文献 / Bibliography

使用 BibTeX 管理参考文献：

Manage references with BibTeX:

1. 创建 `references.bib` 文件：
   ```bibtex
   @article{einstein1905,
     title={Zur Elektrodynamik bewegter Körper},
     author={Einstein, Albert},
     journal={Annalen der Physik},
     year={1905}
   }
   ```

2. 在 `.tex` 文件中引用：
   ```latex
   根据爱因斯坦的理论 \cite{einstein1905}...
   
   \bibliographystyle{plain}
   \bibliography{references}
   ```

3. 编译顺序：
   ```bash
   pdflatex file.tex
   bibtex file.aux
   pdflatex file.tex
   pdflatex file.tex
   ```

> ✅ Overleaf 会自动处理 BibTeX 编译。  
> ✅ Overleaf handles BibTeX compilation automatically.

---

## 🌐 中文支持 / Chinese Support

推荐配置（使用 XeLaTeX）：

Recommended setup (with XeLaTeX):

```latex
\documentclass[UTF8]{ctexart}  % ctexart 自动配置中文

\title{中文 LaTeX 示例}
\author{作者}
\date{\today}

\begin{document}
\maketitle

你好，LaTeX！  
Hello, LaTeX!

\end{document}
```

编译命令：  
Compilation command:

```bash
xelatex myfile.tex
```

---

## 📁 项目结构建议 / Recommended Project Structure

```
my-paper/
├── main.tex
├── sections/
│   ├── intro.tex
│   └── method.tex
├── figures/
│   └── diagram.png
├── references.bib
└── README.md
```

在 `main.tex` 中用 `\input{sections/intro}` 引入子文件。

Use `\input{sections/intro}` in `main.tex` to include subfiles.

---

## ✅ 小贴士 / Tips

| 技巧 | 说明 |
|------|------|
| **不要手动编号** | LaTeX 自动处理章节、公式、图表编号 |
| **善用宏包** | 如 `geometry`（页边距）、`hyperref`（超链接）、`booktabs`（专业表格） |
| **错误排查** | 查看 `.log` 文件定位报错位置 |

| Tip | Description |
|-----|-------------|
| **Don’t number manually** | LaTeX auto-numbers sections, equations, figures |
| **Use packages wisely** | e.g., `geometry` (margins), `hyperref` (hyperlinks), `booktabs` (professional tables) |
| **Debug errors** | Check the `.log` file to locate errors |

---

## 📚 推荐资源 / Recommended Resources

- 📘 [《一份（不太）简短的 LaTeX 介绍》](https://github.com/CTeX-org/lshort-zh-cn)（中文经典）  
- 🌐 [Overleaf Learn](https://www.overleaf.com/learn) — 官方教程  
- 🧪 [Detexify](http://detexify.kirelabs.org/) — 手绘符号识别 LaTeX 命令  
- 📦 [CTAN](https://ctan.org/) — LaTeX 宏包大全

---

> ✨ 现在你已经可以开始用 LaTeX 写作了！  
> ✨ You’re now ready to start writing with LaTeX!