---
title: Improvements to the form builder
date: 2018-12-09 20:03:37 Z
---

Today I have made some improvements to the form builder. It is now possible to have multiple forms on one page. I also added Netlify as a form engine. Netlify is a hosting platform for static websites that can also handle form submissions. Note that Netlify's free plan limits you to 100 submissions per month. If your website sends more forms you will be bumped to the paid plan, which starts at a hefty 45 dollar a month. Therefore you need to enable a recaptcha on your form (otherwise you will end up paying for the spam submissions alone). To do so I added 'recaptcha' as a new 'input type'. 

If you use Netlify as your form engine, you only need to write this in your form builder:

```
- name: recaptcha
  input_type: recaptcha
  placeholder:
  required: true
```

If you do NOT use Netlify as your form engine, but one of the others (cloudcannon, formspree or formbucket), you need to write this:

```
- name: recaptcha
  input_type: recaptcha
  placeholder: [your recaptcha site-key]
  required: true
```

Additionally you need to add this to your head (non-Netlify only):

    {% raw %}{% if page.forms %}<script src='https://www.google.com/recaptcha/api.js'></script>{% endif %}{% endraw %}
    
Note that the above code assumes you use the latest version of the [form builder](/without-plugin/form-builder/). Happy coding!