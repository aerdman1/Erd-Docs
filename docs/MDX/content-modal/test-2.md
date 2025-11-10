---
title: test
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
```javascript
const checkoutResponse = await paze.checkout({
  // Identity & session
  emailAddress: "USER_EMAIL@example.com", // Preferred: Required if lookup by Email (email OR phone)
  mobileNumber: "USER_MOBILE_NUMBER", // Conditional: Required if lookup by Phone (email OR phone)
  sessionId: "YOUR_SESSION_ID", // Recommended: same value per session that is used to link the transaction in your system

  // Flow control (this is for modifying how the Paze™ Experience works)
  actionCode: "START_FLOW", // Optional: START_FLOW (default and option required for Auto Initiate Flow)
  intent: "REVIEW_AND_PAY", // Optional: REVIEW_AND_PAY (default and option required for Auto Initiate Flow)

  // Amount to display
  transactionValue: {
    // Recommended: as it renders subtotal in Paze™ Experience
    transactionCurrencyCode: "USD", // Conditional with transactionValue
    transactionAmount: "149.99", // Conditional with transactionValue
  },

  // Address & card controls
  shippingPreference: "ALL", // Optional: ALL (default) | NONE
  billingPreference: "ALL", // Optional: ALL (default)
  acceptedShippingCountries: ["US", "CA"], // Optional: string[]
  acceptedPaymentCardNetworks: [], // Optional: string[]; empty[] for all available networks, but can specify VISA, MASTERCARD, DISCOVER to restrict
});

// checkoutResponse → { result: "COMPLETE" | "INCOMPLETE", checkoutResponse?: "<JWS>" }
```

<br />
