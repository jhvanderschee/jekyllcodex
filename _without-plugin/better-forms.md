---
title: Better forms
---

### Introduction

This script makes your forms a pleasure to fill out. It shows graphical validation errors by adding a green thick mark after succesful validation and a red border on error WHILE you fill out your form. The script also allows you to leave the page/form and come back later without loosing your input. Finally the page will scroll animated to the first error in your form after an unsuccesful submit. You can test these features at this [example](/contact){: .gray}.

### How it works

It validates all fields with javascript on blur. It adds 'active', 'valid' and 'error' classes. This enables you to build all kind of nice features. The 'active' class, for example, can be used to create Material Design styled labels that look like placeholders and shrink to make place for the cursor. To make entered values persist, the script places a serialized cookie on your computer with all fields. The cookies name equals the id of the form. In the [form builder](/without-plugin/form-builder/){: .gray} the id of the form is generated and equal to the slugified page URL.

### Installation

Step 1. Download the file [better-forms.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/better-forms.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="/js/jquery.min.js"></script>
{% include better-forms.html %}
</body>
</html>{% endraw %}
```