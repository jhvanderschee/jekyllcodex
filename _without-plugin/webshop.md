---
title: "Webshop"
inactive: true
---

### Introduction

This is a simple webshop with payment methods that do not require a monthly fee. Look at the donate page for its current state. It is not yet finished and I will update this page very soon.

### How it works
 webshop basically works like this: you create a link with an 'addtocart' class that links to the cart. This link will look for the 'price' and 'description' attribute and add the product to the cart cookie. When you click 'checkout' in the cart you go to a checkout form. This forms adds additional data to the cart cookie. When you click the next step in the payment process, you go to a payment link from Plink (Mollie). Before sending the user to the payment link the cart info will be submitted through email. After succesful payment the user gets redirected to your websites (by Plink). 

[expand]

When you do not want to use the cart, simply use these links (not yet implemented):

```
{% raw %}<a href="/checkout" class="buy" price="1.00" description="test">Buy</a>{% endraw %}
```

[/expand]

### Installation

Before you can add the webshop you need to [create a Mollie account](https://www.mollie.com){: .gray}. Mollie will ask you to register your website. They will verify if you have a proper return policy, clearly mentioned company data and clear general terms and conditions. Once your website is approved by Mollie you can add payment methods. Go to [https://useplink.com](https://useplink.com){: .gray} and register. Within your Mollie dashboard you can click on your profile and select 'Payment links' to go to your Plink account. Create a re-usable link with a variable amount and description. Once you have done that, you are ready to add the webshop to your website.

#### Step 1. Add the footer include with the payment link

Download [webshop.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/webshop.html) and add it to your '_includes' folder. Make sure the bottom of your layout document looks like this (the paymentlink should be your personal re-usable link you just created):

```
{% raw %}...
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
{% include webshop.html paymentlink="https://useplink.com/payment/ssMgtkddEzgC4rKKJJ9T" %}
</body>
</html>{% endraw %}
```

#### Step 2. Add the cart and checkout files

First, download [cart.md](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/cart.md) and [checkout.md](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/checkout.md) and save them in the root of your site. Next, download [cart.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/cart.html) and [checkout.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/checkout.html) and save them in your '_includes' directory.

#### Step 3. Create some product links

Create some product links. They should look roughly like this:

```
{% raw %}<a href="/cart" class="addtocart" price="1.00" description="test">Add to cart</a>{% endraw %}
```

### Questions?

Once you got it running, you can fine-tune everything by editing the Liquid/HTML code. Are you unable to figure out how to create nice product pages with product variants? Just look at the source code of this website on Github. Still need help? Ask a question on Stack Overflow, or pay me to help you.