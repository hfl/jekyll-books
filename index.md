---
layout: default
title: 首页
nav_order: 1
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /
---

# 专注于编写好文档
{: .fs-9 }

文档而已（Just the Docs）可以使您编写一个可定制且托管于 GitHub Pages 的响应式文档作为起点。
{: .fs-6 .fw-300 }

[马上开始](#开始){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [在 GitHub 查看](https://github.com/pmarsceill/just-the-docs){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## 开始

### 依赖关系

『文档而已』基于静态站点生成器—— [Jekyll](https://jekyllrb.com) 系统，想要获取更多信息请查阅[快速上手指南](https://jekyllrb.com/docs/)。『文档而已』不需要特殊插件就可以运行 GitHub Pages 的标准 Jekyll 编译器。[Jekyll SEO Tag 插件](https://github.com/jekyll/jekyll-seo-tag)默认已经内置（不需另行安装），所以可以直接在文档页面使用 SEO 和打开图形元数据。配置 SEO 和打开图形元数据查阅 [Jekyll SEO Tag 使用指南](https://jekyll.github.io/jekyll-seo-tag/usage/)。

### 快速开始：使用 GitHub Pages 远程版式

1. 添加『文档而已』到 Jekyll 站点的 `_config.yml` 文件中的 [remote theme](https://blog.github.com/2017-11-29-use-any-theme-with-github-pages/) 参数
```yaml
remote_theme: pmarsceill/just-the-docs
```
<small>You must have GitHub Pages enabled on your repo, one or more Markdown files, and a `_config.yml` file. [See an example repository](https://github.com/pmarsceill/jtd-remote)</small>

### 本地化安装：使用基于 GEM 的版式

1. Install the Ruby Gem
```bash
$ gem install just-the-docs
```
```yaml
# .. or add it to your your Jekyll site’s Gemfile
gem "just-the-docs"
```
2. Add Just the Docs to your Jekyll site’s `_config.yml`
```yaml
theme: "just-the-docs"
```
3. _Optional:_ Initialize search data (creates `search-data.json`)
```bash
$ bundle exec just-the-docs rake search:init
```
3. Run you local Jekyll server
```bash
$ jekyll serve
```
```bash
# .. or if you're using a Gemfile (bundler)
$ bundle exec jekyll serve
```
4. Point your web browser to [http://localhost:4000](http://localhost:4000)

If you're hosting your site on GitHub Pages, [set up GitHub Pages and Jekyll locally](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll) so that you can more easily work in your development environment.

### 配置『文档而已』

- [See configuration options]({{ site.baseurl }}{% link docs/configuration.md %})

---

## 关于项目

Just the Docs is &copy; 2017-{{ "now" | date: "%Y" }} by [Patrick Marsceill](http://patrickmarsceill.com).

### 许可

Just the Docs is distributed by an [MIT license](https://github.com/pmarsceill/just-the-docs/tree/master/LICENSE.txt).

### 参与

When contributing to this repository, please first discuss the change you wish to make via issue,
email, or any other method with the owners of this repository before making a change. Read more about becoming a contributor in [our GitHub repo](https://github.com/pmarsceill/just-the-docs#contributing).

#### Thank you to the contributors of Just the Docs!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"/></a>
  </li>
{% endfor %}
</ul>

### Code of Conduct

Just the Docs is committed to fostering a welcoming community.

[View our Code of Conduct](https://github.com/pmarsceill/just-the-docs/tree/master/CODE_OF_CONDUCT.md) on our GitHub repository.
