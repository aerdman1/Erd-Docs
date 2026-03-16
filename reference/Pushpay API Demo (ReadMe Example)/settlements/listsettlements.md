---
title: List settlements
excerpt: >-
  **Description**  <br /> *Version 1*  <br /> Create a new ACH template. API
  allows users to create new ACH (Automated Clearing House) templates for
  processing electronic payments. It streamlines the setup of payment
  instructions and associated account details, facilitating efficient
  transaction management. Upon creation, the templates are set to a pending
  approval status, ensuring a review process is in place. For sample request and
  response, refer to the payload section [Create ACH
  Template](https://api.dragonflyft.com/trial/reference/createtemplate) <br />
  The table below indicates the mandatory fields that need to be keyed in to
  generate a successful response.  <br />| S.No | Mandatory Fields |
  Description                                  | Location       | Sample
  data           || :----| :--------------- |
  :------------------------------------------- | :--------------|
  :-------------------- || 1    | sec_code         | Secondary
  code                               | PATH PARAMS    | CCD   || 2    |
  requestUID       | Prepopulated                                 | BODY
  PARAMS    | DummyRequestIDValue   || 3    | baseServiceRqVersion  |
  Prepopulated                            | BODY PARAMS    |
  5                     || 4    | templateCreateRqVersion  |
  Prepopulated                         | BODY PARAMS    | 1                    
  || 5    | templateName     | Unique name for the template                   |
  BODY PARAMS-> achtemplateInfo object |  Template123  || 6    |
  ident            | Financial institution identifier       | BODY PARAMS->
  achtemplateInfo object-> paymentAccountInfo array-> financialInstitution
  object | AT611904300234573201 || 7    | identType        | Financial
  institution identifier type  | BODY PARAMS-> achtemplateInfo object->
  paymentAccountInfo array-> financialInstitution object | ACCTIDIBAN || 8    |
  accountUID       | Unique encoded number of AccountID           | BODY
  PARAMS-> achtemplateInfo object-> paymentAccountInfo-> accountIdent object  |
  d376a497-bfa1-48c7-9b19-4a21bb209c7d || 9    | hostProductCode  | Identifier
  for the product associated with the origination account | BODY PARAMS->
  achtemplateInfo object-> paymentAccountInfo array | BC1C || 10   |
  currency         | Preferred currency code in three digits    | BODY PARAMS->
  achtemplateInfo object-> amount object  | USD || 11   | amount           |
  Amount                                     | BODY PARAMS-> achtemplateInfo
  object-> amount object  | 1000 || 12   | ident            | Financial
  institution identifier             | BODY PARAMS-> achtemplateInfo->
  recipients array-> ident object | AT611904300234573201 || 13   |
  identType        | Financial institution identifier type  | BODY PARAMS->
  achtemplateInfo-> recipients array-> ident object | ACCTIDIBAN    || 14   |
  name             | Financial institution name             | BODY PARAMS->
  achtemplateInfo-> recipients array-> ident object | US Payments Bank || 15   |
  ident            | Financial institution identifier       | BODY PARAMS->
  achtemplateInfo object-> recipients array-> accountInfo object->
  financialInstitution object | 231278122 || 16   | identType        | Financial
  institution identifier type  | BODY PARAMS-> achtemplateInfo object->
  recipients array-> accountInfo object-> financialInstitution object | 0 ||
  17   | primaryIdent     | Primary account identifier             | BODY
  PARAMS-> achtemplateInfo object-> paymentAccountInfo array-> accountIdent
  object | d376a497-bfa1-48c7-9b19-4a21bb209c7d || 18   | accountType      |
  Type of account                        | BODY PARAMS-> achtemplateInfo
  object-> paymentAccountInfo array | Savings   || 19   | creditDebitType  |
  Indicator to denote if credit or debit | BODY PARAMS-> achtemplateInfo
  object     |  CRDT  || 20   | statusType       |
  statusType                             | BODY PARAMS-> achtemplateInfo object 
  |  2   || 21   | companyEntryDescription | Company entry
  description             | BODY PARAMS-> achtemplateInfo object  | ACH Company
  name || 22   | achcompanyID     | Encrypted value of ACH Company identifier  |
  BODY PARAMS-> achtemplateInfo object  | QUNIX1Rlc3Q= || 23   |
  achcompanyName   | Encrypted value of ACH Company Name        | BODY PARAMS->
  achtemplateInfo object  | QUNIX1Rlc3Q= || 24   | templateActivationDate    |
  Date when template is ready to use  | BODY PARAMS-> achtemplateInfo object  
  |  2025-11-10T11:48:49.890Z  | | 25   | isTemplateActive | Indicator to denote
  if template can be used (Active) or not(Inactive)  | BODY PARAMS->
  achtemplateInfo object | true | <br /> The table below indicates the
  conditional / optional fields that can be keyed in to generate a successful
  response.  <br />| S.No | Conditional / Optional Fields |
  Description                       | Location       | Sample data            | 
  | :----| :---------------------------- | :-------------------------------- |
  :--------------| :--------------------  || 1    | versionStampId   | Version
  information of the resource object     | BODY PARAMS-> achtemplateInfo    | 
  VDBKV1UwNUk3Wl8y     | | 2    | templateIdent    | Unique identifier is a
  number generated by the application for internal tracking | BODY PARAMS->
  achtemplateInfo object |  ESZV2Z3Y40  | | 3    | templateName     | Unique
  name for the template                   | BODY PARAMS-> achtemplateInfo object
  |  Template123  | | 4    | templateAmountIndicator | Field to indicate whether
  template is created with exactAmount or changeable amount | BODY PARAMS->
  achtemplateInfo object |  Indicator123 | | 5    | currency         | Preferred
  currency code in three digits        | BODY PARAMS-> achtemplateInfo object->
  templateLimit object | USD  | | 6    | amount           |
  amount                                         | BODY PARAMS-> achtemplateInfo
  object-> templateLimit object | 1000 || 7    | templateApprovalsNumber   |
  Number of approvals required for payments generated from the template | BODY
  PARAMS-> achtemplateInfo object  | 2  | | 8    | lastUsedDateTime          |
  Field to indicate when the last time template was used to create a payment  |
  BODY PARAMS-> achtemplateInfo object | 2025-11-10T11:48:49.890Z  | | 9    |
  paymentIdent     | Unique identification to unambiguously identify the payment
  within the message | BODY PARAMS-> achtemplateInfo object | CCD1 | | 10   |
  serverId         | Confirmation number for payment received from
  host                             | BODY PARAMS-> achtemplateInfo object |
  ServerID  || 11   | paymentType      | Specifies the type of payment that will
  be used to move the amount of money | BODY PARAMS-> achtemplateInfo object | 
  CCD || 12   | paymentStatus    | Code identifying the payment status    | BODY
  PARAMS-> achtemplateInfo object   |  pending approval | | 13   |
  versionStampId   | Version information of the resource object | BODY PARAMS->
  achtemplateInfo object-> paymentAccountInfo array | VDBKV1UwNUk3Wl8y  || 14  
  | name             | Financial institution name             | BODY PARAMS->
  achtemplateInfo object-> paymentAccountInfo array-> financialInstitution
  object | US Payments Bank || 15   | city             | Name of the
  city                       | BODY PARAMS-> achtemplateInfo object->
  paymentAccountInfo array-> financialInstitution object->address object |
  Cranston || 16   | code             | State abbreviation                     |
  BODY PARAMS-> achtemplateInfo object-> paymentAccountInfo array->
  financialInstitution object->address object-> stateProvince object | RI |  |
  17   | name             | Name of state or province, limited to 70
  characters   | BODY PARAMS-> achtemplateInfo object-> paymentAccountInfo
  array-> financialInstitution object->address object-> stateProvince object |
  RHODE ISLAND |  | 18   | stateCodeAndNameVersion | Defaults to
  1                   | BODY PARAMS-> achtemplateInfo object->
  paymentAccountInfo array-> financialInstitution object->address object->
  stateProvince object | 1 |  | 19   | countyDistrict   | Identifier of a county
  (county name) in US, district or region  | BODY PARAMS-> paymentAccountInfo
  object-> paymentAccountInfo array-> financialInstitution object->address
  object   | Warwick |  | 20   | postalCode       | Postal
  code                            | BODY PARAMS-> achtemplateInfo object->
  paymentAccountInfo array-> financialInstitution object->address object | 02818
  | | 21   | countryCode      | Specifies the country code in the format of
  character string  | BODY PARAMS-> paymentAccountInfo object->
  paymentAccountInfo array-> financialInstitution object->address object | US | 
  | 22   | genericLocationVersion  | Defaults to 1                   | BODY
  PARAMS-> achtemplateInfo object-> paymentAccountInfo array->
  financialInstitution object->address object | 1 || 23   | addressLine      |
  addressLine                            | BODY PARAMS-> achtemplateInfo
  object-> paymentAccountInfo array-> financialInstitution object->address
  object | 123, PONTIAC AVENUE || 24   | streetName       | Name of
  street                         | BODY PARAMS-> achtemplateInfo object->
  paymentAccountInfo array-> financialInstitution object->address object | Hope
  Street  || 25   | addressType      | Type of address                        |
  BODY PARAMS-> achtemplateInfo object-> paymentAccountInfo array->
  financialInstitution object->address object | Business |  | 26   |
  genericAddressVersion  | Defaults to 1                    | BODY PARAMS->
  achtemplateInfo object-> paymentAccountInfo array-> financialInstitution
  object->address object | 2 || 27   | postOfficeBox    | Post Office
  Box                        | BODY PARAMS-> achtemplateInfo object->
  paymentAccountInfo array-> financialInstitution object->address object   | PO
  Box 123 |  | 28   | bankOption       | Bank option                           
  | BODY PARAMS-> achtemplateInfo object-> paymentAccountInfo array->
  financialInstitution object | ACH |  | 29   | standardBank       | Indicator
  to denote if standard bank is tur or false | BODY PARAMS-> achtemplateInfo
  object-> paymentAccountInfo array-> financialInstitution object  | True |  |
  30   | paymentFinancialInstitutionVersion  | Defaults to 1       | BODY
  PARAMS-> achtemplateInfo object-> paymentAccountInfo array->
  financialInstitution object | 1 || 31   | maskedAccountId  | Masked account
  ID                      | BODY PARAMS-> achtemplateInfo object->
  paymentAccountInfo array-> accountIdent object | || 32   | ident            |
  Financial institution identifier       | BODY PARAMS-> achtemplateInfo
  object-> paymentAccountInfo array-> accountIdent object-> otherIdents array |
  552 || 33   | issuer           | Name of the authority that assigns the
  identification | BODY PARAMS-> achtemplateInfo object-> paymentAccountInfo
  array-> accountIdent object-> otherIdents array | Bank Of America    || 34   |
  accountOtherIdentificationVersion | Defaults to 1         | BODY PARAMS->
  achtemplateInfo object-> paymentAccountInfo array-> accountIdent object->
  otherIdents array  | 1 || 35   | paymentAccountIdentificationVersion |
  Defaults to 1       | BODY PARAMS-> achtemplateInfo object->
  paymentAccountInfo array-> accountIdent object | 1 || 36   | accountName     
  | Name of the account                    | BODY PARAMS-> achtemplateInfo
  object-> paymentAccountInfo array | Account One || 37   | accountNickName  |
  Nickname of account as shown in SAM    | BODY PARAMS-> achtemplateInfo
  object-> paymentAccountInfo array | MySavings || 38   | balanceAmount    |
  Balance of account                     | BODY PARAMS-> achtemplateInfo
  object-> paymentAccountInfo array | 1000.00   || 39   | product          |
  Product                                | BODY PARAMS-> achtemplateInfo
  object-> paymentAccountInfo array | CB Business Checking  || 40   |
  productType      | Product type                           | BODY PARAMS->
  achtemplateInfo object-> paymentAccountInfo array | Deposit || 41   |
  currency         | Preferred currency code in three digits      | BODY
  PARAMS-> achtemplateInfo object-> paymentAccountInfo object  |  USD || 42   |
  fundId           | Fund ID associated with the company    | BODY PARAMS->
  achtemplateInfo object-> paymentAccountInfo array | 34545 || 43   |
  accountInfoVersion | Defaults to 1                              | BODY
  PARAMS-> achtemplateInfo object-> paymentAccountInfo object | 1 || 44   |
  convertedAmount  | In cross currency payment, this field represent the
  equivalent amount for amount entered while payment creation | BODY PARAMS->
  achtemplateInfo object |    | | 45   | baseCurrencyCode  | Currency of the
  instruction amount                 | BODY PARAMS-> achtemplateInfo object  | 
  USD          | | 46   | quotedCurrencyCode  | Currency in which amount needs
  to be converted   | BODY PARAMS-> achtemplateInfo object-> exchangeRateInfo |
  EUR || 47   | rate              | Exchange rate between the currency
  pair            | BODY PARAMS-> achtemplateInfo object-> exchangeRateInfo
  |     | | 48   | rateType          | Rate Type for which exchange rate inquiry
  was done | BODY PARAMS-> achtemplateInfo object  |  SPOT | | 49   |
  bookingRate       | Booking rate                                 | BODY
  PARAMS-> achtemplateInfo object    | True  | | 50   | contractID        |
  contractID                                   | BODY PARAMS-> achtemplateInfo
  object    |    | | 51   | dealId            |
  dealId                                       | BODY PARAMS-> achtemplateInfo
  object    |    | | 52   | exchangeRateType  | Type of exchange
  rate                        | BODY PARAMS-> achtemplateInfo object->
  exchangeRateInfo object | SPOT  || 53   | exchangeRateRule  |
  exchangeRateRule                             | BODY PARAMS-> achtemplateInfo
  object-> exchangeRateInfo object | || 54   | exchangeRateInfoVersion  |
  Defaults to 1                         | BODY PARAMS-> achtemplateInfo object->
  exchangeRateInfo object | 1 || 55   | paymentValueDate  | The date on which
  the transfer will be made  | BODY PARAMS-> achtemplateInfo object    |
  2025-11-10T11:48:49.890Z | | 56   | paymentSendDate   | Date when the payment
  will be sent out for further processing  | BODY PARAMS-> achtemplateInfo
  object | 2025-11-10T11:48:49.890Z | | 57   | isConfidential    | Flag denotes
  payment information is confidential and only visble if user has confidential
  batches entitlement | BODY PARAMS-> achtemplateInfo object    |True  | | 58  
  | recurringScheduleType | Timing for the recurring transfer or future transfer
  | BODY PARAMS-> achtemplateInfo object-> recurringInfo object | 1  || 59   |
  endDate           | An end date for the last recurring transfer  | BODY
  PARAMS-> achtemplateInfo object-> recurringInfo object |
  2025-12-27T09:03:46.804 || 60   | numberOfPayments  | Number of recurring
  transfers to be made     | BODY PARAMS-> achtemplateInfo object->
  recurringInfo object | 12 || 61   | adjustedValueDateRule | The action to take
  if the payment falls on a weekend or holiday. Options include: Move payment to
  next processing day or Move payment to previous processing day. | BODY
  PARAMS-> achtemplateInfo object-> recurringInfo object | F  || 62   |
  numberOfPaymentsOption | The timing for the recurring payment or future
  payment schedule.  Values are ""0"" - Continue until further notice ""1"" -
  Number of Payments ""2"" - End Date | BODY PARAMS-> achtemplateInfo object->
  recurringInfo object |  1  || 63   | isActive         | Template active - true
  or false               | BODY PARAMS-> achtemplateInfo object-> recurringInfo
  object | false || 64   | isLastRecurrence | Current recurrence is last in
  series or not   | BODY PARAMS-> achtemplateInfo object-> recurringInfo object
  | True || 65   | currentSeqNum    | Current Sequence Number of
  Payment            | BODY PARAMS-> achtemplateInfo object-> recurringInfo
  object | 2 || 66   | startDate        | Start date of
  Payment                         | BODY PARAMS-> achtemplateInfo object->
  recurringInfo object | 2025-11-27T09:23:30.496Z || 67   | lastGenDate      |
  Last generated date of Payment                | BODY PARAMS-> achtemplateInfo
  object-> recurringInfo object | 2025-11-27T09:23:30.496Z || 68   |
  recurringInfoVersion| Prepopulated                               | BODY
  PARAMS-> achtemplateInfo object-> recurringInfo OBJECT | 1 || 69   |
  paymentReference | action                                        | BODY
  PARAMS-> achtemplateInfo object    |  ActionValue          | | 70   |
  approveOnSubmit  | On submit the instruction is approved         | BODY
  PARAMS-> achtemplateInfo OBJECT | True || 71   | AuthorizationMemo | Memo
  added during authorization of approval / reject | BODY PARAMS->
  achtemplateInfo object | Approved this payment  || 72   |
  basePaymentInfoVersion  | Defaults to 1                   | BODY PARAMS->
  achtemplateInfo object  | 1  || 73   | extendedFieldName             |
  extendedFieldName                | BODY PARAMS-> achtemplateInfo object->
  additionalAttributes array  | CustomField || 74   |
  extendedFieldValue            | extendedFieldValue               | BODY
  PARAMS-> achtemplateInfo object-> additionalAttributes array  | CustomValue ||
  75   | extendedFieldType             | extendedFieldType                | BODY
  PARAMS-> achtemplateInfo object-> additionalAttributes array  | string || 76  
  | dynamicAttributeVersion       | Prepopulated                     | BODY
  PARAMS-> achtemplateInfo object-> additionalAttributes array  | 1 || 77   |
  offsetCreationLevelType       | offsetCreationLevelType          | BODY
  PARAMS-> achtemplateInfo object    |  LevelTypeA           | | 78   |
  companyDiscretionaryData      | companyDiscretionaryData         | BODY
  PARAMS-> achtemplateInfo object    |  Data123              | | 79   |
  sameDayAchDisclaimerAccepted  | Is sameDayAchDisclaimerAccepted  | BODY
  PARAMS-> achtemplateInfo object    |  True                 || 80   |
  webPrenoteMandateDisclaimerAccepted  | Is webPrenoteMandateDisclaimerAccepted 
  | BODY PARAMS-> achpaymentInfo object    |  False          | | 81   |
  destinationCountry            | Destination country              | BODY
  PARAMS-> achtemplateInfo object    |  US         | | 82   |
  destinationCurrency           | Destination currency             | BODY
  PARAMS-> achtemplateInfo object    |  USD        | | 83   |
  recurringIndicator            | Indicator for recurring          | BODY
  PARAMS-> achtemplateInfo object    |  true       | | 84   |
  displayAuthTypeKey            | displayAuthTypeKey               | BODY
  PARAMS-> achtemplateInfo object    |  Key123     | | 85   |
  versionStampId                | Version information of the resource object |
  BODY PARAMS-> achtemplateInfo object-> recipients array  |  VDBKV1UwNUk3Wl8y 
  | | 86   | uniqueIdent                   | Unique ident for recipient       |
  BODY PARAMS-> achtemplateInfo object-> recipients array  |  UniqueID123  | |
  87   | nickname                      | nickname                         | BODY
  PARAMS-> achtemplateInfo object-> recipients array-> ident object |  | | 88  
  | recipientIdentVersion         | Defaults to 1                    | BODY
  PARAMS-> achtemplateInfo object-> recipients array-> ident object    |  1  | |
  89   | groupIdent                    | Group id                         | BODY
  PARAMS-> achtemplateInfo object    |    | | 90   |
  paymentType                   | Specifies the type of payment that will be
  used to move the amount of money | BODY PARAMS-> achtemplateInfo object->
  paymentType array |  CCD | | 91   | accountInfo                   | Specifies
  the account details associated with money movement | BODY PARAMS->
  achtemplateInfo object-> accountInfo object |  | | 92   |
  contactInfo                   | Specifies the contact details associated with
  money movement | BODY PARAMS-> achtemplateInfo object-> contactInfo object | 
  | | 93   | saveToMasterList              | Recipient needs to be saved in
  master recipient list or not  | BODY PARAMS-> achtemplateInfo object |  True |
  | 94   | approveOnSubmit               | Payment receives one of its required
  approvals upon submission  | BODY PARAMS-> achtemplateInfo object |  True  | |
  95   | masterRecipient               | Field represent if the recipient is
  master receipient or not | BODY PARAMS-> achtemplateInfo object    |  False ||
  96   | masterUniqueIdent             | Unique identifier for Master recipient
  | BODY PARAMS-> achpaymentInfo object  |      | | 97   |
  baseRecipientInfoVersion      | Defaults to 1                     | BODY
  PARAMS-> achpaymentInfo object    |  1  | | 98   |
  secondaryAccountInfo          | Details of the secondary account  | BODY
  PARAMS-> achpaymentInfo object-> secondaryAccountInfo object |  | | 99   |
  secondaryAccountPaymentAllocation  | Details of the secondary account payment
  allocation  | BODY PARAMS-> achtemplateInfo object->
  secondaryAccountPaymentAllocation object    |    | | 100  |
  vendorBillingNumber           | Vendor Billing Number             | BODY
  PARAMS-> achtemplateInfo object    |  335434  | | 101  |
  prenoteStatus                 | Status of pre note                | BODY
  PARAMS-> achtemplateInfo object    |  StatusC | | 102  |
  prenoteExpirationDate         | Expiration date of prenote        | BODY
  PARAMS-> achtemplateInfo object    |  2025-11-10T11:48:49.890Z || 103  |
  destinationCurrency           | Currency of the destination country  | BODY
  PARAMS-> achtemplateInfo object    |  USD  | | 104  |
  destinationCountry            | Name of the destination country      | BODY
  PARAMS-> achtemplateInfo object    |  USA  | | 105  |
  currency                      | Preferred currency code in three digits | BODY
  PARAMS-> achtemplateInfo object-> amount |  USD | | 106  |
  amount                        | Amount                            | BODY
  PARAMS-> achtemplateInfo object-> amount |  1000  | | 107  |
  recipientIndex                | recipientIndex                    | BODY
  PARAMS-> achtemplateInfo object  |  Index123   || 108  |
  discretionaryData             | discretionaryData                 | BODY
  PARAMS-> achtemplateInfo object  |  DataC   | | 109  |
  checkNumber                   | Check number                      | BODY
  PARAMS-> achtemplateInfo object  |  35657555   | | 110  |
  transactionTypeCode           | Code for transaction type         | BODY
  PARAMS-> achtemplateInfo object  |  TypeCodeC  | | 111  |
  currency                      | Preferred currency code in three digits | BODY
  PARAMS-> achtemplateInfo object-> additionalFee object  |  USD | | 112  |
  amount                        | Amount                            | BODY
  PARAMS-> achtemplateInfo object-> additionalFee object  | 2000 | | 113  |
  traceNumber                   | Trace number                      | BODY
  PARAMS-> achtemplateInfo object  |    | | 114  | memo                         
  | Memo entered during approval or rejection of the payment  | BODY PARAMS->
  achtemplateInfo object |  Approving this transaction | | 115  |
  ctxQuickInvoiceEntry          | ctxQuickInvoiceEntry              | BODY
  PARAMS-> achtemplateInfo object  | False | | 116  |
  authCode                      | Authentication code               | BODY
  PARAMS-> achtemplateInfo object  | 346464 | | 117  |
  addendaIdent                  | Identifier of the addenda         | BODY
  PARAMS-> achtemplateInfo object-> paymentAddendaInfo array |
  ActionValue          | | 118  | addenda                       |
  Addenda                           | BODY PARAMS-> achtemplateInfo object->
  paymentAddendaInfo array | Addenda information  | | 119  |
  achpaymentRecipientAddendaInfoVersion  | version details          | BODY
  PARAMS-> achtemplateInfo object-> paymentAddendaInfo array |   | | 120  |
  isDeleted                     | isDeleted                         | BODY
  PARAMS-> achtemplateInfo object  | True  | | 121  |
  isReversed                    | isReversed                        | BODY
  PARAMS-> achtemplateInfo object  | False || 122  |
  achpaymentRecipientinfoVersion | version details                  | BODY
  PARAMS-> achtemplateInfo object  |       | | 123  |
  achrecipientInfoVersion        | version details                  | BODY
  PARAMS-> achtemplateInfo object  |       | | 124  |
  iatoriginatorCompanyName       | Company name of the IAT originator | BODY
  PARAMS-> achtemplateInfo object  |  Target          | | 125  |
  iatoriginatorCompanyTaxID      | Company Tax ID of the IAT originator | BODY
  PARAMS-> achtemplateInfo object |      | | 126  |
  iatoriginatorAddress           | Address for the IAT originator   | BODY
  PARAMS-> achtemplateInfo object    |       | | 127  |
  iatfundingForeignBank          | Funding bank of IAT              | BODY
  PARAMS-> achtemplateInfo object    |       | | 128  |
  achpaymentInfoVersion          | version details                  | BODY
  PARAMS-> achtemplateInfo object    |       |  Note: This is a partial list,
  some fields are not listed here.
api:
  file: pushpay_demo_openapi_FULL_markdown_examples.json
  operationId: listSettlements
hidden: false
---
 
