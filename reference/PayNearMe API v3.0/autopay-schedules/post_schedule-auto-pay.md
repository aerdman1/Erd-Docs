---
title: /schedule_auto_pay
excerpt: >-
  Use either the <code>pnm_order_identifier</code> or the
  <code>site_order_identifier</code> to find the order for which you want to
  create a schedule of recurring transactions, or an autopay schedule. Only one
  autopay schedule can be defined for an order. Autopay schedules can be
  configured for the following frequencies:<ul><li><code>weekly</code> -
  Payments are made every week on the same day as the
  <code>auto_pay_start_date</code> (e.g., every
  Wednesday)</li><li><code>bi-weekly</code> - Payments are made every other week
  on the same day as the <code>auto_pay_start_date</code> (e.g., every other
  Wednesday)</li><li><code>monthly</code> - Payments are made each month on the
  same date as the <code>auto_pay_start_date</code> (e.g., the 20th of every
  month)</li><li><code>twice_monthly</code> - Payments are made twice a month on
  the dates specified in the <code>auto_pay_multi_first</code> and
  <code>auto_pay_multi_last</code> parameters, which are required for this
  autopay frequency (e.g., the 15th and 28th of every
  month)</li><li><code>end_of_month</code> - Payments are made on the last day
  of every month (e.g., the last day of every
  month)</li><li><code>due_date_monthly</code> - Payments are made on the due
  date provided by the client in their [Consumer Account
  File](https://paynearme-enterprise-group.readme.io/paynearme-devdocs/docs/learning-the-basics)</li></ul>
api:
  file: Jay.json
  operationId: post_schedule-auto-pay
hidden: false
---