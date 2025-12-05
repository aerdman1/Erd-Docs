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
**Private Connections and Failover Policy:**

You must manually switch private endpoints to the secondary region during a failover event. If different providers are used, private endpoints will not work during a failover.
</Callout>

#### Create a New Manual Failover Policy

1. In MyJFrog, go to **Settings** | **DNS routing** |**Manual Failover**, and accept the terms and conditions.

   ![Manual_Failover.png](../../../../image/uuid-f419997c-73af-6d3b-7db8-f11631f61243.png)
2. Enter a routing URL, which is the URL of the load balancer.

   ![add-manual-failover-policy.png](../../../../image/uuid-320656ea-7071-33bc-e96a-8ff42bb02667.png)
3. Set up your topology.

   * Select a primary JPD.

     This JPD will be the active JPD. By default, all traffic under the routing URL will be routed to this JPD. The primary JPD is monitored and in the event of it being down for more than 10 minutes an email will be sent out.
   * Select a secondary JPD.

     This JPD will be passive.
4. Click **Save** to create the manual failover policy.

   The new policy is added in the `processing` status till the DNS is added and successfully configured. This might take a few minutes.

#### Monitor an Existing Manual Failover Policy

Once a new policy is added you can see in the table view the routing status changing from `Processing` to `OK`, which means the defined routing URL is set and routing traffic to the defined active JPD.

![DNSRoutingSettings.png](../../../../image/uuid-e33d05a5-7fa2-716d-9148-01b9c252dd31.png)

The JPD status provides real time status checking the readiness of Artifactory.

Although the UI shows the real time status, the monitoring over the JPD sends an email notification after 10 minutes of the primary JPD being down or after 10 minutes of it being up again.

In the event of the primary JPD being down the JPD status will change to `Failed` and the routing status will change to `error`.

The secondary JPD, being up and ready will be in the passive status - and the **Switch** button is available to click and approve the rerouting of the traffic to the secondary JPD.

![status.png](../../../../image/uuid-da73c2dc-1f61-efc2-03df-884256e02141.png)

In the event that traffic is routed to the primary JPD and the secondary JPD fails for some reason, the routing status will remain `OK` as traffic is routed to the primary JPD and served. The Secondary JPD status will be `Failed` and the **Switch** button will be disabled.

![status2.png](../../../../image/uuid-2c40aff5-4c53-d159-c3f8-58d13126e534.png)

#### Actions on a Manual Failover Policy

You can take the following actions on a manual failover policy.

##### Manual Switch

You may decide to switch your routing to your secondary JPD for testing purposes, when both JPDs are up or in the event of your primary JPD being down.

In both cases you need to verify that all configurations and data is synced to meet your expectations prior to performing the switch. This is especially important when switching back, after an event, from the secondary to the primary.

1. In MyJFrog, go to **Settings** | **DNS routing** |**Manual Failover**.

   ![ManualFailover.png](../../../../image/uuid-b0ad0f94-b506-181a-be44-9be253823e8f.png)
2. A pop-up specifies the change you are about to perform. Select the checkbox to acknowledge the routing change.

   ![ManualSwitch.png](../../../../image/uuid-02e3ddfa-beb6-c3c7-bc32-adac49e16be5.png)
3. Once the switch is performed you will see the secondary JPD status change to “active” and the routing status change to “OK”. In the event of the primary JPD being down you will not be able to switch back till the primary JPD is up again. If a client is using a VPC caching may prevent the DNS from refreshing.

   ![AfterSwitch.png](../../../../image/uuid-aa48cb46-01ca-cf2b-ead5-7e8135eec80c.png) 
<Callout icon="❗️" theme="error">
   **Important**

   In the event of performing a switch for testing reasons it is recommended to keep the test enabled only as long as is necessary to verify the results. Once done you must manually switch back again.
</Callout>

![AfterSwtich2.png](../../../../image/uuid-03f50e6a-d912-4025-0224-29bb4f7fa3d8.png)

##### Edit Manual Failover Policy

You may edit your Primary and Secondary JPDs but not the routing URL.

In the event you wish to change the routing URL you may create another Failover policy with a new routing URL over the same two JPDs.

1. In MyJFrog, go to **Settings** | **DNS routing** |**Manual Failover**.
2. Hover over the three-dots menu and select **Edit**.
3. Update the topology.
4. Click **Save**.

##### Deactivate Manual Failover Policy

You can deactivate a manual failover policy so that it is paused. You can reactivate the policy again at any time.

1. In MyJFrog, go to **Settings** | **DNS routing** |**Manual Failover**.
2. Hover over the three-dots menu and select **Deactivate**.

   ![deactivate.png](../../../../image/uuid-df7aafd8-4275-e5b5-3dcb-bb0be38f8da7.png)
3. Click **Confirm**.

The following image shows deactivated policy.

![deactivated.png](../../../../image/uuid-9c360b34-63f9-f4d9-c75b-73ed86321d63.png)

##### Reactivate Manual Failover Policy

You can reactivate a paused manual failover policy.

1. In MyJFrog, go to **Settings** | **DNS routing** |**Manual Failover**.
2. Hover over the three-dots menu and select **Reactivate**.

   ![reactivate.png](../../../../image/uuid-b6945dc9-bcff-a597-da07-378214da578d.png)
3. Click **Confirm**.

