---
name: file-expense
description: File an expense report. Use when the user mentions a receipt, reimbursement, or expense, or asks to submit spending for approval.
---

To file an expense:

1. Ask for the receipt if the user hasn't attached one, and read the amount, date, merchant, and currency from it.
2. Call the expenses connector's `create_report` tool with those fields. Default the category from the merchant type; ask only if it's ambiguous.
3. If the amount is over the user's approval limit (check with `get_policy`), add their manager as approver before submitting.
4. Reply with the report number and its approval status. Don't paste the full API response.