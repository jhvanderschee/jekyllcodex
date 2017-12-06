---
title:  "Building a webshop with Jekyll"
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

Although I know that this webshop is far from perfect, it allow you to sell products in almost any country, for a very small fee. Things that are currently missing, but you could easily add are a thank you page and a seperate delivery address. Tax calculations, based on country and delivery prices are also missing, but would be a little bit harder to add. 

Adding these missing things is still on my to-do list. I will update this post once they are added.

Things that are not included in this webshop *by design* are:

- Automatic invoices
- Track and trace codes for parcels