---
layout: default
title: 排版
parent: UI 组件
nav_order: 1
---

# 排版
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 字体

默认情况下，『文档而已』都是使用原生系统的 sans-serif 字库：

```scss
system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif
```

ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz
{: .fs-5 .ls-10 .code-example }

对于等款字体，例如代码片段或者 `<pre>` 元素，『文档而已』使用原生系统等款字体：

```scss
"SFMono-Regular", Menlo, Consolas, Monospace
```

ABCDEFGHIJKLMNOPQRSTUVWXYZ
abcdefghijklmnopqrstuvwxyz
{: .fs-5 .ls-10 .text-mono .code-example }

---

## 响应式缩放

『文档而已』使用基于视窗大小的响应式缩放。

| 选择器               | 小屏字号 `font-size`             | 大屏字号 `font-size`         |
|:----------------------|:---------------------------------|:------------------------------|
| `h1`, `.text-alpha`   | 32px                             | 36px                          |
| `h2`, `.text-beta`    | 18px                             | 24px                          |
| `h3`, `.text-gamma`   | 16px                             | 18px                          |
| `h4`, `.text-delta`   | 14px                             | 16px                          |
| `h5`, `.text-epsilon` | 16px                             | 18px                          |
| `h6`, `.text-zeta`    | 18px                             | 24px                          |
| `body`                | 14px                             | 16px                          |

---

## 标题

标题渲染如：

<div class="code-example">
<h1>标题 1</h1>
<h2>标题 2</h2>
<h3>标题 3</h3>
<h4>标题 4</h4>
<h5>标题 5</h5>
<h6>标题 6</h6>
</div>
```markdown
# 标题 1
## 标题 2
### 标题 3
#### 标题 4
##### 标题 5
###### 标题 6
```

---

## 正文文本

默认正文文本渲染如下：

<div class="code-example" markdown="1">
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</div>
```markdown
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
```

---

## 行内元素

<div class="code-example" markdown="1">
文本可以**粗体**, _斜体_, 或者~~删除线穿过~~。

[链接到其他页面](another-page)。
</div>
```markdown
文本可以**粗体**, _斜体_, 或者~~删除线穿过~~。

[链接到其他页面](another-page)。
```

---

## 排版工具类

还有大量定制的排版 CSS 类用于覆盖默认原来的文字大小、粗细、行高和首字母大小写等。

[查看排版工具类]({{ site.baseurl }}{% link docs/utilities/utilities.md %}#typography){: .btn .btn-outline }
