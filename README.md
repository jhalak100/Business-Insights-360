# Business Insights 360

# Project Overview

AtliQ Hardware has been growing quickly in recent years and has decided to use Power BI for data analytics for the first time. The goal is to stay ahead of competitors and make better decisions using data. This project aims to answer important questions from stakeholders about different areas of the business, such as finance, sales, marketing, and supply chain. With this step, AtliQ Hardware hopes to improve its operations and continue leading in the market.

# Explore the Live Power BI Project  

Click the link below to engage with the live Power BI project and explore the interactive dashboard:  [**Live Power BI Project**](https://app.powerbi.com/view?r=eyJrIjoiYjI5ZTdhZmQtZDY4YS00YzQ0LTlkY2EtYTQ2YjFhODUzNjkxIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)

This dashboard provides a comprehensive overview and insights into the project, showcasing the power of data-driven decision-making through Power BI.  


## Tools and Technologies Used

- **SQL**
- **Power BI Desktop**
- **Excel**
- **DAX Language**
- **DAX Studio** (for optimizing the report)


## Power BI Techniques Mastered  

- **Key questions to ask before starting a project**  
- Creating **calculated columns** for data enrichment  
- Building **measures** with DAX for advanced calculations  
- Designing effective **data models** for relationships and hierarchies  
- Using **Bookmarks** to toggle between visuals seamlessly  
- Implementing **page navigation** with interactive buttons  
- Applying the **DIVIDE** function to handle zero-division errors gracefully  
- Creating a **date table** using M language for time-based analysis  
- Setting up **dynamic titles** based on applied filters for context clarity  
- Incorporating **KPI indicators** for performance tracking  
- Adding **conditional formatting** with icons or color-based visuals for better insights  
- Implementing **data validation techniques** to ensure accuracy  
- Working with **Power BI Services** for report publishing and management  
- Publishing reports to **Power BI Services** for broader access  
- Configuring a **personal gateway** for automatic data refresh  
- Creating and managing **Power BI Apps** for sharing reports  
- Collaborating within **workspaces** and managing **access permissions** effectively  

## Business Terms and Metrics  

- **Gross Price**: The total price of a product before any deductions.  
- **Pre-Invoice Deductions**: Adjustments applied to the price before invoicing (e.g., discounts, rebates).  
- **Post-Invoice Deductions**: Adjustments applied after invoicing (e.g., returns, allowances).  
- **Net Invoice Sale**: The final amount after applying all pre- and post-invoice deductions.  
- **Gross Margin**: The difference between sales revenue and the cost of goods sold (COGS).  
- **Net Sales**: Total revenue after accounting for all deductions and returns.  
- **Net Profit**: The final profit after deducting all expenses, taxes, and costs.  
- **COGS (Cost of Goods Sold)**: The total cost incurred to produce and deliver a product.  
- **YTD (Year to Date)**: Performance metrics calculated from the start of the year to the current date.  
- **YTG (Year to Go)**: Metrics or goals remaining for the rest of the year.  
- **Direct Sales**: Sales made directly to consumers without intermediaries.  
- **Retailer**: Businesses that sell products directly to consumers.  
- **Distributors**: Entities that buy products in bulk and distribute them to retailers or other intermediaries.  
- **Consumer**: The end user of a product or service.  

# Company Background  

**AltiQ Hardware** is a rapidly growing company with a global presence. The company specializes in selling computers and computer accessories through three main channels:  

- **Retailers**  
- **Direct Sales**  
- **Distributors**  

Recently, the company experienced an unexpected loss after opening a store in America. This decision was based on surveys, intuition, and limited Excel-based analysis. Meanwhile, competitors have well-established analytics teams enabling them to make data-driven decisions. To stay competitive and ensure better survival in the industry, AltiQ Hardware has decided to build its own analytics team to generate actionable insights and make informed decisions.  

---


# Dataset Overview  

Understanding the available data is crucial before starting any analysis. A clear understanding of the dataset structure ensures efficient and meaningful insights.  

---

## Dataset Components  

### **Dimension Tables**  
These tables contain static data such as customer and product details.  

- **`dim_customer`**  
  - 27 distinct markets (e.g., India, USA, Spain)  
  - 75 distinct customers across all markets  
  - 2 platform types:  
    - **Brick & Mortar**: Physical/offline stores  
    - **E-commerce**: Online stores (e.g., Amazon, Flipkart)  
  - 3 sales channels:  
    - Retailer  
    - Direct  
    - Distributors  

- **`dim_market`**  
  - 27 distinct markets (e.g., India, USA, Spain)  
  - 7 sub-zones  
  - 4 regions:  
    - **APAC**  
    - **EU**  
    - **NAN**  
    - **LATAM**  

- **`dim_product`**  
  - Divisions:  
    - **P & A** (Peripherals & Accessories): Accessories, PC, Notebook, Desktop  
    - **N & S** (Networking & Storage): Networking, Storage  
  - 14 different product categories (e.g., Internal HDD, Keyboard)  
  - Multiple variants available for the same product  

---

### **Fact Tables**  
These tables contain transactional data.  

- **`fact_forecast_monthly`**  
  - Used to forecast customer needs in advance, aiding in:  
    - **Higher customer satisfaction**  
    - **Reduced storage costs**  
  - Denormalized for analytical purposes by the Data Engineering team.  
  - All dates in this table are replaced by the start date of the month.  
  - Includes forecast quantity needed for each customer in the final column.  

- **`fact_sales_monthly`**  
  - Similar structure to `fact_forecast_monthly`, but the final column contains the **sold quantity** instead of the forecasted value.  

---

## Additional Tables (From gdb056)  

- **`freight_cost`**  
  - Details of travel costs and other associated costs per market and fiscal year.  

- **`gross_price`**  
  - Gross price details with product codes.  

- **`manufacturing_cost`**  
  - Manufacturing cost details with product codes and year.  

- **`pre_invoice_deductions`**  
  - Pre-invoice deduction percentages for each customer by year.  

- **`post_invoice_deductions`**  
  - Details of post-invoice and other deductions.  

---

This structured understanding of the dataset provides a foundation for data analysis and ensures a smoother workflow.  

# Importing Data into Power BI  

In this project, the database used is **MySQL**. To import datasets from the MySQL database into Power BI, follow these steps:  

1. **Establish Connection**  
   - Open Power BI Desktop.  
   - Navigate to the **Home** tab and click on **Get Data**.  
   - Select **MySQL Database** from the list of available connectors.  

2. **Provide Database Credentials**  
   - Enter the server name and database name.  
   - Provide the database access credentials (username and password).  

3. **Select Tables**  
   - Once connected, browse the database and select the required tables or views for your analysis.  

4. **Load or Transform Data**  
   - Choose either to load the data directly or transform it in Power Query for cleaning and shaping before analysis.  

This ensures seamless data integration from MySQL to Power BI, allowing for efficient analysis and visualization.  

# Data Model  

Data modeling is a crucial step in building effective Power BI reports. It serves as the foundation upon which all visuals and analyses are built. A well-structured data model improves the overall performance of the report, while poor data modeling can significantly impact performance and user experience.  

### Importance of Data Modeling  
- **Foundation for Reports**: All visuals and insights in the report are based on the data model.  
- **Performance Impact**: A poorly structured model can slow down the report's performance and lead to inefficiencies in analysis.   

### Data Modeling Method Used  
In this project, we have used the **Snowflake Schema** (Snowfall data modeling method) to structure the data model. This method helps in organizing the data in a way that ensures both efficiency and scalability. 

![Model 2](https://github.com/user-attachments/assets/8839d582-ddd1-4d25-b094-1b00e7609285)

## Dashboard Designing

Based on the mock-ups received as requirement, the team will start designing the visuals and create measure as and when required.

## Home View

In the Home View, all the view buttons will be available. The user can navigate to a specific view page by clicking the corresponding button:

- **Info**
- **Finance View**
- **Sales View**
- **Marketing View**
- **Supply Chain View**
- **Executive View**

# Final Overview
https://github.com/user-attachments/assets/d84611a2-c2fc-45d6-a4d4-f4bc6fbecb08



# Home Page 

![overall](https://github.com/user-attachments/assets/df21b75f-f60d-4785-b316-64aab20dc4b0)

# Finance View

![Finnace view](https://github.com/user-attachments/assets/4852c556-538a-4bec-ba2f-aa02a588f04a)


# Sales View
![Sales_view](https://github.com/user-attachments/assets/9f3a9d39-a49d-4123-9649-e61f1222c5d0)


# Marketing View

![Marketinf view](https://github.com/user-attachments/assets/7834b637-514b-4c8a-a23e-864a361b85df)


# Supply chain View

![Supply_chain view](https://github.com/user-attachments/assets/cec30fdf-27f0-4a8e-ac81-6b9fd5cfe724)


# Executive View

![Excecutive_view](https://github.com/user-attachments/assets/ef84865b-ead5-4c37-bc2d-f5a39df861f9)

# Info Page

![infopage](https://github.com/user-attachments/assets/29b25189-2b5f-4b07-b926-8955c10484cb)

# Project Outcome
This report enables data-driven decisions and answers numerous "why" questions, providing actionable insights for various scenarios.




















