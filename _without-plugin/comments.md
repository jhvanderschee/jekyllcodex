---
title: "Comments"
inactive: false
comment_issue_id: 4
---

### Introduction

Being able to add comments to your posts is good for visitor engagement.

### How it works

Every comment tread is an issue on Github. The script adds a tread of comments to pages with a 'comment_issue_id'. The tread is added to the bottom of the (jQuery defined) element in the include .

### Installation

Step 1. Download the file [comments.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/comments.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="/js/jquery.min.js"></script>
{% include comments.html element=".post-content" github_account="jhvanderschee/jekyllcodex" %}
</body>
</html>{% endraw %}
```