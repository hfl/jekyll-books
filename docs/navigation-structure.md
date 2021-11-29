---
layout: default
title: 导航架构
nav_order: 5
---

# 导航架构
{: .no_toc }

<details open markdown="block">
  <summary>
    目录
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

## 主导航

『文档而已』的主导航在大屏界面会出现在页面左侧，小屏界面会出现在页面顶端（需要点击后出现）。主导航可以打造为多级菜单系统（可以有多层下级页面）。

默认情况下，除非定义了父页面，否则所有页面都将在主导航中显示为顶级页面（请参阅[带有子项的页面](#带有子项的页面)）。

---

## 页面排序

定义页面顺序可以在页面的 YAML 前导设定中使用 `nav_order` 参数设置。

#### 示例
{: .no_toc }

```yaml
---
layout: default
title: Customization
nav_order: 4
---
```

The parameter values determine the order of the top-level pages, and of child pages with the same parent. You can reuse the same parameter values (e.g., integers starting from 1) for the child pages of different parents.

The parameter values can be numbers (integers, floats) and/or strings. When you omit `nav_order` parameters, they default to the titles of the pages, which are ordered alphabetically. Pages with numerical `nav_order` parameters always come before those with strings or default `nav_order` parameters. If you want to make the page order independent of the page titles, you can set explicit `nav_order` parameters on all pages.

By default, all Capital letters come before all lowercase letters; you can add `nav_sort: case_insensitive` in the configuration file to ignore the case. Enclosing strings in quotation marks is optional.

> *Note for users of previous versions:* `nav_sort: case_insensitive` previously affected the ordering of numerical `nav_order` parameters: e.g., `10` came before `2`. Also, all pages with explicit `nav_order` parameters previously came before all pages with default parameters. Both were potentially confusing, and they have now been eliminated. 

---

## 排除页面

For specific pages that you do not wish to include in the main navigation, e.g. a 404 page or a landing page, use the `nav_exclude: true` parameter in the YAML front matter for that page.

#### 示例
{: .no_toc }

```yaml
---
layout: default
title: 404
nav_exclude: true
---
```

The `nav_exclude` parameter does not affect the [auto-generating list of child pages](#auto-generating-table-of-contents), which you can use to access pages excluded from the main navigation.

Pages with no `title` are automatically excluded from the navigation. 

---

## 带有子项的页面

Sometimes you will want to create a page with many children (a section). First, it is recommended that you keep pages that are related in a directory together... For example, in these docs, we keep all of the written documentation in the `./docs` directory and each of the sections in subdirectories like `./docs/ui-components` and `./docs/utilities`. This gives us an organization like:

```
+-- ..
|-- (Jekyll files)
|
|-- docs
|   |-- ui-components
|   |   |-- index.md  (parent page)
|   |   |-- buttons.md
|   |   |-- code.md
|   |   |-- labels.md
|   |   |-- tables.md
|   |   +-- typography.md
|   |
|   |-- utilities
|   |   |-- index.md      (parent page)
|   |   |-- color.md
|   |   |-- layout.md
|   |   |-- responsive-modifiers.md
|   |   +-- typography.md
|   |
|   |-- (other md files, pages with no children)
|   +-- ..
|
|-- (Jekyll files)
+-- ..
```

On the parent pages, add this YAML front matter parameter:
-  `has_children: true` (tells us that this is a parent page)

#### 示例
{: .no_toc }

```yaml
---
layout: default
title: UI Components
nav_order: 2
has_children: true
---
```

Here we're setting up the UI Components landing page that is available at `/docs/ui-components`, which has children and is ordered second in the main nav.

### 子页面
{: .text-gamma }

On child pages, simply set the `parent:` YAML front matter to whatever the parent's page title is and set a nav order (this number is now scoped within the section).

#### 示例
{: .no_toc }

```yaml
---
layout: default
title: Buttons
parent: UI Components
nav_order: 2
---
```

The Buttons page appears as a child of UI Components and appears second in the UI Components section.

### 自动生成目录

默认情况下，所有带有子页面的页面会在内容后自动生成子页面的目录。取消此功能，在父页面的 YAML 前导参数设置 `has_toc: false` 即可。

#### 示例
{: .no_toc }

```yaml
---
layout: default
title: UI Components
nav_order: 2
has_children: true
has_toc: false
---
```

### 含子页面的子页面
{: .text-gamma }

Child pages can also have children (grandchildren). This is achieved by using a similar pattern on the child and grandchild pages.

1. Add the `has_children` attribute to the child
1. Add the `parent` and `grand_parent` attribute to the grandchild

#### 示例
{: .no_toc }

```yaml
---
layout: default
title: Buttons
parent: UI Components
nav_order: 2
has_children: true
---
```

```yaml
---
layout: default
title: Buttons Child Page
parent: Buttons
grand_parent: UI Components
nav_order: 1
---
```

This would create the following navigation structure:

```
+-- ..
|
|-- UI Components
|   |-- ..
|   |
|   |-- Buttons
|   |   |-- Button Child Page
|   |
|   |-- ..
|
+-- ..
```

---

## 辅助链接

To add auxiliary links to your site (in the upper right on all pages), add it to the `aux_links` [configuration option]({{ site.baseurl }}{% link docs/configuration.md %}#aux-links) in your site's `_config.yml` file.

#### 示例
{: .no_toc }

```yaml
# Aux links for the upper right navigation
aux_links:
  "Just the Docs on GitHub":
    - "//github.com/pmarsceill/just-the-docs"
```

---

## 带页内目录导航的页面

要在文档页面生成目录，可以在 Markdown 的 `<ol>` 后使用 Kramdown 的 `{:toc}` 方法。这将基于页面各部分的标题自动生成一个带有锚点链接的有序列表。有时候您需要在页面中使用标题，却又不想让其出现在目录中，这时候就可以使用 `{: .no_toc }` 的 CSS 类来忽略某些标题。

#### 示例
{: .no_toc }

```markdown
# 导航架构
{: .no_toc }

## 目录
{: .no_toc .text-delta }

1. TOC
{:toc}
```

本示例在目录中忽略了页面名称标题（`#`），以及目录自己的标题（`##`），因为它是多余的，然后是目录。如果使用无序列表，用 `- TOC` 代替 `1. TOC`。

### 折叠目录

目录可以使用 `<details>` 和 `<summary>` 元素设置折叠，如下所示。属性 `open` （默认展开目录）和样式 `{: .text-delta }` 可选。

```markdown
<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>
```

效果如[页面顶端](#导航架构)（`{:toc}` 每个页面只能用一次）。
