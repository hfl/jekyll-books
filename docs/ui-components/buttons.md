---
layout: default
title: 按钮
parent: UI 组件
nav_order: 2
---

# 按钮
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 基本按钮样式

### 看似按钮的链接

<div class="code-example" markdown="1">
[链接按钮](http://example.com/){: .btn }

[链接按钮](http://example.com/){: .btn .btn-purple }
[链接按钮](http://example.com/){: .btn .btn-blue }
[链接按钮](http://example.com/){: .btn .btn-green }

[链接按钮](http://example.com/){: .btn .btn-outline }
</div>
```markdown
[链接按钮](http://example.com/){: .btn }

[链接按钮](http://example.com/){: .btn .btn-purple }
[链接按钮](http://example.com/){: .btn .btn-blue }
[链接按钮](http://example.com/){: .btn .btn-green }

[链接按钮](http://example.com/){: .btn .btn-outline }
```

### 按钮元素

GitHub Flavored Markdown 不支持 `button` 元素，所以不得不使用内联 HTML ：

<div class="code-example">
<button type="button" name="button" class="btn">按钮元素</button>
</div>
```html
<button type="button" name="button" class="btn">按钮元素</button>
```

---

## 使用按钮的工具类

### 按钮大小

使用[字号工具类]({{ site.baseurl }}{% link docs/utilities/typography.md %})容器包裹按钮来达到缩放效果：

<div class="code-example" markdown="1">
<span class="fs-6">
[大按钮](http://example.com/){: .btn }
</span>

<span class="fs-3">
[小按钮](http://example.com/){: .btn }
</span>
</div>
```markdown
<span class="fs-8">
[链接按钮](http://example.com/){: .btn }
</span>

<span class="fs-3">
[Tiny ass button](http://example.com/){: .btn }
</span>
```

### 按钮间距

使用[边距工具类]({{ site.baseurl }}{% link docs/utilities/layout.md %}#spacing)在同一块（block）内调整按钮间距。

<div class="code-example" markdown="1">
[有间距的按钮](http://example.com/){: .btn .btn-purple .mr-2 }
[按钮](http://example.com/){: .btn .btn-blue .mr-2 }

[有更大间距的按钮](http://example.com/){: .btn .btn-green .mr-4 }
[按钮](http://example.com/){: .btn .btn-blue }
</div>
```markdown
[有间距的按钮](http://example.com/){: .btn .btn-purple .mr-2 }
[按钮](http://example.com/){: .btn .btn-blue .mr-2 }

[有更大间距的按钮](http://example.com/){: .btn .btn-green .mr-4 }
[按钮](http://example.com/){: .btn .btn-blue }
```
