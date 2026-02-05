---
title: /cancel_payment
excerpt: >-
  Use the <code>pnm_payment_identifier</code> to cancel a payment. Only
  unprocessed payments can be canceled. For ACH payments, this is before the
  daily batch transfer to the bank. For cards, the cutoff time is based on the
  card processing network.
api:
  file: Jay.json
  operationId: post_cancel-payment
hidden: false
---