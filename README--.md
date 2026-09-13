# E-Commerce Sales Analysis (SQL)

A relational database project analyzing e-commerce sales data using MySQL — built as part of the Data Analytics certification at Besant Technologies.

## Objective

Analyze e-commerce sales data to answer real business questions:
- Which products sell the most, and which generate the most revenue?
- Who are the high-value customers?
- How do sales trend month over month?
- Which products are underperforming (never ordered)?

## Database Design

The schema has 5 normalized tables:

| Table | Description |
|---|---|
| `customers` | Customer details (id, name, email, city) |
| `products` | Product catalog (id, name, category, price, stock) |
| `orders` | Order records linked to customers |
| `order_details` | Line items per order (product, quantity, unit price) |
| `payments` | Payment records linked to orders |

**Constraints used:** PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK (e.g. price > 0, quantity > 0) — to keep the data consistent and realistic.

### ER Diagram

customers (1) ──< orders (1) ──< order_details >── (1) products
orders (1) ──< payments

(See `er-diagram.png` for the full diagram with field types.)

## What's in this repo

- **`schema.sql`** — table creation statements with all constraints
- **`queries.sql`** — 20+ analysis queries: joins, subqueries, aggregation (GROUP BY / HAVING), window functions (RANK), a view, an index, and a stored procedure
- **`er-diagram.png`** — entity relationship diagram

## Sample Insights

- Identified the best-selling product by total quantity sold
- Ranked all products by revenue using a window function
- Flagged customers with total order value above ₹10,000
- Built a reusable view (`high_value_orders`) for repeat reporting
- Added an index on `order_date` to speed up date-range lookups
- Wrote a stored procedure to fetch orders for any given date range on demand

## Tools

MySQL / MySQL Workbench

## Author

Chandana B — [LinkedIn](https://linkedin.com/in/chandana-b-5569b53b5) · [GitHub](https://github.com/chandanab-09)
