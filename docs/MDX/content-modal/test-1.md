---
title: test
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
> **PCC** - Pseudo City Code (an alphanumeric identifier for an agent's office in GDS to book and sell travel services)
>
> Hereinafter:
>
> * **PCC A**: Agent's own PCC for booking creation
> * **PCC B**: Different PCC used to obtain new prices and issue tickets

This feature allows travel agents to reprice deferred (On Hold) Sabre (1S) or Travelport (1G) bookings using private fares from a different Pseudo City Code (PCC) in the Iris Portal. When an agent creates a deferred (On Hold) booking with one PCC (**PCC A**), the **Reprice Held Booking** feature allows the agent to reprice the held booking using private fares from a different PCC (**PCC B**) and then issue the ticket. After reprice, the ticket is issued using fares from **PCC B**, but the ownership of the booking record (PNR) remains with **PCC A** that created the deferred (On Hold) booking.

Agents can use the **Reprice Held Booking** feature in the following scenarios in the Iris Portal:

* Prime Booking
* Repricing an Imported GDS PNR (Sabre (1S) or Travelport (1G))

After a deferred (On Hold) booking or a deferred imported GDS PNR is repriced using the **Reprice Held Booking** feature, the following post servicing functionality can be applied to the bookings:

* Add Ancillaries - Seats & Add-On(s)
* Add Flights
* Retain Ticket
* Reissue (only available for Sabre)
* Void Ticket Only
* Void & Cancel

> **Note:** All post-ticketing actions requiring ticket access will be processed using PCC B credentials, as the ticket was issued using PCC B fares.

***

# Prerequisites

* Ensure the **Reprice Held Booking** checkbox is checked in the **Supplier Features** section of the **Edit: Supplier [Supplier Code] page** for the Sabre (1S) or Travelport (1G) supplier integration.
* Ensure the **Reprice Held Booking** checkbox is checked in the **Feature and Permissions** section of the **Edit: POS (Point of Sale)** page of the required Point of Sale (POS).
* Ensure the **repricePCC** code is configured in the **Edit Credentials For Sabre (1S)** or **Travelport (1G)** in the **[POS Name]** page of **Manage Credentials** for the required Point of Sale (POS).
* Ensure that all bookings contain an active stored price quote (**PQ/TST**) before attempting to reprice.

***

# Considerations

* The **Reprice Held Booking** feature is currently only supported for Sabre (1S) and Travelport (1G) bookings.
* Note that screenshots in this document show Sabre (1S) examples. The process is almost identical for Travelport (1G). When configuring for Travelport, simply select "Travelport - 1G" instead of "Sabre - 1S" where indicated.

***

# Error Messages

* If no private fare is available, a "**No offers found**" error message will display.
* If no private fare is available for the RBD, a "**No fares found for RBD**" error message will display.
* If no private fare is available for the route, passenger type, and journey type, a "**No combinable fares for class used**" error message will display.
* If multiple fare preferences are selected in the **Fare Preference** option, and one of them is not available or applicable during reprice, a "**No combinable fares for class used**" error message will display.

***

### Limitations

**Travelport (1G) Specific:**

<Callout icon="⚠️" theme="warn">
  * Ticket **Exchange** (Reshop) is not implemented for Travelport (1G) in Production, and is therefore not available as a post-ticketing services for the **Reprice a Held Booking** feature.
  * Due to Travelport (1G) system limitations, it is not possible to reprice a booking after performing a **Void Ticket Only** action (when an agent has voided only the ticket and the booking is placed back on hold).
</Callout>

***

# Enable the Reprice Held Booking Feature

Before using the **Reprice Held Booking** feature, it must be enabled in three places:

1. **Supplier**
2. **Point of Sale (POS)**
3. **Manage Credentials**

> **Note**: Only administrator agents can enable the **Reprice Held Booking** feature at the **Supplier** and **Point of Sale (POS)** levels.

### 1. Enable the Reprice Held Booking Feature for the Supplier Integration

* Log in to the Iris Portal.
* On the **Portal** page, click the Platform menu button.
* Click **Distribution / suppliers** in the DMT section.
* Search for the Sabre (1S) or Travelport (1G) supplier integration using the **Search** field.
* Click the **Edit** icon in the **Action** column to edit the supplier integration.
* Check the **Reprice Held Booking** checkbox in the **Supplier Features** section, and click **Update**.

  <Image align="left" border={true} src="https://files.readme.io/75eab1ac1f592f7a1a738c541df80a99b5972101e1d2f26a3105cdc62b5002ae-reprice_held_booking_flag_3.png" className="border" />
* The **Reprice Held Booking** feature is enabled for the selected supplier integration.

### 2. Enable the Reprice Held Booking Feature for a Point of Sale (POS)

* On the **Portal** page, click the Platform menu button.
* Click List Point of Sale in the **POINT OF SALE** section.
* Select the required organisation from the **Organisation** drop-down and enter the office name or office ID in the **Office Name/ID** field. Then, click **Search**.
* Select the returned POS from the search results, and click the **Edit** icon in the **Action** column to edit the POS.
* Check the **Reprice Held Booking** checkbox in the **Features and Permissions** section, and click **Update**.

  <Image align="left" src="https://files.readme.io/04d559192898694d9552080b00df9d19021c6d9b3ffedeee38340acd51aaf329-reprice_held_booking_flag_3.png" />
* The **Reprice Held Booking** feature is enabled for the required POS.

### 3. Configure the RepricePCC for a Point of Sale (POS) in Manage Credentials

Configuration fields vary by supplier.

### For Sabre (1S) and Travelport (1G):

* Log in to the Iris Portal.
* On the **Portal** page, click the **Platform** menu button.
* Click **Manage Credentials** in the **DMT** section.
* Select **Sabre - 1S** or **Travelport - 1G** from the **Select Supplier** drop-down list.
* Select the required **POS** from the **Select POS** drop-down list.
* Click the **Edit** icon in the **Action** column to edit the required POS.
* Add your PCC code to the **RepricePCC** field, enter the username and password for the target PCC credentials, and click **Update**.

<Image align="center" border={true} src="https://files.readme.io/095e3878cc74ae01eb3afb49964844a79c04f9bdd6f8bed0f02a8f16ac5c32ac-Reprice1A.png" className="border" />

<Callout theme="default">
  **Note:** Travelport (1G) uses the term 'TargetBranch' as an identifier connected to PCC (used in their API). In the Iris Portal, this is configured through the **RepricePCCDetails** field in **Manage Credentials**.
</Callout>

### Field Explanations for RepricePCCDetails for Sabre (1S) and Travelport (1G)

| Field                                       | Required                                                                                                     |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| **TargetBranch (only for Travelport (1G))** | Enter your PCC code                                                                                          |
| **RepricePCCPassword**                      | Enter the password for the target PCC                                                                        |
| **RepricePCCUsername**                      | For Sabre (1S): Standard username format<br />For Travelport (1G): Format is Universal API/uAPI[credentials] |

* The **RepricePCC** credentials are now configured for the required POS.

### For Amadeus (1A)

<Callout theme="default">
  **Note:** Amadeus uses OID (Office ID) rather than PCC as the primary identifier. In this document, both terms are used interchangeably (PCC = OID).
</Callout>

* Log in to the Iris Portal.
* On the **Portal** page, click the **Platform** menu button.
* Click **Manage Credentials** in the **DMT** section.
* Select **Amadeus - 1A** from the **Select Supplier** drop-down list.
* Select the required **POS** from the drop-down list.
* Click the **Edit** icon in the **Action** column to edit the required POS.
* In the **RepricePCCDetails** field, configure the **target** PCC/OID credentials: **OfficeID**, **WSAPuserID**, **userID**, **Password**.

<Image align="center" src="https://files.readme.io/ddc0d8e8c537d489521c6ca0342764fa455e329b3572da74c55c0be6f9995050-Reprice1A001.png" />

### Field Explanations for RepricePCCDetails for Amadeus (1A)

| Field      | Description                                                             |
| ---------- | ----------------------------------------------------------------------- |
| `OfficeID` | Enter the Office ID (OID) for the target PCC (PCC B) used for repricing |
| `WSAP`     | Enter the Web Service Access Point identifier                           |
| `userID`   | Enter the user ID for the target PCC credentials                        |
| `Password` | Enter the password for the target PCC credentials                       |

> **Important:** Ensure the credentials provided correspond to PCC B (the target PCC used for repricing with private fares).

* Click **Update**.
* The **RepricePCC** credentials are now configured for the required POS.

***

# Use the Reprice Held Booking Feature

## Prime Booking Scenario

Follow the steps below to use the **Reprice Held Booking** feature in a Prime Booking scenario in the Iris Portal:

> **Note**: In this example, a deferred (On Hold) Sabre (1S) round-trip booking, which contains published fares, is used. The workflow is identical for Travelport (1G) bookings.

* Log in to the Iris Portal.
* Open the **Order Management** page.
* Search for and open a deferred (On Hold) round-trip booking which contains published fares.
* Click **Reprice Held Booking**.

  <Image align="center" width="150px" src="https://files.readme.io/ca580106a65c2017957d0065f5479aa80d595cef2bc6b2b2e4c6d9583c4dd335-reprice_held_booking_04.png" />
* Click **Change** for the required segment on the **Your Previous Booking Details** page.

<Image align="left" src="https://files.readme.io/a0455c1f5dc7fcfb817380636e48affa309f7fb22659d1c0621d98c2f62f073e-reprice_held_booking_05.png" />

<Callout theme="default">
  **Note**: When a deferred (On Hold) round-trip booking is selected for reprice, and the **Change** button is clicked for one of the segments, then the second segment is automatically selected based on the original fare quote. You cannot reprice only one segment in a round-trip booking.
</Callout>

<Image align="left" src="https://files.readme.io/83421930b229b36296353b1c362e48a2b4e21e4a6d1cf25d3b6615d20ce8301c-reprice_held_booking_06.png" />

* The **Reprice Criteria** page displays.

> **Note**: The **Flight Information**, such as the **Departure Airport**, **Arrival Airport**, **Date**, and **Cabin** of the booking, cannot be edited on the **Reprice Criteria** page.

<Image align="center" src="https://files.readme.io/3759b13175fd9cc9cd3bc7290387d48517eb885c46a1bf052e635a3d1c576056-reprice_held_booking_07.png" />

* Select the required **Fare Preference** and or **Type** options from the **Fare Preference** and **Type** drop-down lists. The following options are available:
* **Fare Preference**:
  * Published Only
  * Private Only
  * Type:
    * Tour Code
    * Corporate Code
    * Retailer Code
* In this example, the **Private Fare** option is selected from the **Fare Preference** drop-down list. Click **PROCEED TO REPRICE**.

<Image align="center" src="https://files.readme.io/cec47ada3e1b9ac1a245c2cd396abd9b302711de73e4dfe896993e7371a4ffe0-reprice_held_booking_08.png" />

* The **REPRICE** page displays the originally selected fare and all available **Private Fare** options for each segment, based on the specified Reservation Booking Designator (RBD) in the original booking.

<Image align="left" src="https://files.readme.io/9faf4853f7463c5eaaaac6049e19705ce96ff84b00404157e9fcb091fcf22305-reprice_held_booking_09.png" />

* In this example, a cheaper **Private Fare** is selected for both segments. The **Original Selection** and **Selected fares** are highlighted on the **REPRICE** page.

<Image align="center" src="https://files.readme.io/2cb3250a58b9f74d722c79d89ffe9b944cd7815919397b20d92e802aba78a12e-reprice_held_booking_10.png" />

<Image align="center" caption="Inbound Segment" src="https://files.readme.io/ca45852be54d6aa263d7a7ccd228bb25d3598c0d02bc76b42caf70ccd734a9b5-reprice_held_booking_11.png" />

* Once the new and cheaper **Private Fares** are selected per segment, the **Booking Summary** page displays.

<Image align="center" src="https://files.readme.io/dc84fa39db003a0d6af6dad299bf0c0b29fda327da04015a6dabd566792d64da-reprice_held_booking_12.png" />

* The **Booking Summary** page displays the following information:
  * The **BASE FARE** difference between the **ORIGINAL SELECTION** (Published Fares) and the chosen **CURRENT SELECTION** (Private Fares)
  * The **FEES & TAXES** difference between the **ORIGINAL SELECTION** (Published Fares) and the chosen **CURRENT SELECTION** (Private Fares). Click **FEES & TAXES** to display all the applicable fees and taxes.
  * The **GRAND TOTAL** difference between the **ORIGINAL SELECTION** (Published Fares) and the chosen **CURRENT SELECTION** (Private Fares)
  * The **PAX TYPE**, the **Commission (Not included in Base Fare)** percentage the agent will receive, and the **Grand Total** amount.
* For this example, the **ISSUE TICKET** option is used. Click **ISSUE TICKET**.

  <Image align="center" width="150px" src="https://files.readme.io/079bced4ecffa844f926af5c048a362fe4a2d604d97a987754f560a733a40547-reprice_held_booking_13.png" />
* Select a payment option from the **Choose Payment Type** drop-down list.
* Click **PROCEED TO PAY**.

  <Image align="center" width="300px" src="https://files.readme.io/9a01c97d880f0ed4e1f3ebfb0260b8d74e4a620ae8d127cfab273e8e95f3e11c-reprice_held_booking_14.png" />
* The booking is successfully repriced and issued with the newly selected, cheaper private fares in the Iris Portal.

## Import PNR Scenario

Follow the steps below to use the **Reprice Held Booking** feature in an Import PNR scenario in the Iris Portal:

* Log in to the Iris Portal.
* Open the **Order Management** page.
* Click **Import PNR**.
* Enter the **Airline/Agency Locator** code, select the **Provider** from the drop-down list, and specify the Point of Sale (POS) (**Country**, **Brand**, **Team**) under which the GDS PNR will be imported. Click **Import**.

  <Image align="center" width="600px" src="https://files.readme.io/428022e7955c201bea173fd761fe252f5aaa8de83738b0886bec105a8640c7f2-reprice_held_booking_15.png" />
* The GDS PNR is imported successfully into the Iris Portal, and the **Order Details** page of the imported PNR displays.
* Click **Reprice Held Booking**.

  <Image align="center" width="150px" src="https://files.readme.io/7b5d7eb06de71cc7b9f183200c1df1c50be68d88faa19f7280ae4209ad47b908-reprice_held_booking_16.png" />
* Click **Change** for the required segment on the **Your Previous Booking Details** page.

<Image align="center" src="https://files.readme.io/fa9e1a8fb4204d08f1be509cbba8b28fc2cf0f3ba46104b366cc908b74577a82-reprice_held_booking_17.png" />

> **Note**: When an imported and deferred (On Hold) round-trip booking is selected for reprice, and the **Change** button is clicked for one of the segments, the second segment is automatically selected based on the original fare quote. You cannot reprice only one segment in a round-trip booking.

<Image align="center" width="800px" src="https://files.readme.io/6d8dfb8fbe18410c8e090b929cc2ca629833f2a379a7398f1d75cc251a2d4201-reprice_held_booking_18.webp" />

* The **Reprice Criteria** page displays.

> **Note**: The **Flight Information**, such as the **Departure Airport**, **Arrival Airport**, **Date**, and **Cabin** of the booking, cannot be edited on the **Reprice Criteria** page.

* Select the required **Fare Preference** and or **Type** options from the **Fare Preference** and **Type** drop-down lists. The following options are available:
  * **Fare Preference**:
    * Published Only
    * Private Only
  * Type:
    * Tour Code
    * Corporate Code
    * Retailer Code
* In this example, the **Private Only** option is selected from the **Fare Preference** drop-down list. Click **PROCEED TO REPRICE**.

<Image align="center" width="800px" src="https://files.readme.io/ab8263d978618b5bbfe3af0dbd1b0c0dbd6983c57da6119593fb4c7374cf8ed7-reprice_held_booking_20.png" />

* The **REPRICE** page displays the originally selected fare and all available **Private Fare** options for each segment, based on the specified Reservation Booking Designator (RBD) in the original booking.
* In this example, a cheaper **Private Fare** is selected for both segments. The **Original Selection** and **Selected fares** are highlighted on the **REPRICE** page.

<Image align="center" caption="Outbound Segment" src="https://files.readme.io/2aea1992820fb592309ab54bae6facfd3251f06b4931d21dc734e49d0250cf26-reprice_held_booking_22.png" width="800px" />

<Image align="center" caption="Inbound Segment" src="https://files.readme.io/35b9ba80336c2173f4de73ca6d4ad6eedac6893e32fa5c202a26d51cb4042de0-reprice_held_booking_23.png" width="800px" />

* Once the new and cheaper **Private Fares** are selected per segment, the **Booking Summary** page displays.

  <Image align="center" width="800px" src="https://files.readme.io/12d6a2673876bcb3b44888950c28b548cc0a2640daff377cba727567f6654a18-reprice_held_booking_24.png" />

<br />

* The **Booking Summary** page displays the following information:
  * The **BASE FARE** difference between the **ORIGINAL SELECTION** (Published Fares) and the chosen **CURRENT SELECTION** (Private Fares)
  * The **FEES & TAXES** difference between the **ORIGINAL SELECTION** (Published Fares) and the chosen **CURRENT SELECTION** (Private Fares). Click **FEES & TAXES** to display all the applicable fees and taxes.
  * The **GRAND TOTAL** difference between the **ORIGINAL SELECTION** (Published Fares) and the chosen **CURRENT SELECTION** (Private Fares)
  * The **PAX TYPE**, the applied **Commission (Not included in Base Fare)**, and the **Grand Total** amount, which contains the commission percentage/amount.
* For this example, the **ISSUE TICKET** option is used. Click **ISSUE TICKET**.

  <Image align="center" width="150px" src="https://files.readme.io/933017d91b9fd626e15d6f47bdeab44afdef0cd04a6c369df4c0006962673e76-reprice_held_booking_25.png" />
* Select a payment option from the **Choose Payment Type** drop-down list.
* Click **PROCEED TO PAY**.

  <Image align="center" width="350px" src="https://files.readme.io/596d3c61ceed4af022b00550c331e569e321de9326b01e4d92fffdf3ca712198-reprice_held_booking_26.png" />
* The imported GDS PNR is successfully repriced and issued with the newly selected and cheaper private fares in the Iris Portal.
