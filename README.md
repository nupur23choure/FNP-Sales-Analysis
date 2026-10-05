# Ferns & Petals (FNP) Sales Analysis Dashboard

An end-to-end Excel project: cleaning messy order data with **Power Query**, modelling it with the **Data Model**, and building an interactive **sales dashboard** with Pivot Tables, Pivot Charts and Slicers.

---

## Dashboard

![Dashboard](images/dashboard.png)

---

## Problem Statement

FNP (Ferns & Petals) sells gifts for occasions like Diwali, Raksha Bandhan, Holi, Valentine's Day, Birthdays and Anniversaries. Using order, product and customer data, the goal was to understand **sales trends, customer behaviour and product performance**, and to suggest how FNP can grow sales and improve delivery.

### Business questions answered

1. What is the total revenue?
2. How long does delivery take on average?
3. How do sales change month by month in 2023?
4. Which products earn the most revenue?
5. How much does a customer spend on average?
6. How do the top 5 products perform?
7. Which 10 cities place the most orders?
8. Does a bigger order quantity affect delivery time?
9. How does revenue compare across occasions?

---

## Dataset

| Table | What it contains |
|---|---|
| **Orders** | Order ID, Customer ID, Product ID, Quantity, Order and Delivery date/time, Location, Occasion |
| **Customers** | Customer ID, Name, City, Gender, Contact details, Address |
| **Products** | Product ID, Product name, Category, Price |

**Size:** 1,000 orders, all in 2023.

---

## Tools Used

- **Excel:** Pivot Tables, Pivot Charts, Slicers, formulas
- **Power Query:** data cleaning and transformation
- **Excel Data Model:** relationships between the three tables

---

## Approach

### 1. Data cleaning (Power Query)

The raw date columns were inconsistent: some were real dates, some were text like `24/02/2023`, and many had **day and month swapped**. This gave negative delivery times (delivery before order).

**Fix:** for each order I tested both readings of every date (as written, and day/month swapped) and kept the combination where delivery falls 0 to 15 days after the order. All 1,000 rows had exactly one valid reading, so no guessing was needed. Afterwards, delivery times ranged from **1 to 10 days** with no negatives.

### 2. Data modelling

Loaded Orders, Customers and Products into the **Data Model** and linked them:

- `Orders[Customer_ID]` → `Customers[Customer_ID]`
- `Orders[Product_ID]` → `Products[Product_ID]`

### 3. Calculated metrics

- **Delivery time** = Delivery date − Order date (in days)
- **Average order value** = Total revenue ÷ Total orders

### 4. Dashboard

Built a pivot chart for each question, added KPI cards, and connected slicers (**Order Date, Delivery Date, Occasion**) so every chart updates together.

---

## 📈 Key Results

| Metric | Value |
|---|---|
| Total orders | **1,000** |
| Total revenue | **$3,520,984** |
| Average order value | **$3,520.98** |
| Average delivery time | **5.53 days** |

###  Insights

- **Seasonality:** revenue peaks in **February** (Valentine's season) and **August** (Raksha Bandhan). April to July is the slowest period.
- **Occasions:** **Anniversary** earns the most, followed by **Raksha Bandhan**. **Diwali is the lowest.**
- **Customers:** orders are split almost evenly, **51% men and 49% women**.
- **Delivery vs quantity:** order quantity has **no effect on delivery time** (correlation ≈ 0.00). Average delivery is about 5 to 6 days for every quantity from 1 to 5.
- **Why Diwali is low:** it has only **95 orders (9.5% of the total)** and just 7 different products. Order size and delivery speed were normal, so the gap comes from order volume. The data can't prove the cause; possible reasons are a limited product range and little festive marketing.

###  Top 5 Products

| Rank | Product | Revenue |
|---|---|---|
| 1 | Magnam Set | $121,905 |
| 2 | Quia Gift | $114,476 |
| 3 | Dolores Gift | $106,624 |
| 4 | Harum Pack | $101,556 |
| 5 | Deserunt Box | $97,665 |

---

##  Recommendations

1. **Run offers in slow months** (April to July) with discounts or new occasion bundles.
2. **Stock early for Anniversary and Raksha Bandhan**, the top earners.
3. **Boost Diwali** with festive hampers, a wider product range and an earlier campaign.
4. **Time promotions by day**, using the best-selling days and mid-week deals for weaker ones.

---

## What I Learned

- Data cleaning decides whether the analysis is right: wrong dates gave wrong delivery times.
- How to build relationships in the Excel Data Model.
- How to turn pivot tables into a clear, interactive dashboard.
- How to turn numbers into business recommendations.

---

##  Author

**Nupur**  
Aspiring Data Analyst | SQL · Python · Power BI · Excel

🔗 LinkedIn: [Nupur Choure](https://www.linkedin.com/in/nupur-choure-923314390)

⭐ If you found this project useful, feel free to star the repository.