##### Delete Manual Failover Policy

You can delete a manual failover policy. Once you delete, the policy is removed from your subscription.

1. In MyJFrog, go to **Settings** | **DNS routing** |**Manual Failover**.
2. Hover over the three-dots menu and select **Delete**.

   ![delete.png](../../../../image/uuid-bb0d1800-8a62-a358-8c67-310c54711e4a.png)
3. Click **Confirm**.

### Geolocation Setup and Monitoring

Geolocation routing lets you choose the resources that serve your traffic based on the geographic location of your users, meaning the location from which the DNS queries originate.

You can predefine your traffic load across endpoints in a predictable, easy-to-manage way, so that each user location is consistently routed to the same endpoint. You can specify geographic locations by continent, by country, or by state in the United States.

You may define between 2-10 JPDs, in different regions.

#### Guidelines and Known Limitations of Geolocation

Be aware of the following limitations of geolocation.

* This setup does not synchronize your JPDs. To facilitate seamless failover, both JPDs must be kept synchronized and updated by you. To achieve this, use Federated Repositories and Access Federation to sync Artifactory data. Federated Repositories do not support sync of JFrog Xray data. Refer to [Federated Repositories](/docs/630069#UUID-cb6bf9c1-c34b-c82e-8465-86836411fa01), documentation for limitations and deployment guidelines,

  In active/active setups, some discrepancy between JPDs may occur due to federation lag. Therefore, we recommend that you use this for “read only” or on edge instances only.
* Edge: For edge setups, syncing only occurs from the main instance to the edge, and not from edge to the main instance. For more information, see [JFrog Distribution](/docs/360460#UUID-e194ab38-beae-8bd9-35b3-a8179347aa5b).
* You may not define overlapping geographic locations. Geolocation maps IP addresses to locations. In the event of requests from unidentifiable locations the response will return an unresolved response.

  For a list of countries on each continent, refer <Anchor label="here" href="https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2" target="_blank">here</Anchor>.

  In the event that a location has been blocked via geolocation restrictions it will also be blocked in the selection list.
* Private Endpoint: You can use a geolocation routing policy for records in private hosted zones. Select the continent, country, or sub-division closest to the region of your resource.

#### Create a New Geolocation Policy

1. In MyJFrog, go to **Settings** | **DNS routing** | **Geolocation**.

   Read and accept the prerequisite and guidelines.

   ![add-geo-location-policy.png](../../../../image/uuid-9833ce93-1393-5c6b-977a-436a399dfbe0.png)
2. Enter a routing URL, which is the URL of the load balancer.
3. Define source regions for multiple JPDs.

   
<Callout icon="📘" theme="info">
   **Note**

   You can define a minimum of two and maximum of 10 JPDs in different regions.

   You may define multiple source regions for a JPD. Each source region is unique for a JPD. There can not be multiple JPDs that have the same or overlapping source regions.

   For example, if source region USA is defined to JPD A, you cannot define Virginia to JPD B as it is overlapping. But, you can define three states in USA to three different JPDs as long as you do not define USA as a source to any instance under the policy.
</Callout>

4. Click **Save** to save the policy.

#### Monitor an Existing Geolocation Policy

The status is reflected in the table view in the portal. Once a new policy is added you can see in the table view the routing status changing from `Processing` to `OK`, which means the defined routing URL is set and routing traffic based on the defined source regions to each active JPD.

![CreateGeolocation2.png](../../../../image/uuid-0e9a5dc8-cee3-5fcf-e9d2-5b5c86a0d288.png)

In the event of one of the JPDs being down, traffic routed from the defined source regions will be unresolved and so the routing status will change to `ERROR` although the other JPDs under the policy might be fine and traffic will continue to be routed to them.

#### Actions on a Geolocation Policy

You can take the following actions on a geolocation policy.

##### Edit Geolocation Policy

You can edit your source regions and the defined JPDs but not the routing URL.

In the event you wish to change the routing URL you may create another geolocation policy with a new routing URL over the same JPDs.

1. In MyJFrog, go to **Settings** | **DNS routing** |**Geolocation**.
2. Hover over the three-dots menu and select **Edit**.
3. Update the topology.
4. Click **Save**.

##### Deactivate Geolocation Policy

You can deactivate a geolocation policy so that it is paused. You can reactivate the policy again at any time.

1. In MyJFrog, go to **Settings** | **DNS routing** |**Geolocation**.
2. Hover over the three-dots menu and select **Deactivate**.

   ![deactivate.png](../../../../image/uuid-df7aafd8-4275-e5b5-3dcb-bb0be38f8da7.png)
3. Click **Confirm**.

##### Reactivate Geolocation Policy

1. In MyJFrog, go to **Settings** | **DNS routing** |**Geolocation**.
2. Hover over the three-dots menu and select **Reactivate**.

   ![reactivate.png](../../../../image/uuid-b6945dc9-bcff-a597-da07-378214da578d.png)
3. Click **Confirm**.

##### Delete Geolocation Policy

You can delete a geolocation policy. Once you delete, the policy is removed from your subscription.

1. In MyJFrog, go to **Settings** | **DNS routing** |**Geolocation**.
2. Hover over the three-dots menu and select **Delete**.

   ![delete.png](../../../../image/uuid-bb0d1800-8a62-a358-8c67-310c54711e4a.png)
3. Click **Confirm**.