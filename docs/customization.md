---
layout: default
title: 定制
nav_order: 6
---

# 定制
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 颜色方案
{: .d-inline-block }

新
{: .label .label-green }

『文档而已』支持两个颜色方案：亮色（light，默认值），和暗色（dark）。

启用一个颜色方案，在站点的 `_config.yml` 文件中设置 `color_scheme` 参数。 

#### 示例
{: .no_toc }

```yaml
# 颜色方案支持 "light" （默认）和 "dark"
color_scheme: dark
```
<button class="btn js-toggle-dark-mode">预览暗色方案</button>

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = '预览暗色方案';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = '返回亮色';
  }
});
</script>

## 定制方案

### 定义一个定制方案

您可以添加定制方案。
假如您添加的方案叫做 `foo` （当然您可以任意给名字），那么就需要添加一个文件 `_sass/color_schemes/foo.scss` （记得将`foo`改为您给定的名字），在这个文件里您可以随意设定主题的颜色、字体、间距等。

可用变量列表在 [_variables.scss](https://github.com/pmarsceill/just-the-docs/tree/master/_sass/support/_variables.scss) 文件里。

例如，修改链接颜色从紫色变为蓝色，需要在您的颜色方案文件里：

#### 示例
{: .no_toc }

```scss
$link-color: $blue-000;
```

_注意:_ 不推荐直接在 `_sass/support/variables.scss` 里编辑变量，如果那样做可能会引发其他数据错误。
请使用方案文件。

### 使用定制方案

使用定制颜色方案，只需在您的站点配置文件 `_config.yml` 里设置 `color_scheme` 参数：
```yaml
color_scheme: foo
```

### 可转换定制方案

如果您想动态转换颜色方案，可以使用 javascript 方法——添加文件 `assets/css/just-the-docs-foo.scss` （如果颜色方案名字不是 `foo`，请修改），输入内容如下：

{% raw %}
    ---
    ---
    {% include css/just-the-docs.scss.liquid color_scheme="foo" %}
{% endraw %}

这将会使您通过 javascript 转换颜色方案。

```js
jtd.setTheme('foo');
```

## 覆盖和完全定制样式

如果不想只修改变量，而是要修改 CSS 类，或者增加新的 CSS 定制内容。那么，就将您的样式放进文件 `_sass/custom/custom.scss`。这样做既能将您的定制文件放
进一个单独的文件易于管理，很不影响上游文件的修改应用。

例如，如果您想添加自己的打印样式，可以添加下面的代码。

#### 示例
{: .no_toc }

```scss
// 仅为打印样式。
@media print {
  .side-bar, .page-header { display: none; }
  .main-content { max-width: auto; margin: 1em;}
}
```
