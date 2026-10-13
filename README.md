# Menuro for Claude Code

Connect Claude Code to your Menuro account and ask about your orders, sales, menu and customers in
plain language. The connector is read-only: it cannot change an order, a menu item or a customer.

## Install

```bash
claude plugin marketplace add devsaran/menuro-mcp
claude plugin install menuro@menuro-mcp
```

Then start Claude Code, run `/mcp`, choose **menuro** and sign in. Use the email and password you
already use for your Menuro admin dashboard, then choose **Allow**.

Prefer not to use a plugin? Add the server directly:

```bash
claude mcp add --transport http menuro https://mcp.menuro.io/mcp
```

## Who can connect

Staff with the admin, co-admin, outlet owner or outlet manager role. Outlet owners and managers see
only their own outlet. Other roles are refused at sign-in.

## What it can read

| Tool | What it answers |
|---|---|
| `list_orders` | Orders in a date range of up to 31 days, filtered by status, outlet or channel |
| `get_order` | One order in full: items, totals, payment, status and customer |
| `get_sales_summary` | Order count, gross sales, average order value, tips and cancellation rate |
| `get_top_items` | Best-selling items by quantity and revenue |
| `list_menu_categories` | Categories and whether each is on, off, or hidden from a channel |
| `list_menu_items` | Items with prices, sold-out state and per-channel overrides |
| `find_customers` | Customers matching part of a name, phone or email |
| `get_customer` | One customer's order history and balances |

Customer phone numbers and emails are always masked.

## Disconnect

In your Menuro admin dashboard, open the profile menu and choose **Disconnect AI assistants**. This
revokes every assistant connected to your account at once.

## Support

info@menuro.io · [Privacy](https://menuro.io/privacy) · [Terms](https://menuro.io/terms)
