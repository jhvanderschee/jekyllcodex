---
title: Building a webshop with Jekyll
date: 2017-11-18 00:00:00 Z
---

This has been on my wish-list for almost two years now: building a simple webshop in Jekyll without paying a monthly fee to a third party. And I have finally succeeded! To see how it works, please visit my [donate page](/donate). The webshop requires just two settings, the email address for the confirmation and your Plink payment link. Setup can be done in minutes and only requires a Mollie account. There are no limitations on the layout of the product pages. It uses HTML API, a principle on which Lea Verou from MIT has done a decent amount of research and is proven to be easy to implement. In the donate page I have shown how this can work for product variants.

The webshop accepts all payment methods from Mollie:

- Mastercard
- Visa
- American Express
- PayPal
- SEPA Bank Transfer
- SEPA Direct Debit
- Bitcoin
- SOFORT Banking
- iDEAL
- Bancontact
- KBC/CBC Payment Button
- Belfius Pay Button
- paysafecard
- CartaSi
- Cartes Bancaires
- Gift cards

This webshop is far from perfect. It has no stock keeping, no VAT calculations and no automated invoices. However, this webshop does allow you to sell products in almost any country for a very small fee. All fields in the checkout form are automagically added to your confirmation email and when you add radio buttons with a price and description, these values will be added to the order (i.e. gift wrapping or shipping method).

