---
title: Error Test
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
## Authentication

All requests to the MortgageAPI must be authenticated with a valid Oauth API token. To obtain an API token, please review the OAuth Connection recipe:

<TutorialTile backgroundColor="#018FF4" emoji="￼" id="65a7ed0f014c8b003fc2f2b4" link="https://docs.mortgageapi.rocket.mortgage/v1/recipes/oauth-connection" slug="oauth-connection" title="OAuth Connection" />

## Retrieving Products and Pricing Options

To retrieve Rocket Pro mortgage products and pricing options, make a POST request to <Anchor label="/products/pricing-scenarios" target="_blank" href="https://developers.mortgageapi.rocket.mortgage/reference/calculatepricingscenarios#/">/products/pricing-scenarios</Anchor>.

The API spec denotes what is required to return a pricing scenario, when an optional value is not passed, a default value is set, those default values can be found in the field description of the API spec.

<br />

### Example Request:

```json
{
"propertyDetails": {
"value": 250000,
"address": {
"zipCode": "48071"
},
"units": "One",
"isNewConstruction": false
},
"borrowerDetails": {
"creditScore": 750,
"income": {
"monthly": 7800
},
"debt": {
"monthly": 1250
},
"isVeteran": false,
"housing": {
"isPresentResidenceRented": false
}
},
"loanDetails": {
"purpose": "RefinanceRateAndTerm",
"amount": 175000,
"settings": {
"channel": "Wholesale"
},
"compensation": {
"type": "ClientPaid",
"originationFlatFee": 1000,
"originationPercentage": 1
},
"pmiPreference": "ClientPaid"
}
}
```