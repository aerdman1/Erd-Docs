---
title: Raw pipes without valid table structure
excerpt: >
  This endpoint has pipe characters but should not necessarily become a proper
  table.


  | test | test | test |

  | test | test | test |


  There is no proper separator row above.
api:
  file: FIS_test.yaml
  operationId: get_raw-pipes-no-table
hidden: false
---