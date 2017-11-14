---
title: "Form builder"
inactive: false
---

### Introduction

This page is coming soon... Do not want to wait? Look at the <a href="/contact/" style="color: #777777; text-decoration: underline;">example form</a>.


### How it works

Add this to your pages front matter:

```
{% raw %}---
form:
  to: jhvanderschee@gmail.com
  subject: New submission!
  redirect: /
  form_engine: cloudcannon
  fields: 
    - name: name
      input_type: text
      placeholder: Your name
      required: true
    - name: email
      input_type: email
      placeholder: Your email address
      required: true
    - name: sex
      input_type: radio
      placeholder: male
      required: true
    - name: sex
      input_type: radio
      placeholder: female
      required: true
    - name: message
      input_type: textarea
      placeholder: Your message
      required: true
    - name: terms
      input_type: checkbox
      placeholder: I accept the terms and conditions
      required: true
    - name: submit
      input_type: submit
      placeholder: Submit this form
      required: true
---{% endraw %}
```

And add this to your layout:

```
{% raw %}{% if page.form %}{% include form.html %}{% endif %}{% endraw %}
```

As a CloudCannon user you can add some extra variables to your _config.yml file to make the experience for the content editor even smoother.

[expand]

```
{% raw %}input_types:
  - text
  - textarea
  - email
  - date
  - checkbox
  - radio
  - number
  - submit

form_engines:
  - cloudcannon
  - formspree{% endraw %}
```

[/expand]

### Installation

Step 1. Make sure your pages front matter looks like the example above<br>
Step 2. Download the file [form.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/form.html)<br>
Step 3. Save the file in the '_includes' directory of your project<br>
Step 4. Add the following line to your layout on the place where you want the form to appear:

```
{% raw %}{% include form.html %}{% endraw %}
```