---
title: /create_payment_method
excerpt: >-
  Enables you to create a credit/debit card, ACH, PayPal, or Venmo payment
  method while returning the <code>payment_method_identifier</code>. Use this
  endpoint to just create and tokenize payment methods or to simultaneously
  create the payment method and send a payment. The following parameters are
  required when creating payment
  methods:<ul><li><code>pnm_order_identifier</code></li><li><code>payment_method_type</code></li></ul><h2>Credit
  and Debit Cards</h2>When creating credit or debit card payment methods, be
  sure to include the following required
  parameters:<ul><li><code>payment_method_card_number_pii</code></li><li><code>payment_method_card_expiry_pii</code></li><li><code>payment_method_cvv_pii</code></li><li><code>payment_method_billing_name</code></li><li><code>payment_method_billing_address</code></li><li><code>payment_method_billing_zipcode</code></li><li><code>payment_method_billing_phone</code>
  (Can be made an optional parameter)</li></ul><h2>Bank Accounts</h2>When
  creating ACH payment methods, be sure to include the following required
  parameters:<ul><li><code>payment_method_billing_name</code></li><li><code>payment_method_billing_zipcode</code></li><li><code>payment_method_ach_aba_pii</code></li><li><code>payment_method_ach_account_pii</code></li></ul><h2>PayPal
  and Venmo</h2>When creating a PayPal payment method, be sure to include the
  <code>payment_method_paypal_account_id</code> parameter. For Venmo payment
  methods, include the <code>payment_method_venmo_username</code>
  parameter.<h2>Sending the Payment</h2>If you want to send payment at the same
  time you create the payment method, be sure to include the following required
  parameters:<ul><li><code>send_payment=true</code></li><li><code>payment_amount</code></li><li><code>payment_currency</code></li></ul>
api:
  file: Jay.json
  operationId: post_create-payment-method
hidden: false
---