---
title: List settlements
excerpt: >
  Returns a paged list of settlements for a merchant.


  ### Common filters

  | Filter | Type | Notes |

  |---|---|---|

  | `type` | string | `CreditCard` or `ACH` |

  | `isReconciled` | boolean | `true` to only show reconciled settlements |

  | `page` / `pageSize` | number | Pagination controls |


  ### Notes

  - This table is **Markdown stored inside the OpenAPI `description`** field.

  - Useful for quick “mini docs” on the endpoint without editing the page in
  ReadMe.
api:
  file: pushpay_demo_openapi_FULL_markdown_examples.json
  operationId: listSettlements
hidden: false
---