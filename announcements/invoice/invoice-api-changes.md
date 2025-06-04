## What is changing?

We are introducing changes to improve the accuracy of invoice data returned by our API.
As part of this enhancement, we will be modifying specific fields returned by
`getInvoice` and `getCreditNote` endpoints. These changes will take effect on **July 15, 2025**.

## How might this affect you?

If your integration currently uses the `getInvoice` or `getCreditNote` endpoints, be aware of the following existing behaviours:

- The field `items[n].quantity` is always returned as `1`, regardless of the actual quantity.
- The field `items[n].unitCost` is returned with the same value as `items[n].totalCost`.

## What is changing in the iVvy API?

Starting **July 15, 2025**, the `getInvoice` and `getCreditNote` endpoints will return the following:

- `items[n].quantity`: the actual quantity of the item.
- `items[n].unitCost`: the cost per unit, not the total cost.

## Example

For an item representing 10 menus priced at $23 each:

**Current Output:**
```json
{
  "quantity": 1,
  "unitCost": 230,
  "totalCost": 230
}
```
**After Change:**
```json
{
  "quantity": 10,
  "unitCost": 23,
  "totalCost": 230
}
```
## What should you do?
Please update your integration logic if it currently assumes that:
- `items[n].quantity` is always 1, or
- `items[n].unitCost` is equal to `items[n].totalCost`.

## Related Links
- [getInvoice Documentation](../../invoice/get-invoice.md)
- [getCreditNote Documentation](../../invoice/get-credit-note.md)]

## Need Help?
If you have any questions or concerns regarding this API change please don't hesitate to reach out to our dedicated support team at support@ivvy.com.

