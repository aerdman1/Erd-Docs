---
title: Error Test
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
```json
{
"scenarioId": "02ba5496-9719-4ccc-9822-b60e0160cc87",
"products": [
{
"name": "Payment Smart 40yr Fixed",
"productCode": "A40I",
"amortizationType": "Fixed",
"term": 40,
"isEligible": false,
"isRecommended": false,
"agencyType": "NonAgency",
"miType": "BorrowerPaid",
"miFactor": 0,
"undiscountedBaseRate": 6.625,
"undiscountedBasePoints": -0.494,
"documentationType": "full",
"toleranceAmount": 500,
"tolerancePercent": 0.25,
"underwritingSource": "",
"qmUnderwritingType": "AbilityToRepay",
"adjustments": [],
"ineligibilities": [
"Loan Amount must exceed $806500"
],
"prices": []
},
{
"name": "Conforming 30 Year Fixed",
"productCode": "A30",
"amortizationType": "Fixed",
"term": 30,
"isEligible": true,
"isRecommended": false,
"agencyType": "FannieMae",
"miType": "BorrowerPaid",
"miFactor": 0,
"undiscountedBaseRate": 6.375,
"undiscountedBasePoints": -0.386,
"documentationType": "full",
"toleranceAmount": 500,
"tolerancePercent": 0.25,
"underwritingSource": "DU",
"qmUnderwritingType": "VSH",
"adjustments": [
{
"name": "FN R/T L 60.01-70 FICO 740-759",
"points": 0.25
},
{
"name": "10bp Credit",
"points": -0.1
},
{
"name": "Ln Amt $150001-175000",
"points": -0.45
},
{
"name": "Rocket Pro Refi Credit",
"points": -0.3
},
{
"name": "30-Day Commitment",
"points": -0.09
}
],
"prices": [
{
"apr": 7.819,
"rate": 7.75,
"points": -4.125,
"basePoints": -5.091,
"undiscountedAllInPoints": -0.162,
"monthlyPayment": 1253.73,
"miAmount": 0,
"isEligible": true,
"ltv": 0.7,
"cltv": 0.7,
"hcltv": 0.7,
"dti": 0.36666,
"frontEndDTI": 0.20641,
"adjustedRate": 7.75,
"undiscountedAllInRate": 6.625,
"reserveAmount": 0,
"amountFinanced": 173843.35,
"numberOfOddDays": 10,
"perDiemInterest": 37.67,
"premiumAmount": 104.125,
"totalPerDiemInterest": 376.7,
"totalTargetProfit": -885.5,
"totalLenderPaidCredit": 0,
"sellerConcessions": 0,
"cashOutAmount": 0,
"discount": {
"points": -4.125,
"amount": -7218.75
},
"discountAfterComp": {
"points": -4.125000000000001,
"amount": -7218.750000000001
},
"totalLoanAmount": 175000,
"fundsToClose": {
"total": 178564.65,
"details": {
"finalLoanAmount": {
"total": 175000,
"details": {
"vaFundingFee": 0,
"ufmip": 0,
"baseLoanAmount": {
"refinanceDetails": {
"cashOutAmount": 0
}
}
}
},
"nonFinancedAmounts": {
"details": {
"vaFundingFee": 0,
"ufmip": 0,
"netFees": {
"details": {
"aprFees": [
{
"code": "",
"amount": 779.95,
"groupType": ""
}
],
"nonAPRFees": [
{
"code": "",
"amount": 983,
"groupType": ""
}
]
}
},
"netPerDiem": {
"details": {
"numberOfOddDays": 10,
"perDiemInterest": 376.7
}
}
}
},
"totalLenderPaidCredit": 0
}
},
"lockExpirationDate": "2025-08-11T00:00:00",
"commitmentPeriod": 30,
"buydownDurationInYears": 0,
"failedToApplyBuydown": false,
"payments": []
}
]
}
]
} 
```