# MkDocs + Material 额外 Markdown 语法

## 1. 提示框（Admonitions）
!!! note
    这是一个 `note` 提示框。

!!! abstract
    这是一个 `abstract` 提示框。

!!! info
    这是一个 `info` 提示框。

!!! tip
    这是一个 `tip` 提示框。

!!! success
    这是一个 `success` 提示框。

!!! question
    这是一个 `question` 提示框。

!!! warning
    这是一个 `warning` 提示框。

!!! failure
    这是一个 `failure` 提示框。

!!! danger
    这是一个 `danger` 提示框。

!!! bug
    这是一个 `bug` 提示框。

!!! example
    这是一个 `example` 提示框。

!!! quote
    这是一个 `quote` 提示框。

---

## 2. 代码块（Highlight.js 代码高亮）

```python
def hello():
    print("Hello, MkDocs!")
```

```javascript
console.log("Hello, MkDocs!");
```

---

## 3. 任务列表（Task Lists）

- [x] 已完成的任务
- [ ] 未完成的任务
- [ ] 另一个未完成的任务

---

## 4. 目录（Table of Contents）
在 Markdown 文件顶部添加：

```markdown
[TOC]
```

MkDocs 会自动生成目录。

---

## 5. 表格（Tables）

| 名称  | 年龄 | 性别 |
|------|----|----|
| 小明  | 12 | 男  |
| 小红  | 11 | 女  |

---

## 6. 公式（MathJax / KaTeX）

```markdown
$$
E = mc^2
$$
```

$$
E = mc^2
$$

行内公式示例： $a^2 + b^2 = c^2$

---

## 7. 下标 & 上标

- 下标：H~2~O（H₂O）
- 上标：x^2^（x²）

---

## 8. 键盘快捷键（Keyboard Keys）

```
++Ctrl++ + ++C++
```

**效果**： ++Ctrl++ + ++C++

---

## 9. 脚注（Footnotes）

```markdown
MkDocs[^1] 是一个强大的文档工具。

[^1]: MkDocs 是一个基于 Markdown 的静态网站生成器。
```

---

## 10. 折叠内容（Details）

```markdown
??? note "点击展开"
    这里是隐藏的内容
```

??? note "点击展开"
    这里是隐藏的内容

---

## 11. 代码块行号（Code Block Line Numbers）

```yaml
markdown_extensions:
  - pymdownx.highlight:
      linenums: true
```

示例：

```python linenums="1"
print("Hello, MkDocs!")
```

---

## 12. 代码块文件名（Filename in Code Block）

```python title="example.py"
print("Hello, MkDocs!")
```

---

## 13. 进度条（Progress Bar）

```markdown
==50%==
```

**效果**：
==50%==

---

## 14. 文本高亮（Highlight）

```markdown
==重要信息==
```

**效果**：
==重要信息==

---

## 15. 文本删除线（Strikethrough）

```markdown
~~删除的文本~~
```

**效果**：
~~删除的文本~~

---

## 16. Mermaid 图表（流程图、时序图）

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

---

## 17. 图片缩放（Image Zooming）

```markdown
![点击查看](https://via.placeholder.com/150){ width=200 }
```

![点击查看](https://via.placeholder.com/150){ width=200 }

---

## 18. 颜色文本（Color Text）

```markdown
<span style="color:red">红色文字</span>
```

**效果**：
<span style="color:red">红色文字</span>

---

## 19. 引用 GitHub Issues / PR

```markdown
gh-1234
```

**效果**：
gh-1234（会自动链接到 GitHub Issue）

---

## 20. 代码块折叠（Collapsible Code Block）

```yaml
??? example "示例代码"
    ```python
    print("Hello, MkDocs!")
    ```
```

??? example "示例代码"
    ```python
    print("Hello, MkDocs!")
    ```

---

## 21. 目录（Navigation Tabs）

```yaml
theme:
  features:
    - navigation.tabs
```

---

## 总结

MkDocs + Material 提供了丰富的 Markdown 扩展功能，包括：
- **Admonitions 提示框**
- **代码高亮**
- **数学公式**
- **流程图**
- **任务列表**
- **折叠内容**
- **图片缩放**
- **GitHub Issue 直接引用**
- **表格、目录、脚注**
- **高亮、删除线、上标、下标**
- **进度条、键盘快捷键**








## 自定义
- [配置](./config.md)

### 搜索
#### 搜索提升
=== "提升"
    ```
    ---
    search:
        boost: 2 
    ---

    # Page title
    ...
    ```
=== "下降"
    ```
    ---
    search:
        boost: 0.5
    ---

    # Page title
    ...
    ```

#### 排出在搜索之外

```
---
search:
  exclude: true
---

# Page title
...
```

### 博客
#### 添加博客
```
---
draft: true 
date: 2024-01-31 
categories:
  - Hello
  - World
---

# Hello world!
...
```

#### 添加作者
为了给您的帖子添加一些个性，您可以将每篇帖子与一个或多个作者关联。首先，.authors.yml在您的博客目录中创建文件，然后添加作者：
```markdown
authors:
  squidfunk:
    name: Martin Donath
    description: Creator
    avatar: https://github.com/squidfunk.png
```

然后在文章上添加
```
---
date: 2024-01-31
authors:
  - squidfunk
    ...
---

# Hello world!
...
```

#### 添加类别
类别是按主题在专用索引页上对帖子进行分组的绝佳方式。这样，对特定主题感兴趣的用户可以浏览您关于此主题的所有帖子。确保已启用类别并将其添加到 front mattercategories属性：


```
---
date: 2024-01-31
categories:
  - Hello
  - World
---

# Hello world!
```

#### 添加标签

```
---
date: 2024-01-31
tags:
  - Foo
  - Bar
---

# Hello world!
...
```
#### 设置slug
```
---
slug: hello-world
---

# Hello there world!
...
```
#### 添加相关链接
```
---
date: 2024-01-31
links:
  - plugins/search.md
  - insiders/how-to-sponsor.md
---

# Hello world!
...
```
```
---
date: 2024-01-31
links:
  - plugins/search.md
  - insiders/how-to-sponsor.md
  - Nested section:
    - External link: https://example.com
    - setup/setting-up-site-search.md
---

# Hello world!
...
```

#### 设定阅读时间¶
```
---
date: 2024-01-31
readtime: 15
---

# Hello world!
...
```