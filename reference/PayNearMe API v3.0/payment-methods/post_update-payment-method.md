---
title: /update_payment_method
excerpt: >-
  Use the <code>/update_payment_method</code> endpoint to retire or deactivate a
  payment method.<h2>Retiring a Payment Method</h2> When a payment method is
  "retired" <ul><li>The <code>payment_method_identifier</code> will not be
  returned in the <code>/find_order</code> or <code>/find_payment_methods</code>
  responses</li><li>The payment method will not display in the PayNearMe
  Business Portal, Agent Interface, or on the Select Payment Method screen of
  the Consumer Portal</li><li>The retired <code>payment_method_identifier</code>
  can be used in the <code>/make_payment</code> call to complete a
  payment.</li></ul> Use <code>retire_payment_method=true</code> to retire the
  payment method in either the <code>/create_payment_method</code> or
  <code>/update_payment_method</code> calls. To "unretire" a payment method so
  that it will display again in the places listed above, use
  <code>retire_payment_method=false</code>. <h2>Deactivating a Payment
  Method</h2>When a payment method is "deactivated" <ul><li>The
  <code>payment_method_identifier</code> will not be returned in the
  <code>/find_order</code> or <code>/find_payment_methods</code>
  responses.</li><li>The payment method will not display on the Select Payment
  Method screen of the Consumer Portal.</li><li>The payment method will display
  as <b>Inactive</b> in the PayNearMe Business Portal and Agent
  Interface.</li><li>The deactivated <code>payment_method_identifier</code> will
  automatically decline payments for all transaction attempts.</li><li>The
  deactivated payment method cannot be reactivated by submitting
  <code>deactivate_payment_method=false</code>. It can only be reactivated by
  re-adding it via the <code>/create_payment_method</code> endpoint.</li></ul>
  To deactivate a payment method, use
  <code>deactivate_payment_method=true</code>.
api:
  file: Jay.json
  operationId: post_update-payment-method
hidden: false
---