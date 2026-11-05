# Warehouse tools

Small Python utilities for warehouse order and shipping workflows.

Run the tests with `python3 -m unittest discover -s tests -v`.

## Shipping

`shipping_quote(weight_kg, zone, service="standard")` returns a delivery quote
in dollars.

| Parameter  | Values                      | Notes                              |
|------------|-----------------------------|------------------------------------|
| `weight_kg`| positive float              | Parcel weight in kilograms         |
| `zone`     | `"local"`, `"regional"`     | Delivery zone                      |
| `service`  | `"standard"`, `"express"`   | Defaults to `"standard"`           |

**Express** adds a flat **$7.00** surcharge on top of the standard rate.
An unknown zone or service raises `ValueError`.

### CLI examples

```bash
# Standard quote (default)
python -m warehouse.cli 2.5 local

# Express quote
python -m warehouse.cli 2.5 local --service express
```
