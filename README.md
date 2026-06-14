# Sales Performance Dashboard

An Excel-based sales analytics project that summarizes order-level sales, profit, and quantity data across customer segments, product categories, and shipping modes, presented through a single-page KPI and chart dashboard.

## What's in here

- <a href="https://github.com/Manohar-92/Sales-Performance-Dashboard/blob/main/Orders-Filled.xlsx">Orders-Filled.xlsx<a/> – the main file. Has the raw order data, the pivot tables behind the charts, and the dashboard itself.
- <a href="">Orders-With_Nulls.xlsx<a/> – same data but with a few Sales/Profit values missing (Order IDs 32, 35, 36, 65). Kept this around for testing how the pivots/charts handle blanks.
- <a href="https://github.com/Manohar-92/Sales-Performance-Dashboard/commit/218de5d87b35062b79441bf4294e64ec1bd38b2a">Orders_Sales_Performance_Dashboard.png<a/> – screenshot of the finished dashboard.

## The data

1,007 order line items / 660 distinct orders, columns are:

Order ID, Order Date, Order Quantity, Sales, Ship Mode, Profit, Unit Price, Customer Name, Customer Segment, Product Category

- Customer Segment: Consumer, Corporate, Home Office, Small Business
- Product Category: Furniture, Office Supplies, Technology
- Ship Mode: Regular Air, Express Air, Delivery Truck

## Orders-Filled.xlsx layout

- **Orders Sheet** – raw data, no blanks
- **Pivot** – all the pivot tables feeding the dashboard (sales by segment, sales by ship mode, sales trend over time, sales by category, profit by segment, ship mode performance, top orders, quantity by segment)
- **Dashboard** – the actual dashboard page

## Dashboard Layout

The `Dashboard` sheet (and the PNG screenshot) is organized as follows:

1. **KPI summary row** – Total Sales, Total Profit, Total Qty Sold, Avg Unit Price, Profit Margin, Total Orders
2. **Sales by Segment** – donut chart of sales share by Consumer / Corporate / Home Office / Small Business
3. **Sales & Profit by Ship Mode** – bar chart comparing sales and profit across Regular Air, Express Air, and Delivery Truck
4. **Sales by Product Category** – bar chart of sales for Technology, Office Supplies, and Furniture
5. **Profit by Customer Segment** – column chart of profit per segment
6. **Avg Profit by Ship Mode** – column chart of average profit per order by ship mode
7. **Order Quantity by Segment** – column chart of total units ordered per segment

All charts are driven by pivot tables on the `Pivot` sheet, which in turn reference `Orders Sheet`.

<img width="1310" height="756" alt="Orders Sales Performance Dashboard" src="https://github.com/user-attachments/assets/79dcef1a-bf92-4bbc-9e6f-39a5f00d827e" />


## Known issue / to fix

The KPI row at the top isn't right — Total Sales and Total Profit are showing the exact same number, Avg Unit Price shows $0.00, and Profit Margin shows 100%. Pretty sure the formulas are pointing at the wrong range. Actual numbers from the Orders Sheet:

- Total Sales: ~$1,880,516
- Total Profit: ~$218,028
- Total Qty Sold: 25,006
- Avg Unit Price: ~$91.26
- Profit Margin: ~11.6%
- Total Orders: 660

Need to go back and re-link those cells to the Orders Sheet / Pivot tables.

## To do
- [ ] Fix the KPI formulas
- [ ] Maybe add a year-over-year trend chart
- [ ] Test against the nulls version once formulas are fixed
