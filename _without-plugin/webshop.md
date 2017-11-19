---
title: "Webshop"
inactive: true
---

### Introduction

This is a simple webshop with payment methods that do not require a monthly fee. Look at the donate page for its current state. It is not yet finished and I will update this page very soon.

### How it works

The web shop basically works like this: you create a link with an 'addtocart' class. This link will look for the 'price' and 'description' attribute and add them to a javascript cookie. When you click 'checkout' you go to a checkout form. This forms adds additional data to the javascript cookie. When you click the next step in the payment process, you go to a payment link from Plink (Mollie). After a succesful payment you get redirected to your websites success page (by Plink). 

### Installation

#### Step 1. Create a Mollie account

You start with creating a Mollie account. After creating a Mollie account you need to register your website. Mollie will verify if you have a proper return policy, clearly mentioned company data and clear general terms and conditions. Once your website is approved you can add payment methods, like Creditcard, PayPal and iDeal (a Dutch payment method).

#### Step 2. Create a Plink account

Go to [https://useplink.com](https://useplink.com){: .gray} and register. Within your Mollie dashboard you can click on your profile and select 'Payment links' to go to your Plink account. 

#### Step 3. Insert the payment link in the webshop

Add your personal link in the code by updating this: {% raw %}{% assign paymentlink = https://useplink.com/payment/ssMgtkddEzgC4rKKJJ9T/ %}{% endraw %}.