---
title: /create_order
excerpt: >-
  With PayNearMe, an order is required any time money moves or is scheduled to
  move. Orders can be created or “staged” at the time of payment where each
  transaction has a unique Order ID (via the <code>/create_order</code> API
  call) or can be created beforehand as reusable  identifiers for consumers (via
  an SFTP bulk file upload). At a minimum, the following parameters are required
  to create an
  order:<ul><li><code>order_amount</code></li><li><code>order_currency</code></li><li><code>site_customer_identifier</code></li><li><code>order_type</code></li><li><code>order_is_standing</code></li></ul>
api:
  file: Jay.json
  operationId: post_create-order
hidden: false
---