---
title: Search settlements (demo for requestBody examples)
excerpt: >
  Demo endpoint to show **requestBody examples** and Markdown-in-spec rendering
  in ReadMe.


  ### Request fields

  | Field | Type | Description |

  |---|---|---|

  | `type` | string | Settlement type filter |

  | `isReconciled` | boolean | Reconciled filter |

  | `estimatedDepositDateFrom/To` | string(date-time) | Date range filter |

  | `page` / `pageSize` | number | Pagination |


  ### Why this exists

  - GET endpoints usually don’t have a `requestBody`.

  - This POST is only to demonstrate request-body examples in the API Reference.
api:
  file: pushpay_demo_openapi_FULL_markdown_examples.json
  operationId: searchSettlements
hidden: false
---