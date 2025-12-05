---
title: Content Modal
excerpt: Content Modal
deprecated: false
hidden: false
icon: far fa-arrows-maximize
link:
  new_tab: false
metadata:
  robots: index
---

   
<Callout icon="📘" theme="info">
   **Note**

   It will take a few minutes for your changes to apply.
</Callout>

## DNS Routing in MyJFrog

A routing policy lets you define a single jfrog.io routing URL and to direct traffic over it to topology members based on DNS logic.

<Callout icon="📘" theme="info">
**Subscription Information**

This feature is supported on JFrog Cloud platform, with an Enterprise+ license.

Primary Admins, Admins, and technical users can create and manage the different DNS policies.
</Callout>

<Callout icon="⚠️" theme="warning">
**Warning**

This feature does not affect the synchronization between your JPDs. It is upon you to ensure data and all security configurations between JPDs are synced and up-to-date.

Docker subdomains are not supported.
</Callout>


###### Know Before You Use

* You may create up to 10 routing policies (with 10 different routing URLs) per subscription.

  You can use a routing URL once per routing policy (Manual Failover or Geolocation).
* This setup does not synchronize your JPDs. To facilitate seamless failover, both JPDs must be kept synchronized and updated by you. To achieve this, use Federated Repositories and Access Federation to sync Artifactory data. Federated Repositories do not support sync of JFrog Xray data. Refer to [Federated Repositories](/docs/630069#UUID-cb6bf9c1-c34b-c82e-8465-86836411fa01), documentation for limitations and deployment guidelines,
* You must setup all security configurations, georestrictions, allowlist, and private endpoints for each JPD.
* This solution is implemented using the AWS Route 53 service, which serves DNS requests for all supported cloud providers.
<Callout icon="📘" theme="info">
**Private Connections and Failover Policy:**

You must manually switch private endpoints to the secondary region during a failover event. If different providers are used, private endpoints will not work during a failover.
</Callout>


#### [Manual Failover Routing Policy](/docs/manual-failover-setup-and-monitoring "Manual Failover Setup and Monitoring")

Use when you want to configure active-passive failover between two JPDs in different regions.

#### [Geolocation Routing Policy](/docs/geolocation-setup-and-monitoring "Geolocation Setup and Monitoring")

Use when you want to route traffic based on the location of your users (the location that DNS queries originate from). You may define 2-10 JPDs, in different regions, under one routing URL.

* We recommend that you set up instances such as edges or JPDs in “read only” mode to ensure synchronization is consistent.
* In active/active setups, some discrepancy between JPDs may occur due to federation lag.
* Geolocation maps IP addresses to locations
In the event of requests from unidentifiable locations the response will return an unresolved response.

#### Set Up a Custom Domain Name

To use a custom domain name to point to your routing URL:

* [Set up a custom domain name](/docs/manage-domains-in-myjfrog "Manage Domains in MyJFrog").
* Set up a policy with a routing URL.
* Under your domain, in the DNS records, point your domain to the routing URL instead of the specific JPDs as specified in the last step of the custom domain name set up

### Manual Failover Setup and Monitoring

When two JPDs are configured in an Active-Passive Failover configuration, a load balancer is used to monitor traffic and switch manually from the primary JPD to the secondary JPD in the event the primary JPD is not available. The routing URL defines the URL of the load balancer.

This is a manual failover between two JFrog Cloud instances (primary and secondary) in two different regions, under one routing URL.

* In the event of the primary JPD being down for over 10 minutes, a notification will be sent, via email, to the user and traffic can be routed manually, via MyJFrog UI, from the primary to secondary JPD.
* It is possible to failover to the secondary JPD for testing purposes, via the MyJFrog UI, even when the primary JPD is healthy. In this case all traffic will be switched and routed to the secondary JPD.

Both platform and edges are supported. Deployment identity under a single routing URL must be identical (edge to edge and platform to platform).

For edge set ups, syncing only occurs from main instance to the edge through distribution, and not edge to main instance.

#### Guidelines and Known Limitations of Manual Failover

Be aware of the following limitations of manual failover.

* This setup does not synchronize your JPDs. To facilitate seamless failover, both JPDs must be kept synchronized and updated by you. To achieve this, use Federated Repositories and Access Federation to sync Artifactory data. Federated Repositories do not support sync of JFrog Xray data. Refer to [Federated Repositories](/docs/630069#UUID-cb6bf9c1-c34b-c82e-8465-86836411fa01), documentation for limitations and deployment guidelines,
* You must setup all security configurations, georestrictions, allowlist, and private endpoints for each JPD.
* Prior to performing a manual failover, all validations regarding state of synchronization and set up must be done by the user.
* Automatic failover, same region failover, self-hosted JPDs, and Docker subdomains are not supported.
* This is not a DR or Active-Active load balancing solution.