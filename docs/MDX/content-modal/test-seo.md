---
title: Test SEO
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---


<Callout icon="⚠️" theme="warning">
**Warning**

This feature does not affect the synchronization between your JPDs. It is upon you to ensure data and all security configurations between JPDs are synced and up-to-date.

Docker subdomains are not supported.
</Callout>




#### [Manual Failover Routing Policy](/docs/manual-failover-setup-and-monitoring "Manual Failover Setup and Monitoring")

Use when you want to configure active-passive failover between two JPDs in different regions.

#### [Geolocation Routing Policy](/docs/geolocation-setup-and-monitoring "Geolocation Setup and Monitoring")

Use when you want to route traffic based on the location of your users (the location that DNS queries originate from). You may define 2-10 JPDs, in different regions, under one routing URL.
