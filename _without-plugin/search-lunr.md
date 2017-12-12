---
title: Search with Lunr.js
---

### Introduction

Modern websites have a search bar, searching within the site for specific content. These search boxes often search the database in real-time. That is not possible within a static website. Therefore another solution must be found. An [demo](/search) can be found on the search page.

### How it works

This search relies on a local index. It uses the Lunr.js script to search. This script does not require jQuery. First a local index is build, using the documents variable. Then the Lunr.js code is called. Finally a custom-made function (called 'lunr_search') puts the results in a Google-like style on the screen. Below you will find the code. 

[expand]

```
{% raw %}<script src="/js/lunr.js"></script>

<script>
{% assign counter = 0 %}
var documents = [{% for page in site.pages %}{% if page.url contains '.xml' or page.url contains 'assets' %}{% else %}{
    "id": {{ counter }},
    "url": "{{ site.url }}{{ page.url }}",
    "title": "{{ page.title }}",
    "body": "{{ page.content | markdownify | replace: '.', '. ' | replace: '</h2>', ': ' | replace: '</h3>', ': ' | replace: '</h4>', ': ' | replace: '</p>', ' ' | strip_html | strip_newlines | replace: '  ', ' ' | replace: '"', ' ' }}"{% assign counter = counter | plus: 1 %}
    }, {% endif %}{% endfor %}{% for page in site.without-plugin %}{
    "id": {{ counter }},
    "url": "{{ site.url }}{{ page.url }}",
    "title": "{{ page.title }}",
    "body": "{{ page.content | markdownify | replace: '.', '. ' | replace: '</h2>', ': ' | replace: '</h3>', ': ' | replace: '</h4>', ': ' | replace: '</p>', ' ' | strip_html | strip_newlines | replace: '  ', ' ' | replace: '"', ' ' }}"{% assign counter = counter | plus: 1 %}
    }, {% endfor %}{% for page in site.posts %}{
    "id": {{ counter }},
    "url": "{{ site.url }}{{ page.url }}",
    "title": "{{ page.title }}",
    "body": "{{ page.date | date: "%Y/%m/%d" }} - {{ page.content | markdownify | replace: '.', '. ' | replace: '</h2>', ': ' | replace: '</h3>', ': ' | replace: '</h4>', ': ' | replace: '</p>', ' ' | strip_html | strip_newlines | replace: '  ', ' ' | replace: '"', ' ' }}"{% assign counter = counter | plus: 1 %}
    }{% if forloop.last %}{% else %}, {% endif %}{% endfor %}];

var idx = lunr(function () {
    this.ref('id')
    this.field('title')
    this.field('body')

    documents.forEach(function (doc) {
        this.add(doc)
    }, this)
});
function lunr_search(term) {
    document.getElementById('lunrsearchresults').innerHTML = '<ul></ul>';
    if(term) {
        document.getElementById('lunrsearchresults').innerHTML = "<p>Search results for '" + term + "'</p>" + document.getElementById('lunrsearchresults').innerHTML;
        //put results on the screen.
        var results = idx.search(term);
        if(results.length>0){
            //console.log(idx.search(term));
            //if results
            for (var i = 0; i < results.length; i++) {
                // more statements
                var ref = results[i]['ref'];
                var url = documents[ref]['url'];
                var title = documents[ref]['title'];
                var body = documents[ref]['body'].substring(0,160)+'...';
                document.querySelectorAll('#lunrsearchresults ul')[0].innerHTML = document.querySelectorAll('#lunrsearchresults ul')[0].innerHTML + "<li class='lunrsearchresult'><a href='" + url + "'><span class='title'>" + title + "</span><br /><span class='body'>"+ body +"</span><br /><span class='url'>"+ url +"</span></a></li>";
            }
        } else {
            document.querySelectorAll('#lunrsearchresults ul')[0].innerHTML = "<li class='lunrsearchresult'>No results found...</li>";
        }
    }
    return false;
}
</script>
<style>
    .lunrsearchresult .title {color: #d9230f;}
    .lunrsearchresult .url {color: silver;}
    .lunrsearchresult a {display: block; color: #777;}
    .lunrsearchresult a:hover, .lunrsearchresult a:focus {text-decoration: none;}
    .lunrsearchresult a:hover .title {text-decoration: underline;}
</style>


<form onSubmit="return lunr_search(document.getElementById('lunrsearch').value);">
    <p><input type="text" class="form-control" id="lunrsearch" name="q" maxlength="255" value="" placeholder="Search via Lunr.js" /></p>
</form>
<div id="lunrsearchresults">
    <ul></ul>
</div>{% endraw %}
```

[/expand]

### Installation

Step 1. Download the file [search-lunr.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/search-lunr.html)
<br />Step 2. Save the file in the '_includes' directory of your project
<br />Step 3. Download the file [lunr.js](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/js/lunr.js)
<br />Step 4. Save the file in the 'js' (root) directory of your project
<br />Step 5. Add the following statement to your layout where you want the search box to appear:

```
{% raw %}{% include search-lunr.html %}{% endraw %}
```