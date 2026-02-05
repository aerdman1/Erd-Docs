---
title: /cancel_order
excerpt: >-
  Use either the <code>pnm_order_identifier</code> or the
  <code>site_order_identifier</code> to find the active order you want to cancel
  immediately. Consumers cannot make payments against cancelled orders. After
  cancelling, the <code>order_status</code> will display as <code>closed</code>
  and the <code>order_closed_reason</code> displays as <code>canceled</code>.
api:
  file: Jay.json
  operationId: post_cancel-order
hidden: false
---