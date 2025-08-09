---

## Overview

The Gold Layer is the business-level data representation, structured to support analytical and reporting use cases. It consists of **dimension tables** and **fact tables** for specific business metrics

---

### 1. gold.dim_customers

- **Purpose:** Stores customer details enriched with demographic and geographic data
- **Columns:**

| **Column Name** | **Data Type** | **Description** |
| --- | --- | --- |
| customer_key | INT | Surrogate key uniquely identifying each customer record in the dimension table. |
| customer_id | INT | Unique numerical identifier assigned to each customer. |
| customer_name | NVARCHAR(50) | Alphanumeric identifier representing the customer, used for tracking and referencing |
| first_name | NVARCHAR(50) | The customer’s first name, as recorded in the system. |
| last_name | NVARCHAR(50) | The customer’s last name or family name. |
| country | NVARCHAR(50) | The country of residence for the customer (e.g. `Australia`) |
| marital_status | NVARCHAR(50) | The marital status of the customer (e.g. `Married` , `Single`) |
| gender | NVARCHAR(50) | The gender of the customer (e.g. `Male`, `Female`, `n/a`) |
| birthdate | DATE | The date of birth of the customer, formatted as YYYY-MM-DD (e.g., 1971-10-06). |
| create_date | DATE | The date and time when the customer record was created in the system |

---

### 2. gold.dim_products

- **Purpose:** Stores product details enriched with category and product data
- **Columns:**

| **Column Name** | **Data Type** | **Description** |
| --- | --- | --- |
| product_key | INT | Surrogate key uniquely identifying each product record in the product dimension table. |
| product_id | INT | A unique identifier assigned to the product for internal tracking and referencing. |
| product_number | NVARCHAR(50) | A structured alphanumeric code representing the product, often used for categorization or inventory. |
| product_name | NVARCHAR(50) | Descriptive name of the product, including key details such as type, color, and size. |
| category_id | NVARCHAR(50) | A unique identifier for the product’s category, linking to its high-level classification. |
| category | NVARCHAR(50) | The broader classification of the product (e.g., Bikes, Components) to group related |
| sub_category | NVARCHAR(50) | A more detailed classification of the product within the category, such as product type |
| maintenance | NVARCHAR(50) | Indicates whether the product requires maintenance (e.g., `Yes` , `No`) |
| cost | INT | The cost or base price of the product, measured in monetary units. |
| product_line | NVARCHAR(50) | The specific product line or series to which the product belongs (e.g. Road, Mountain) |
| start_date | DATE | The date when the product became available for sale or use, stored in |

---

### 3. gold.fact_sales

- **Purpose:** Stores sales data
- **Columns:**

| **Column Name** | **Data Type** | **Description** |
| --- | --- | --- |
| order_no | NVARCHAR(50) | A unique identifier assigned to the order for internal tracking and referencing. |
| product_key | INT | Surrogate key uniquely identifying each product record in the product dimension table. |
| customer_key | INT | Surrogate key uniquely identifying each customer record in the dimension table. |
| order_date | DATE | Order Date |
| ship_date | DATE | Ship Date |
| due_date | DATE | Due Date |
| sales_amount | INT | The sales amount of this transaction |
| quantity | INT | The quantity of product purchased in this transaction |
| price | INT | The price of product purchased in this transaction |
