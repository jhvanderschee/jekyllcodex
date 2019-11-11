---
title: Breadcrumbs
---

### Introduction

Breadcrumb paths are a single line of links (often placed above the title) that show a page's location in the site hierarchy. Every website should have breadcrumbs, as it benefits SEO as well as the users understanding of the sites structure.

### How it works

This code looks at the path of the current page to destill the breadcrumb path. This approach has a small footprint, as only the current page has to be consulted during the build of the breadcrumbs. Additionally, this code does not require the breadcrumbs to be explicitly defined in the front matter / YML. This means the path can be defined by your file and folder structure or by your (native Jekyll) path variables. The following code looks at the permalink and translates it into a breadcrumb/path.

[expand]

```
{% raw %}<div id="breadcrumbs">
{% assign crumbs = page.url | remove:'/index.html' | split: '/' %}
<a href="/">Home</a>
{% for crumb in crumbs offset: 1 %}
  {% if forloop.last %}
    / {{ page.title }}
  {% else %}
    / <a href="{% assign crumb_limit = forloop.index | plus: 1 %}{% for crumb in crumbs limit: crumb_limit %}{{ crumb | append: '/' }}{% endfor %}">{{ crumb | replace:'-',' ' | remove:'.html' | capitalize }}</a>
  {% endif %}
{% endfor %}
</div>{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [breadcrumbs.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/breadcrumbs.html)
<br />Step 2. Save the file in the ‘_includes’ directory of your project
<br />Step 3. Add the following line to your layout on the place where you want the breadcrumbs to appear:

```
{% raw %}{% include breadcrumbs.html %}{% endraw %}
```