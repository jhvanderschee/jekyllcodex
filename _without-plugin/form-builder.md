---
title: "Form builder"
inactive: false
---

### Introduction

Forms are really important in websites. They come in all shapes and sizes. They range from a simple [contact form](/contact){: .gray} to forms that handle webshop orders or event sign-ups. WordPress has the extremely popular 'Contact Form 7' and 'Gravity Forms' plugins, but Jekyll does not have such a plugin (yet). To fill this void I created a basic form builder for Jekyll.

### How it works

Add this to your pages front matter:

```
{% raw %}---
form:
  to: jhvanderschee@gmail.com
  subject: New submission!
  redirect: /
  form_engine: formspree
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

CloudCannon users should add the available options to their '_config.yml' file to make the experience for content editors even smoother.

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

Step 1. Make sure your front matter of your page looks like the example above<br>
Step 2. Download the file [form.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/form.html)<br>
Step 3. Save the file in the '_includes' directory of your project<br>
Step 4. Add the following line to your layout on the place where you want the form to appear:

```
{% raw %}{% if page.form %}{% include form.html %}{% endif %}{% endraw %}
```