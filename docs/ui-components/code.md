---
layout: default
title: 代码
parent: UI 组件
has_children: true
nav_order: 6
---

# 代码
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 行内代码

行内代码使用反向单引号（`）包裹。

<div class="code-example" markdown="1">
Lorem ipsum dolor sit amet, `<行内代码片段>` adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 带`<行内代码片段>`的标题。
{: .no_toc }
</div>
```markdown
Lorem ipsum dolor sit amet, `<行内代码片段>` adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

## 带`<行内代码片段>`的标题。
```

---

## 语法高亮代码块

对于代码块使用三个反向单引号启用 Jekyll 内建代码高亮（Rouge），引入语言名称支持如下：

<div class="code-example" markdown="1">
```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```
</div>
{% highlight markdown %}
```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```
{% endhighlight %}

---

## 带有渲染示例的代码块

演示前端代码，有时需要显示渲染结果。引入项目样式后需要渲染，可以是使用 `<div>` 加上 `code-example` 类，再使用代码块语法即可。如果您想要使用 Markdown 而不是 HTML 来渲染输出，使用 `markdown="1"` 属性告诉 Jekyll 您渲染的代码是 Markdown 格式……这是要获得元……

<div class="code-example" markdown="1">

<div class="code-example" markdown="1">

[Link button](http://example.com/){: .btn }

</div>
```markdown
[Link button](http://example.com/){: .btn }
```

</div>
{% highlight markdown %}
<div class="code-example" markdown="1">

[Link button](http://example.com/){: .btn }

</div>
```markdown
[Link button](http://example.com/){: .btn }
```
{% endhighlight %}
