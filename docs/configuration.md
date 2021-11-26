---
layout: default
title: 配置
nav_order: 2
---

# 配置
{: .no_toc }


『文档而已』可以在 `_config.yml` 文件中定义一些 Jekyll 站点的规范配置参数。
{: .fs-6 .fw-300 }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---


查看站点 [_config.yml](https://github.com/pmarsceill/just-the-docs/tree/master/_config.yml) 文件示例。

## 站点标志

```yaml
# 设置替换标题的标志 path/url
logo: "/assets/images/just-the-docs.png"
```

## 搜索

```yaml
# 启用或者关闭站点搜索
# 主持 true （默认）或者 false
search_enabled: true

search:
  # Split pages into sections that can be searched individually
  # Supports 1 - 6, default: 2
  heading_level: 2
  # Maximum amount of previews per search result
  # Default: 3
  previews: 3
  # Maximum amount of words to display before a matched word in the preview
  # Default: 5
  preview_words_before: 5
  # Maximum amount of words to display after a matched word in the preview
  # Default: 10
  preview_words_after: 10
  # Set the search token separator
  # Default: /[\s\-/]+/
  # Example: enable support for hyphenated search words
  tokenizer_separator: /[\s/]+/
  # Display the relative url in search results
  # Supports true (default) or false
  rel_url: true
  # Enable or disable the search button that appears in the bottom right corner of every page
  # Supports true or false (default)
  button: false
```

## 辅助链接

```yaml
# Aux links for the upper right navigation
aux_links:
  "Just the Docs on GitHub":
    - "//github.com/pmarsceill/just-the-docs"

# Makes Aux links open in a new tab. Default is false
aux_links_new_tab: false
```

## 标题锚点链接

```yaml
# 标题锚点链接在页面内容的 h1 到 h6 级标题悬停时显示，用于用户链接到页面内指定内容。
#
# 支持 true （默认值）或者 false
heading_anchors: true
```

## 页尾内容

```yaml
# 页尾内容
# 出现在每页内容的结尾处
# 注意：footer_content 选项已弃用，可能会在未来的主要版本中删除。  请使用`_includes/footer_custom.html` 以获得更强大的功能。 
footer_content: "Copyright &copy; 2017-2020 Patrick Marsceill. Distributed by an <a href=\"https://github.com/pmarsceill/just-the-docs/tree/master/LICENSE.txt\">MIT license.</a>"

# 页尾最后更新时间
last_edit_timestamp: true # show or hide edit time - page must have `last_modified_date` defined in the frontmatter
last_edit_time_format: "%b %e %Y at %I:%M %p" # uses ruby's time format: https://ruby-doc.org/stdlib-2.7.0/libdoc/time/rdoc/Time.html

# 页尾 "在 GitHub 编辑此页" 链接文字
gh_edit_link: true # 显示或隐藏编辑此页链接
gh_edit_link_text: "在 GitHub 编辑此页。"
gh_edit_repository: "https://github.com/pmarsceill/just-the-docs" # 您的 github 仓储 URL
gh_edit_branch: "master" # 您的文档分支
# gh_edit_source: docs # 源文件目录
gh_edit_view_mode: "tree" # "tree" 或者 "edit" ，您想要用于立即跳转编辑器的方式
```

_注意：`footer_content` 已经弃用，但仍支持。更好的使用体验是将其功能移入`_includes/footer_custom.html`——内容将支持功能强大的标记语言 liquid。_

- the "page last modified" data will only display if a page has a key called `last_modified_date`, formatted in some readable date format
- `last_edit_time_format` uses Ruby's DateTime formatter; see examples and more information [at this link.](https://apidock.com/ruby/DateTime/strftime)
- `gh_edit_repository` is the URL of the project's GitHub repository
- `gh_edit_branch` is the branch that the docs site is served from; defaults to `master`
- `gh_edit_source` is the source directory that your project files are stored in (should be the same as [site.source](https://jekyllrb.com/docs/configuration/options/))
- `gh_edit_view_mode` is `"tree"` by default, which brings the user to the github page; switch to `"edit"` to bring the user directly into editing mode

## 色彩方案

```yaml
# 色彩方案支持 "亮色" (默认) 和 "暗色"
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

查看[定制]({{ site.baseurl }}{% link docs/customization.md %})获取详细信息。

## Google 分析

```yaml
# Google 访问分析追踪（可选）
# e.g, UA-1234567-89
ga_tracking: UA-5555555-55
ga_tracking_anonymize_ip: true # Use GDPR compliant Google Analytics settings (true by default)
```

## 文档专题集合

默认情况下导航和搜索包含普通[页面](https://jekyllrb.com/docs/pages/)。当然，也可以使用 [Jekyll 集合（collections）](https://jekyllrb.com/docs/collections/)从语义上对页面归类。

例如，将所有文档文件放入 `_docs` 文件夹，然后创建 `docs` 集合：
```yaml
# 定义 Jekyll 集合
collections:
  # 定义一个叫做 "docs" 的集合，其文档位于 "_docs" 目录
  docs:
    permalink: "/:collection/:path/"
    output: true

just_the_docs:
  # 定义用于 just-the-docs 的集合
  collections:
    # 引用 "docs" 集合
    docs:
      # 设定集合名字
      name: Documentation
      # Exclude the collection from the navigation
      # Supports true or false (default)
      nav_exclude: false
      # Exclude the collection from the search
      # Supports true or false (default)
      search_exclude: false
```

You can reference multiple collections.
This creates categories in the navigation with the configured names.
```yaml
collections:
  docs:
    permalink: "/:collection/:path/"
    output: true
  tutorials:
    permalink: "/:collection/:path/"
    output: true

just_the_docs:
  collections:
    docs:
      name: Documentation
    tutorials:
      name: Tutorials
```

