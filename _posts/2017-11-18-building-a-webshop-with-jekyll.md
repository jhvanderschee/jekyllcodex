---
title:  "Building a webshop with Jekyll"
---

This has been on my wish-list for almost 2 years now... Building a simple webshop in Jekyll without paying a monthly fee to a third party. And I have finally succeeded!

### Step 1. Create a Mollie account

You start with creating a Mollie account. After creating a Mollie account you need to register your website. Mollie will verify if you have a proper return policy, clearly mentioned company data and clear general terms and conditions. Once your website is approved you can add payment methods, like Creditcard, PayPal and iDeal (a Dutch payment method).

### Step 2. Create a Plink account

Go to [https://useplink.com](https://useplink.com){: .gray} and register. Within your Mollie dashboard you can click on your profile and select 'Payment links' to go to your Plink account. 

### Step 3. Create a payment link

When you create a payment link, choose for a reusable link with a variable amount and a variable description.

https://useplink.com/payment/ssMgtkddEzgC4rKKJJ9T/{{ amount }}/{{ description }}

### Step 4. Insert the payment link in the cart

Add your personal link in the {% assign paymentlink = https://useplink.com/payment/ssMgtkddEzgC4rKKJJ9T/ %}