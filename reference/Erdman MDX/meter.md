---
title: Meter
deprecated: false
hidden: false
metadata:
  robots: index
---
# 1) Pull from your Metrics API (requires metricsApiKey):

<ProgressMeter metricsApiKey="rdme_xn8s9h4bc406cec07bd081cc3351813607c7e5f8686ceeaf5b4fb9f1f8bf8e9bcf82a0" max={100} labelPosition="overlay" showCards={true} />

# 2) Pull from OAS file:

<ProgressMeter websiteBaseUrl="https://erdtest123.readme.io" specFile="ErdSpec1.json" apiGroup="pet" max={100} labelPosition="overlay" showCards={true} />

# 3) Manual entry:

<ProgressMeter
  values={[
    {
      label: "Written",
      cardLabel: "Docs Written",
      value: 40,
      meterBackgroundColor: "#4285F4",
      cardBackgroundColor: "#D2E3FC",
      textColor: "#fff",
      cardTextColor: "#174EA6",
      icon: "fas fa-pen-nib"
    },
    {
      label: "Reviewed",
      cardLabel: "Peer Reviewed",
      value: 25,
      meterBackgroundColor: "#34A853",
      cardBackgroundColor: "#DFF6DD",
      textColor: "#fff",
      cardTextColor: "#0D652D",
      icon: "fas fa-user-check"
    },
    {
      label: "Updated",
      cardLabel: "Recently Updated",
      value: 20,
      meterBackgroundColor: "#FBBC05",
      cardBackgroundColor: "#FEF7E0",
      textColor: "#fff",
      cardTextColor: "#B06000",
      icon: "fas fa-sync-alt"
    },
    {
      label: "Missing",
      cardLabel: "Docs Still Missing",
      value: 15,
      meterBackgroundColor: "#EA4335",
      cardBackgroundColor: "#FCE8E6",
      textColor: "#fff",
      cardTextColor: "#A50E0E",
      icon: "fas fa-exclamation-triangle"
    }
  ]}
  max={100}
  labelPosition="overlay"
  showCards={true}
/>