# Markdown 语法入门指南 / Markdown Syntax Quick Start Guide

> 本指南适用于初学者，涵盖最常用的 Markdown 语法。  
> This guide is for beginners and covers the most commonly used Markdown syntax.

---

## 📝 什么是 Markdown？ / What is Markdown?

**Markdown** 是一种轻量级标记语言，允许你使用易读易写的纯文本格式编写文档，然后转换为结构化的 HTML（或其他格式）。  
**Markdown** is a lightweight markup language that lets you write documents in plain text format that is easy to read and write, then convert them to structured HTML (or other formats).

它广泛用于 GitHub、GitLab、Reddit、Discord 等平台。  
It is widely used on platforms like GitHub, GitLab, Reddit, and Discord.

---

## 🔤 基本语法 / Basic Syntax

### 1. 标题 / Headings

使用 `#` 表示标题，`#` 越多，标题越小。

Use `#` for headings. More `#` means smaller heading.

```markdown
# 一级标题 (H1)
## 二级标题 (H2)
### 三级标题 (H3)
#### 四级标题 (H4)
```

效果：  
Result:

# 一级标题 (H1)  
## 二级标题 (H2)  
### 三级标题 (H3)  

> 💡 GitHub 中，`#` 后需加一个空格。  
> 💡 On GitHub, add a space after `#`.

---

### 2. 段落与换行 / Paragraphs and Line Breaks

段落由一个或多个连续的文本行组成，段落之间用**空行**分隔。  
A paragraph consists of one or more consecutive lines of text, separated by **blank lines**.

在行尾添加 **两个或以上空格** 可实现强制换行。  
Add **two or more spaces** at the end of a line to force a line break.

```markdown
这是第一段。  
这是同一段的第二行（前面有2个空格）。

这是第二段。
```

效果：  
Result:

这是第一段。  
这是同一段的第二行（前面有2个空格）。

这是第二段。

---

### 3. 强调 / Emphasis

- `*斜体*` 或 `_斜体_` → *斜体*  
  `*italic*` or `_italic_` → *italic*
- `**粗体**` 或 `__粗体__` → **粗体**  
  `**bold**` or `__bold__` → **bold**
- `***粗斜体***` → ***粗斜体***  
  `***bold italic***` → ***bold italic***

```markdown
*强调文本*  
**重要文本**  
***非常重要***
```

---

### 4. 列表 / Lists

#### 无序列表 / Unordered Lists

使用 `-`、`*` 或 `+`：

Use `-`, `*`, or `+`:

```markdown
- 项目一
- 项目二
  - 子项目
  - 子项目
```

#### 有序列表 / Ordered Lists

使用数字加点：

Use numbers followed by a dot:

```markdown
1. 第一步
2. 第二步
3. 第三步
```

> ⚠️ 数字不必连续，渲染后会自动排序。  
> ⚠️ Numbers don’t need to be sequential; they’ll auto-number when rendered.

---

### 5. 链接与图片 / Links and Images

#### 链接 / Links

```markdown
[链接文字](https://example.com "可选提示")
```

效果：[GitHub](https://github.com)

#### 图片 / Images

```markdown
![替代文本](/path/to/image.jpg "可选标题")
```

> 💡 替代文本（alt text）在图片无法显示时出现。  
> 💡 Alt text appears if the image fails to load.

---

### 6. 代码 / Code

#### 行内代码 / Inline Code

用反引号包裹：  
Wrap with backticks:

```markdown
使用 `print()` 输出内容。
```

效果：使用 `print()` 输出内容。

#### 代码块 / Code Blocks

用三个反引号 ``` 包裹，并可指定语言以高亮：

Wrap with triple backticks and optionally specify language for syntax highlighting:

````markdown
```python
def hello():
    print("Hello, Markdown!")
```
````

效果：  
Result:

```python
def hello():
    print("Hello, Markdown!")
```

---

### 7. 引用 / Blockquotes

使用 `>` 开头：

Start with `>`:

```markdown
> 这是一段引用。
> 可以跨多行。
```

效果：  
Result:

> 这是一段引用。  
> 可以跨多行。

---

### 8. 分割线 / Horizontal Rule

使用三个或以上的 `-`、`*` 或 `_`：

Use three or more `-`, `*`, or `_`:

```markdown
---
```

效果：  
Result:

---

### 9. 表格 / Tables

使用 `|` 和 `-` 创建表格：

Use `|` and `-` to create tables:

```markdown
| 姓名 | 年龄 | 城市 |
|------|------|------|
| 张三 | 28   | 北京 |
| 李四 | 32   | 上海 |
```

效果：  
Result:

| 姓名 | 年龄 | 城市 |
|------|------|------|
| 张三 | 28   | 北京 |
| 李四 | 32   | 上海 |

> 💡 对齐：在分隔线中加入 `:`  
> 💡 Alignment: Add `:` in the separator line  
> `:---` 左对齐 / left, `:---:` 居中 / center, `---:` 右对齐 / right

---

### 10. 任务列表 / Task Lists (GitHub 特有)

GitHub 支持任务列表：

GitHub supports task lists:

```markdown
- [x] 完成 Markdown 指南
- [ ] 上传到 GitHub
- [ ] 分享给朋友
```

效果：  
Result:

- [x] 完成 Markdown 指南
- [ ] 上传到 GitHub
- [ ] 分享给朋友

---

## ✅ 小贴士 / Tips

| 技巧 | 说明 |
|------|------|
| **预览** | 在 GitHub 编辑文件时，点击 "Preview" 查看效果 |
| **转义** | 用 `\` 转义特殊字符，如 `\*` 显示为 `*` |
| **兼容性** | 不同平台可能支持不同扩展语法（如 GitHub Flavored Markdown）|

| Tip | Description |
|-----|-------------|
| **Preview** | Click "Preview" when editing on GitHub to see rendering |
| **Escape** | Use `\` to escape special characters, e.g., `\*` shows as `*` |
| **Compatibility** | Different platforms may support different extensions (e.g., GitHub Flavored Markdown) |

---

## 📚 推荐资源 / Recommended Resources

- [GitHub Markdown Guide](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)  
- [Markdown 官方网站](https://daringfireball.net/projects/markdown/)  
- [Markdown Live Preview](https://dillinger.io/) — 在线编辑器
