---
title: /refund_payment
excerpt: >-
  Use the <code>pnm_payment_identifier</code> to refund a payment for the full
  or partial amount. Include the <code>refund_amount</code> and the
  <code>refund_currency</code> parameters for partial-amount
  refunds.</br></br>Only processed payments can be refunded. For ACH payments,
  this is after the daily batch transfer to the bank. For cards, the cutoff time
  is based on the card processing network.
api:
  file: Jay.json
  operationId: post_refund-payment
hidden: false
---