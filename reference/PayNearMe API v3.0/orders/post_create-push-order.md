---
title: /create_push_order
excerpt: >-
  Like orders, <code>push_orders</code> are a description of a payment
  obligation--the client's obligation to disburse funds to the consumer. Funds
  are disbursed to verified debit cards, bank accounts, or Paypal or Venmo
  wallets. Clients can opt to perform their own verification of the consumer or
  can use PayNearMe's verification services. The person who receives funds is
  known as a user and is identified with a <code>push_user_identifier</code>.
  Users can be created while creating the <code>push_order</code> or can be
  created in a separate <code>/create_user</code> call. Additionally, if you
  have the consumer/user's payment method information, you can use the
  <code>send_payment</code> option to immediately disburse the funds to
  his/her/their debit card, bank account, or mobile wallet.
api:
  file: Jay.json
  operationId: post_create-push-order
hidden: false
---