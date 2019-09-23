---
title: Form builder
inactive: false
---

### Introduction

Forms are the most important parts of a websites. They range from simple [contact forms](/contact){: .gray} to forms that handle complete webshop orders or event sign-ups. WordPress has extremely popular form solutions, like 'Contact Form 7' and 'Gravity Forms', but Jekyll does not. To fill this void I created a basic form builder for Jekyll.

### How it works

The form uses Twitter Bootstrap and HTML5. The form can be submitted by CloudCannon, Formspree and FormBucket. The first only works on CloudCannon hosting. You can choose between showing placeholders in the inputs or labels above it. Two special fields are available: a field named 'name' (type 'text') will show 'first name' and 'last name' input boxes on one line. A field named 'address' (type 'text') will show 'address', 'city' and 'postal code' input boxes.

To create a form, add the following code to the front matter of your page:

```
{% raw %}---
forms:
  - to: jhvanderschee@gmail.com
    subject: New submission!
    redirect: /
    form_engine: formspree
    placeholders: false
    fields: 
      - name: name
        input_type: text
        placeholder: Name
        required: true
      - name: email
        input_type: email
        placeholder: Email address
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
        placeholder: Message
        required: false
      - name: terms
        input_type: checkbox
        placeholder: I accept the terms and conditions
        required: true
      - name: submit
        input_type: submit
        placeholder: Submit form
        required: true
---{% endraw %}
```

And add this to your layout:

```
{% raw %}{% if page.forms[0] %}{% include form.html form="1" %}{% endif %}{% endraw %}
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
  - recaptcha

form_engines:
  - cloudcannon
  - formspree
  - formbucket
  - netlify{% endraw %}
```

Disclaimer: Note that there is no select (dropdown) support (yet). Also note that browser support is not perfect. The native HTML5 date picker is not available in every browser and that HMTL5 validation does not work in IE9 and Opera Mini. Use [better forms](/without-plugin/better-forms){: .gray}, if you want HTML5 validation support for all browsers.

[/expand]

### Installation

Step 1. Make sure your front matter of your page looks like the example above<br>
Step 2. Download the file [form.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/form.html)<br>
Step 3. Save the file in the '_includes' directory of your project<br>
Step 4. Add the following line to your layout on the place where you want the form to appear:

```
{% raw %}{% if page.forms[0] %}{% include form.html form="1" %}{% endif %}{% endraw %}
```