---
title: /reverse_payment
excerpt: >-
  Use the <code>/reverse_payment</code> endpoint to either cancel or refund a
  payment. Set <code>void_if_not_settled</code> to <code>true</code> to
  completely cancel a payment that has not settled. The cutoff times for the
  cancellation window varies by card network and your site’s ACH submission
  timelines. Settled payments must be refunded by submitting the
  <code>refund_amount</code> and <code>refund_currency</code> parameters. This
  call gives you the ability to refund both full and partial amounts.
api:
  file: Jay.json
  operationId: post_reverse-payment
hidden: false
---