---
title: Data Meter
deprecated: false
hidden: false
metadata:
  robots: index
---
# 1. Pull Top Page Searches (API Key Required)

<DataMeter max={100} labelPosition="overlay" showCards={true} />

# 2. Pull from OAS file

<DataMeter websiteBaseUrl="https://erdtest123.readme.io" specFile="ErdSpec1.json" apiGroup="pet" max={100} labelPosition="overlay" showCards={true} />

# 3. Manual entry (Public)

<DataMeter
  values={[
    {
      label: "Written",
      cardLabel: "Docs Written",
      value: 40,
      meterBackgroundColor: "#4285F4",
      cardBackgroundColor: "#D2E3FC",
      textColor: "#fff",
      cardTextColor: "#174EA6",
      icon: "fas fa-pen-nib",
    },
    {
      label: "Reviewed",
      cardLabel: "Peer Reviewed",
      value: 25,
      meterBackgroundColor: "#34A853",
      cardBackgroundColor: "#DFF6DD",
      textColor: "#fff",
      cardTextColor: "#0D652D",
      icon: "fas fa-user-check",
    },
    {
      label: "Updated",
      cardLabel: "Recently Updated",
      value: 20,
      meterBackgroundColor: "#FBBC05",
      cardBackgroundColor: "#FEF7E0",
      textColor: "#fff",
      cardTextColor: "#B06000",
      icon: "fas fa-sync-alt",
    },
    {
      label: "Missing",
      cardLabel: "Docs Still Missing",
      value: 15,
      meterBackgroundColor: "#EA4335",
      cardBackgroundColor: "#FCE8E6",
      textColor: "#fff",
      cardTextColor: "#A50E0E",
      icon: "fas fa-exclamation-triangle",
    },
  ]}
  max={100}
  labelPosition="overlay"
  showCards={true}
/>