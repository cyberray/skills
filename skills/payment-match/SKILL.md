---
name: payment-match
description: Match a bank / PayNow payment to an unpaid order when the bank message has no order number. Use when a shop gets a payment and needs to know which order it paid for.
---

# Payment Match

## What to do
1. Use only the numbers the shop gives: payment amount, payment time, and the list of unpaid orders (order number, total, order time).
2. Find unpaid orders with the same total AND placed within 90 minutes before the payment.
3. If exactly 1 order matches, mark that order Paid. Show the order number, amount, and time.
4. If 0 orders match, leave it for a manual check. Say: No match — check by hand.
5. If 2 or more orders match, leave it for a manual check. Say: More than 1 match — check by hand.
6. Use each payment once only. Never guess, and never mark an order Paid on a guess.
7. No sending, no paying, no filing — just the match, for the shop to see and approve.

## How to show it
- Short list, one line per order checked.
- End with one line: Paid: ORD-XXX $X, or No match — check by hand, or More than 1 match — check by hand.

## Examples (mock data only, not a real shop)
- Example 1: Payment $11 at 12:17. Unpaid orders: ORD-004 $11 at 12:16, ORD-002 $28 at 11:00. Exactly 1 match: ORD-004 Paid.
- Example 2: Payment $28 at 12:30. Unpaid orders: ORD-002 $28 at 12:00, ORD-005 $28 at 12:10. 2 matches: More than 1 match — check by hand.
- Example 3: Payment $15 at 12:30. Unpaid orders: ORD-004 $11, ORD-002 $28. 0 matches: No match — check by hand.

## Guidelines
- Keep it simple enough for a shop owner to check in 30 seconds.
- Use plain words. No jargon.
- The bank message has no order number, only amount, date and time, sender, and bank reference. Do not invent an order number.
- Never mark an order Paid without the shop saying OK, unless the shop already approved the exactly-1-match rule for this skill.
