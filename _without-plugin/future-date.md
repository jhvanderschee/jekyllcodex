---
title: "Future date"
inactive: true
---

### Introduction

This page is coming soon... Do not want to wait? Send me an email on <a href="mailto:jhvanderschee@gmail.com" style="color: #777777;">jhvanderschee@gmail.com</a>.

[expand]

```
{% raw %}<script>
function getCompareDate() {
    var d = new Date(),
        month = '' + (d.getMonth() + 1),
        day = '' + d.getDate(),
        year = d.getFullYear();
    if (month.length < 2) month = '0' + month;
    if (day.length < 2) day = '0' + day;
    return [year, month, day].join('');
}
$('[future-date]').each(function() {
    if($(this).attr('future-date') < getCompareDate()) $(this).hide();
});
</script>{% endraw %}
```

[/expand]

### Installation

Step 1. Make sure the containing element you want to test has the 'future-date' attribute, like this: `<div future-date="20101225">item</div>`
Step 2. Download the file [future-date.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/future-date.html)<br>
Step 3. Save the file in the '_includes' directory of your project<br>
Step 4. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
{% include future-date.html %}
</body>
</html>{% endraw %}
```