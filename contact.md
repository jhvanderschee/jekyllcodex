---
title: Contact
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
---

## Contactform

Fill in the form below and I will get back to you ASAP.

{% if page.form %}{% include form.html %}{% endif %}