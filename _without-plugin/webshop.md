---
title: "Webshop"
inactive: true
---

### Introduction

This is a simple webshop with payment methods that do not require a monthly fee. Look at the donate page for its current state. It is not yet finished and I will update this page very soon.

### How it works

The webshop basically works like this: you create a link with an 'addtocart' class. This link will look for the 'price' and 'description' attribute and add them to a javascript cookie. When you click 'checkout' you go to a checkout form. This forms adds additional data to the javascript cookie. When you click the next step in the payment process, you go to a payment link from Plink (Mollie). Before sending the user to the payment link the cart info will be submitted through an email. After a succesful payment you get redirected to your websites success page (by Plink). 

### Installation

#### Step 1. Create a Mollie account

You start by [creating a Mollie account](https://www.mollie.com). Mollie will ask you to register your website. They will verify if you have a proper return policy, clearly mentioned company data and clear general terms and conditions. Once your website is approved by Mollie you can add [payment methods](https://www.mollie.com/en/payments).

#### Step 2. Create a Plink payment link

Go to [https://useplink.com](https://useplink.com) and register. Within your Mollie dashboard you can click on your profile and select 'Payment links' to go to your Plink account. Create a re-usable link with a variable amount and description.

#### Step 3. Add the footer include and the payment link

Make sure the bottom of your layout document looks like this (the paymentlink should be your personal re-usable link you just created):

```
{% raw %}...
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
{% include webshop.html paymentlink="https://useplink.com/payment/ssMgtkddEzgC4rKKJJ9T/" %}
</body>
</html>{% endraw %}
```

#### Step 4. Add the cart file to the root of your site

Get the cart.html file here (not yet available). Edit it to your liking.

#### Step 5. Add the checkout file to the root of your site

Get the checkout.html file here (not yet available). Edit it to your liking.