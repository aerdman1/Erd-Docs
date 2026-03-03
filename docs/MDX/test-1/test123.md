---
title: test123
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
<br />

<HTMLBlock>{`
<h3>Example Request</h3><hr>
`}</HTMLBlock>

```curl
curl 'https://api.impact.com/Mediapartners/<AccountSID>/Contracts/<Id>' \
  -X GET \
  -u '<AccountSID>:<AuthToken>' \
  -H 'Accept: application/json'
```
```curl cURL versioned
curl 'https://api.impact.com/Mediapartners/<AccountSID>/Contracts/<Id>?IRVersion=15' \
  -X GET \
  -u '<AccountSID>:<AuthToken>' \
  -H 'Accept: application/json'
```

<HTMLBlock>{`
<h3>Example Response</h3><hr>
`}</HTMLBlock>

```json
{
  "Id": "S-1234567",
  "CampaignId": "8882",
  "Status": "ACTIVE",
  "StartDate": "2021-03-04T16:42:58-05:00",
  "EndDate": "",
  "BrandSignatory": "ACME Inc",
  "BrandSignatoryDate": "2021-03-04T16:37:01-05:00",
  "PartnerSignatory": "Noah Lott",
  "PartnerSignatoryDate": "2021-03-04T16:42:58-05:00",
  "DateCreated": "2021-03-04T16:42:58-05:00",
  "DateLastUpdated": "2021-03-04T16:42:58-05:00",
  "Terms": {
    "Currency": "USD",
    "EventPayouts": [
      {
        "EventTypeId": "16027",
        "EventTypeName": "Sale",
        "EventCategory": "SALE",
        "DefaultPayoutRate": "0",
        "PayoutLevel": "ITEM",
        "PayoutGroups": [
          {
            "Id": "66bb9761-2760-4c7f-afb9-1ff70c9c8850",
            "Rank": "1",
            "Rules": [
              {
                "Variable": "CUSTOMER_CITY",
                "Operator": "IS",
                "Values": [
                  "Santa Barbara"
                ]
              }
            ],
            "PayoutRate": "1"
          }
        ],
        "PayoutAdjustments": [
          {
            "Id": "dd926935-2762-426a-910a-a3aabdc57ee4",
            "Rules": [
              {
                "Variable": "DERIVED_BROWSER",
                "Operator": "IS",
                "Values": [
                  "FIREFOX"
                ]
              }
            ],
            "Direction": "INCREASE",
            "Rate": "1"
          }
        ],
        "PerformanceBonus": {
          "Type": "SUBSEQUENT_ACTIONS",
          "Basis": "ACTIONS",
          "Period": "CALENDAR_MONTH",
          "Tiers": [
            {
              "ActionThreshold": "2147483647",
              "PayoutRate": "0"
            }
          ]
        },
        "PayoutRestrictions": [
          {
            "Id": "08707ac6-ae02-4da2-b009-a0ebf3a38db6",
            "Rules": [
              {
                "Variable": "CUSTOMER_CITY",
                "Operator": "IS",
                "Values": [
                  "Los Angeles"
                ]
              }
            ],
            "ZeroPayoutHideReport": "0"
          }
        ],
        "Limits": [
          {
            "Type": "ACTION",
            "SubType": "SKU",
            "Value": "250.0",
            "LimitBy": "CUSTOMER",
            "Period": "DAY",
            "WeekendOverrideValue": "500"
          }
        ],
        "Locking": {
          "Basis": "TRACKED",
          "Period": "DAY",
          "DayOffset": "30"
        },
        "PayoutScheduling": {
          "Basis": "LOCKED",
          "Period": "END_OF_DAY",
          "DayOffset": "3"
        },
        "CreditPolicy": "LAST_REFERRER",
        "ValidReferrals": [
          {
            "Type": "CLICKS",
            "Window": "30",
            "WindowUnit": "DAY"
          }
        ]
      }
    ],
    "SpecialTermsList": [
      {
        "TermsName": "Special Terms",
        "TermsType": "CUSTOM",
        "TermsPdfUri": "/Mediapartners/<AccountSID>/Campaigns/8882/CustomTerms/10500/Download"
      }
    ],
    "ChangeNotificationPeriod": "0",
    "ReturnPolicy": "ALWAYS_OK",
    "MaxReturnPercentage": "100",
    "ActionLimit": "1000",
    "ActionLimitPeriod": "MONTH",
    "CustomCreativePayer": "ADVERTISER"
  },
  "CampaignTerms": [
    {
      "Name": "Product Boost Campaign 1",
      "Id": "1234",
      "StartDate": "2025-03-28T00:00:00-07:00",
      "EndDate": "2025-03-29T00:00:00-07:00",
      "EventPayouts": [
        {
          "EventTypeId": "13416",
          "DefaultPayout": "10.00",
          "PayoutLevel": "ORDER",
          "PayoutGroups": [
            {
              "Id": "390c0f5a-5d0b-4626-b079-ddbcccb6e3fb",
              "Rank": "1",
              "Rules": [
                {
                  "Variable": "ITEM_SKU",
                  "Operator": "IS",
                  "Values": [
                    "sku1"
                  ]
                }
              ],
              "PayoutRate": "1"
            },
            {
              "Id": "d54965b8-8cc7-4dab-8672-375f945b3a4a",
              "Rank": "2",
              "Rules": [
                {
                  "Variable": "ITEM_SKU_LIST",
                  "Operator": "IS",
                  "Values": [
                    "11356"
                  ]
                }
              ],
              "Payout": "1.00"
            }
          ]
        }
      ]
    }
  ],
  "PdfUri": "/Mediapartners/<AccountSID>/Campaigns/8882/Contracts/S-9558520/Download",
  "Uri": "/Mediapartners/<AccountSID>/Contracts/S-9558520"
}

```
