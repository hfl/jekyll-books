---
layout: default
title: 搜索
nav_order: 7
---

# 搜索
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}

---

『文档而已』使用 [lunr.js](http://lunrjs.com) 提供基于 Jekyll 生成的 JSON 索引的客户端搜索。
所有搜索结果使用一个自动完成样式的界面显示（没有单独的搜索结果页面）。
所有生成的 HTML 页面默认基于下面数据要素显示：

- 页面标题
- 页面内容
- 页面 URL

## 在配置中启用搜索

在站点的 `_config.yml` 文件中启用搜索：

```yaml
# 启用或关闭站点搜索
# 支持 true （默认值）或 false
search_enabled: true
```

### 搜索粒度

页面被分成可以单独搜索的部分，这些部分根据页面标题定义和划分，每部分均会在搜索结果中独立显示。

```yaml
# 页面被分成可以单独搜索的部分
# 支持值 1 - 6, 默认值： 2
search.heading_level: 2
```

### 搜索预览

搜索结果可以预览——显示检索词在结果中的相关位置和内容。

```yaml
# 检索结果最大值
# 默认值： 3
search.previews: 3

# 预览中匹配搜索词前显示的最大单词数
# 默认值： 5
search.preview_words_before: 5

# 预览中匹配搜索词后显示的最大单词数
# 默认值： 10
search.preview_words_after: 10
```

### 搜索分词器

默认情况下，连字符用于分隔搜索词：`gem-based` 等效于 `gem based`，匹配任一单词。允许搜索带连字符的单词：

```yaml
# 设置搜索分词器
# 默认值： /[\s\-/]+/
# 示例：启用连字符搜索关键词支持
search.tokenizer_separator: /[\s/]+/
```

### 搜索结果中显示 URL

```yaml
# 搜索结果中显示 url
# 支持 true （默认值）或者 false
search.rel_url: false
```

### 显示搜索按钮

在屏幕右下角显示搜索按钮，点击可跳至搜索框。

```yaml
# 启用或者关闭在页面右下角显示搜索按钮
# 支持 true 或 false （默认值）
search.button: true
```


## 不参与搜索页面

有些时候，有些页面不需要被索引并且被搜索到，例如 404 页面。
从搜索中去除一个页面，添加 `search_exclude: true` 参数到该页面的
 YAML 前导数据：

#### 示例
{: .no_toc }

```yaml
---
layout: default
title: Page not found
nav_exclude: true
search_exclude: true
---
```


## 使用 GEM 生成搜索索引

如果您想要使用『文档而已』做远程主题，下列步骤则大可不必。

如果您使用 gem 版式，则必须运行 `rake` 命令联合 `just-the-docs` 进行初始化：

```bash
$ bundle exec just-the-docs rake search:init
```

此命令创建 `assets/js/zzzz-search-data.json` 文件，Jekyll 使用该文件创建搜索索引。
当然，您可以参照[此内容]({{ site.github.repository_url }}/blob/master/assets/js/zzzz-search-data.json)手动创建文件。
