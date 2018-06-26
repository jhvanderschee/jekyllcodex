---
title: "Future dates"
---

### Introduction

In case of an event listing, you want to show only future dates. This is hard, because Jekyll only knows what day it is on rebuild, which can be days or months ago. Therefore we need a javascript solution to solve this problem.

### How it works

Normal dates are hard to compare, but dates written as integers in the YYYYMMDD format are not. We let javascript get the current date in this format to compare with. We call this the 'CompareDate'. We write the events date as a custom attribute to the containing HTML element with Jekyll/Liquid. Note that this can be any type of element, a list item or a link will work too. In the same way you can add the custom attribute 'first-future-date' to your elements. This will instruct the javascript to hide all elements, except for the one with the first upcoming date.

[expand]

An example of the Jekyll/Liquid code:

```
{% raw %}{% for item in site.events %}
  <div future-date="{{ item.date | date: '%Y%m%d' }}">...</div>
{% endfor %}{% endraw %}
```

And the javascript, doing its magic:

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

Step 1. Make sure your elements look like this: `<div future-date="YYYYMMDD">...</div>`<br>
Step 2. Download the file [future-dates.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/future-dates.html)<br>
Step 3. Save the file in the '_includes' directory of your project<br>
Step 4. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="/js/jquery.min.js"></script>
{% include future-date.html %}
</body>
</html>{% endraw %}
```