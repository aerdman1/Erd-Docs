---
title: Error Test
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
Once the broker has a mortgage product and pricing option in mind, detailed fees can be returned for that specific product by making a request to POST to [`/products/pricing-scenarios/{scenario-id}/fees`](https://developers.mortgageapi.rocket.mortgage/reference/get-pricing-scenario-fees#/products/pricing-scenarios/\{scenario-id}/fees). The `scenario-id` is returned in the response from [`/products/pricing-scenarios`](https://developers.mortgageapi.rocket.mortgage/reference/calculatepricingscenarios#/), and is used to run fees on the specific transaction.
