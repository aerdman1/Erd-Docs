---
title: /get_smart_token
excerpt: >-
  A <code>secure_smart_token</code> is a unique string of encrypted data values
  that authenticate PayNearMe orders within your app or website that is running
  the [Embedded
  Client](https://apidocs.paynearme.com/devdocs/docs/embedded-client-for-consumers).
  The button used to invoke the PayNearMe JS Library requires a Smart Token to
  initialize the timed session within the iframe. Smart Tokens can be configured
  at the Site level to expire after a set amount of time or can remain the same
  for the duration of the order’s lifetime.</br></br>How you generate Smart
  Tokens will depend on how you configure orders. If consumers will be making
  payments at the time of order generation, use the
  [/create_order](https://apidocs.paynearme.com/devdocs/reference/post_create-order)
  call. If payments will be made after order generation, use the
  <code>/get_smart_token</code> call to regenerate an expired token for an
  existing order. A typical implementation uses the
  <code>/get_smart_token</code> call after creating orders via bulk upload. To
  regenerate the Smart Token for a specific order, use one of the following
  values:<ul><li><code>pnm_order_identifier</code></li><li><code>site_order_identifier</code></li><li><code>pnm_customer_identifier</code></li><li><code>site_customer_identifier</code></li><li><code>site_creator_identifier</code></li></ul><h2>Configuring
  the Smart Link</h2> The encrypted Smart Link URL (i.e.,
  <code>secure_smart_link</code>) returned in the
  [/create_order](https://apidocs.paynearme.com/devdocs/reference/post_create-order),
  [/find_order](https://apidocs.paynearme.com/devdocs/reference/post_find-orders),
  and
  [/get_smart_token](https://apidocs.paynearme.com/devdocs/reference/post_get-smart-token)
  API responses contains all the consumer data passed in with the order and will
  display all payment types configured for the merchant site. To enforce
  specific flows or define specific redirect URLs, use the
  <code>/get_smart_token</code> call to customize the behavior of the Smart
  Link. For more information on configuring an encrypted Smart Link see
  [Customizing the Secure Smart
  Link](https://apidocs.paynearme.com/devdocs/docs/customizing-the-secure-smart-link).
  Use the following parameters to put the consumer in a specific payment flow in
  the Embedded
  Client:<ul><li><code>flow_debit</code></li><li><code>flow_credit</code></li><li><code>flow_ach</code></li><li><code>flow_retailer</code></li><li><code>flow_apple_pay</code></li><li><code>flow_google_pay</code></li><li><code>flow_paypal</code></li><li><code>flow_venmo</code></li><li><code>flow_pin4</code></li><li><code>flow_push_debit</code></li><li><code>flow_push_ach</code></li><li><code>flow_cash_app</code></li><li><code>flow_push_paypal</code></li><li><code>flow_secure_all</code></li><li><code>flow_edit_schedule</code></li><li><code>flow_tokenize</code></li><li><code>flow_hide_saved_payment_methods</code></li></ul>To
  specify an expiration date for the Smart Link or return URLs for specific
  outcomes that can occur in the Embedded Client (e.g., errors, link expiration,
  etc.), use the following
  parameters:<ul><li><code>link_lifetime_seconds</code></li><li><code>short_order_url</code></li><li><code>flow_pay_url</code></li><li><code>flow_no_pay_url</code></li><li><code>flow_add_url</code></li><li><code>flow_no_add_url</code></li><li><code>flow_return_url</code></li><li><code>flow_expired_url</code></li><li><code>flow_error_url</code></li><li><code>flow_venmo_return_url</code></li><li><code>flow_show_all_ppas</code></li></ul><h2>Guaranteed
  ACH</h2> Gaming Operators on the [PayNearMe for
  iGaming](https://apidocs.paynearme.com/devdocs/docs/igaming-overview) platform
  can use the <code>/get_smart_token</code> call to initiate Guaranteed ACH
  transactions using Trustly. To initiate a Guaranteed ACH transaction, include
  the following parameters along with the other required parameters for
  <code>/get_smart_token</code>
  calls:<ul><li><code>flow_trustly=true</code></li><li><code>ext_customer_enrollment_date</code></li><li><code>ext_customer_date_of_birth_pii</code></li><li><code>ext_customer_tax_id_pii</code></li><li><code>flow_bank_oauth_redirect_url</code></li></ul></br>For
  more information on PayNearMe's Guaranteed ACH solution, see the [Guaranteed
  ACH](https://apidocs.paynearme.com/devdocs/docs/guaranteed-ach) guide.
api:
  file: Jay.json
  operationId: post_get-smart-token
hidden: false
---