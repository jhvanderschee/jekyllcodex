---
title: Future dates
---

### Introduction

In case of an event listing, you want to show only future dates. This is hard, because Jekyll only knows what day it is on rebuild, which can be days or months ago. Therefore we need a javascript solution to solve this problem.

### How it works

The script gets the current date in the 'yyyy-mm-dd' format from Javascript. You only have to write the events date as a custom attribute called 'future-date' to the containing HTML element with Jekyll/Liquid and the script will remove elements that have a 'future-date' in the past. Note that these elements can be any type of element, a list item or a link will work too.

[expand]

An example of the Jekyll/Liquid code:

```
{% raw %}{% for item in site.events %}
  <div future-date="{{ item.date | date: '%Y-%m-%d' }}">...</div>
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
    var elements = document.querySelectorAll('[future-date]');
    Array.prototype.forEach.call(elements, function(el, i){
        if(el.getAttribute('future-date').split('-').join('') < getCompareDate()) el.remove();
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
{% include future-date.html %}
</body>
</html>{% endraw %}
```