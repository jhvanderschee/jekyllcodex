---
title: Contact
form:
  to: jhvanderschee@gmail.com
  subject: New submission!
  redirect: /
  form_engine: formspree
  placeholders: true
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
      placeholder: I would accept the terms and conditions (if there were any)
      required: true
    - name: submit
      input_type: submit
      placeholder: Submit this form
      required: true
---

## About this page

Although the primary function of this page/form is to illustrate how the [form builder](/without-plugin/form-builder){: .gray} works, it will actually send an email to my inbox. It uses [Formspree](https://formspree.io){: .gray} to do so, as this website is hosted on GitHub.

## Contact form

Feel free to leave me a (nice) message. Have a nice day!