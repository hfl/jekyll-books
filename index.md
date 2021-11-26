---
layout: default
title: 首页
nav_order: 1
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /
---

# 专注于编写好文档
{: .fs-9 }

『文档而已』[^1]使您以一个可定制且托管于 GitHub Pages 的响应式文档作为文档编写的起点。
{: .fs-6 .fw-300 }

[马上开始](#开始){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [到 GitHub 查看](https://github.com/pmarsceill/just-the-docs){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## 开始

### 依赖关系

『文档而已』基于静态站点生成器—— [Jekyll](https://jekyllrb.com) 系统，想要获取更多信息请查阅[快速上手指南](https://jekyllrb.com/docs/)。『文档而已』不需要特殊插件就可以运行 GitHub Pages 的标准 Jekyll 编译器。[Jekyll SEO Tag 插件](https://github.com/jekyll/jekyll-seo-tag)默认已经内置（不需另行安装），所以可以直接在文档页面使用 SEO 和打开图形元数据。配置 SEO 和打开图形元数据查阅 [Jekyll SEO Tag 使用指南](https://jekyll.github.io/jekyll-seo-tag/usage/)。

### 快速开始：使用 GitHub Pages 远程版式

1. 添加『文档而已』到 Jekyll 站点的 `_config.yml` 文件中的 [remote theme](https://blog.github.com/2017-11-29-use-any-theme-with-github-pages/) 参数
```yaml
remote_theme: pmarsceill/just-the-docs
```
<small>您必须在您的仓储中启用 GitHub Pages，还要由一个或者更多的 Markdown 文件和一个 `_config.yml` 文件。[查看示例仓储](https://github.com/pmarsceill/jtd-remote)</small>

### 本地化安装：使用基于 GEM 的版式

1. 安装 Ruby Gem
```bash
$ gem install just-the-docs
```
```yaml
# .. 或者添加到您的 Jekyll 站点的 Gemfile 文件中
gem "just-the-docs"
```
2. 添加『文档而已』到 Jekyll 站点的 `_config.yml`
```yaml
theme: "just-the-docs"
```
3. _可选:_ 初始化搜索数据（创建 `search-data.json`）
```bash
$ bundle exec just-the-docs rake search:init
```
3. 运行本地 Jekyll 服务器
```bash
$ jekyll serve
```
```bash
# .. 或者如果您使用 Gemfile 文件(bundler)
$ bundle exec jekyll serve
```
4. 通过浏览器访问 [http://localhost:4000](http://localhost:4000)

如果您在 GitHub Pages 托管站点, [建立 GitHub Pages 和 Jekyll 的本地化服务](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll)将使您更容易进行开发。

### 配置『文档而已』

- [查看配置选项]({{ site.baseurl }}{% link docs/configuration.md %})

---

## 关于项目

『文档而已』&copy; 2017-{{ "now" | date: "%Y" }} 版权归 [Patrick Marsceill](http://patrickmarsceill.com).

### 许可

『文档而已』使用 [MIT 协议](https://github.com/pmarsceill/just-the-docs/tree/master/LICENSE.txt)分发传播。

### 参与

在为此仓储做出贡献时，请首先通过 issue、电子邮件或任何其他方法与此仓储的所有者讨论您希望进行的更改后，然后再相应开发。在[我们的 GitHub 仓储](https://github.com/pmarsceill/just-the-docs#contributing)中阅读有关成为贡献者的更多信息。

#### 感谢您参与『文档而已』开发！

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"/></a>
  </li>
{% endfor %}
</ul>

### 行为守则

『文档而已』致力于培养一个热情好客的社区。

在 GitHub 仓储[查看我们的行为守则](https://github.com/pmarsceill/just-the-docs/tree/master/CODE_OF_CONDUCT.md)。

---
#### 注释

[^1]: Just the Docs 的中文版名字
