---
title: Checkout
layout: checkout
form:
  to: jhvanderschee@gmail.com
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
    - name: address
      input_type: email
      placeholder: Email address
      required: true
    - name: message
      input_type: textarea
      placeholder: Message
      required: true
    - name: terms
      input_type: checkbox
      placeholder: I accept the terms and conditions
      required: true
    - name: submit
      input_type: submit
      placeholder: Proceed to payment
      required: true
---

Fill the form below and press the 'Proceed to payment' button.