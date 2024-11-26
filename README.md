# Footwear-Sales-Analytics

## Project Overview
The Footwear Sales Analytics project leverages a comprehensive dataset sourced from Kaggle (link: Kaggle Dataset), providing valuable insights into footwear sales trends, customer buying behaviors, and market preferences. The dataset covers various aspects of the footwear market, including shoe types, pricing, brands, and categories. By analyzing this data, the project aims to uncover key patterns, optimize pricing strategies, identify emerging trends, and provide actionable recommendations for footwear brands and retailers.

This analysis focuses on popular brands like Nike, New Balance, and Fila, and shoe categories such as Running Shoes and Casual Shoes. By exploring relationships between variables like price points, materials, gender preferences, and product categories, the project offers a data-driven approach to enhancing sales performance, inventory management, and targeted marketing.

The dataset contains the following key attributes:

 - Brand: The brand of the footwear (e.g., Nike, New Balance).
 - Type: The product type (e.g., Running Shoes, Casual Shoes).
 - Gender: The target gender for the footwear (e.g., Men, Women).
 - Size: The purchased sizes for each shoe (e.g., 7, 8, 9, etc.).
 - Color: The color(s) of the footwear (e.g., Black, Red, Blue
 - Material - The type of material used (e.g., Mesh, Leather, Synthetic).
 - Price(USD) - The price of the footwear.

 
With the goal of driving better business strategies, this project provides footwear companies with actionable insights, enabling them to fine-tune their marketing campaigns, optimize their pricing structures, and make data-driven decisions to improve profitability and customer satisfaction.

In this project, Excel was used for data cleaning and exploratory analysis.



## Step 1: Data Cleaning

### 1. Convert Price Column
- **Problem**: The `Price` column contains dollar signs (`$`) and is stored as text, making it unusable for numerical analysis.
- **Solution**:
  1. Removed the dollar sign (`$`) using the **Find and Replace** feature in Excel:
     - Press `Ctrl + H`, type `$` in the **Find what** box, leave the **Replace with** box empty, and click **Replace All**.
  2. Converted the `Price` column to a numerical format:
     - Selected the column, navigated to **Home > Number Format**, and changed it to `Number` or `Currency`.
- **Outcome**: The `Price` column is now in a numerical format suitable for analysis.

---

### 2. Standardize Column Names
- **Problem**: Column names were inconsistent (e.g., mixed casing, spaces, special characters).
- **Solution**:
  - Renamed all column headers to follow a consistent naming convention:
    - Converted all names to lowercase for uniformity.
    - Removed special characters.
- **Outcome**: Column names are standardized, making the dataset more readable and easier to use in formulas or code.

---

### 3. Check for Duplicates
- **Problem**: Duplicate rows can lead to inaccurate analysis.
- **Solution**:
  1. Selected the entire dataset in Excel.
  2. Used the **Remove Duplicates** feature:
     - Went to **Data > Remove Duplicates**, selected all columns, and clicked **OK**.
  3. Reviewed the results to ensure only duplicate rows were removed.
- **Outcome**: 82 Duplicate rows were removed, ensuring 924 unique entries in the dataset.

---

### 4. Handle Missing Data
- **Problem**: Missing values in the dataset can affect the accuracy of analysis.
- **Solution**:
  - Checked for missing values:
    - Used **Conditional Formatting** to highlight blanks:
      - **Home > Conditional Formatting > Highlight Cell Rules > Blanks**.
    - Filtered for blank cells in columns to locate them easily.
  - Addressed missing values:
    - Replaced missing numerical values (e.g., `Price`) with the column's average using:
      ```excel
      =AVERAGE(range)
      ```
    - Replaced missing categorical values with "Unknown" or "Not Available."
- **Outcome**: All missing values were handled appropriately, ensuring data completeness.

---

### Conclusion
After performing the above cleaning steps:
1. The dataset is free from inconsistencies in formatting or missing data.
2. It is now ready for exploratory data analysis and visualization.

---

### Cleaned Dataset
- **File Name**: `cleaned_dataset.xlsx`

  

## Step 2: Exploratory Data Analysis (EDA)

### 1. Visualize Brand Popularity
- **Objective**: Identify the most common brands in the dataset.
- **Steps**:
  - Created a bar chart using a Pivot Table to count occurrences of each brand.
  - Sorted the chart by count to display the most popular brands.
- **Outcome**:
  - The analysis shows that New Balance (98), Fila (97), and Nike/Asics (95) are the top brands in terms of frequency in the dataset.
  - These brands dominate the market and likely have higher customer demand than others.
  - [Sales Chart Visualization](./Sales_Analysis/brand_popularity.png)
---

### 2. Analyze Price Distribution
- **Objective**: Understand pricing trends across products.
- **Steps**:
  - Created a histogram to group prices into bins and identify clusters.
  - Used a box plot to highlight price spread, outliers, and median values.
- **Outcome**:
        Histogram and Box plot
    - The histogram groups prices into bins and reveals key insights:
        Most products fall within the price ranges of 67–81, indicating 
        popular mid-range price clusters. There is a significant drop in 
        products priced above 165, showing that higher-end products are 
        less common. Few outliers are visible in the highest price ranges 
        (249–263).
    - [Sales Chart Visualization](./Sales_Analysis/Price_distrubation.png)
      
    - The box plot highlights the following:
      
        Median Price: Centered within the range of approximately 90, indicating the most typical price point.
        Interquartile Range (IQR): The central 50% of the data falls between 70 and 130, showcasing the typical price 
        spread.
        Outlier: A single price exceeds 200, identifying a high-priced outlier.
       - [Sales Chart Visualization](./Sales_Analysis/Price_distrubation_box.png)
       
        

---

### 3. Gender-Based Preferences Analysis

- **Objective**:
Analyze preferences for product type and categories among gender groups to derive insights for marketing and inventory decisions.

- **Steps**:
   - Filtered data by `Gender` and analyzed preferences using Pivot Tables and charts.
   - Created a Pivot Table to analyze counts for each product type.
   - Generated a Clustered Bar Chart to visualize preferences by product type.

- **Outcome**:

   - **Men's Preference**:
      - **Running** shoes are the most popular product category for men.
      - **Casual** and **Skate** are also important but significantly less popular than running shoes.
      - [Sales Chart Visualization](./Sales_Analysis/Mens_product_preference.png)
     

   - **Women's Preference**
      - **Running** shoes are the most popular product category for women as well, though **Casual** shoes are a close 
          competitor.
      - Women also have a higher preference for **Skate** and **Walking** products compared to men.
      - [Sales Chart Visualization](./Sales_Analysis/women_gender_preference.png)

- **Actionable Recommendations**:
      1. **Personalized Marketing Campaigns**:
            - Based on the strong preference for Running shoes among both men and women, create targeted ads highlighting 
           the benefits for each gender. For men, focus on performance and endurance. For women, highlight the versatility and 
           fashion-forward aspects of running shoes, emphasizing stylish designs.
      2.**Optimize Inventory Allocation**:
           - Increase inventory in **Running** and **Casual** shoes based on high demand. For products with low demand
           (e.g.,**Hiking** and **Crossfit**), reduce stock levels or consider phasing them out.
      3. **Gender-Specific Campaigns**:  
            - Design marketing materials and campaigns that address the different preferences between men and women. For 
           women, campaigns could feature more **Casual** and **Skate** products with a fashion-forward angle. For men, 
           campaigns should focus on performance-based products like **Running** and **Casual** shoes, along with sporty, 
           functional messages.

---
### 4. Pricing Analysis by Gender and Brand

- **Objective**:
Analyze the average price (in USD) of products across different brands and gender groups to gain insights into pricing trends.

- **Steps**:
   - Calculated the average price of products for each brand, separated by gender.
   - Used pivot tables to organize the average prices of products by brand and gender.
   - Analyzed the pricing patterns to identify trends for each gender and brand.
  
- **Outcome**:
  - **Men's Products**:
     - On average, **Nike** and **Adidas** have the highest-priced products for men. **Vans** and **Skechers** offer more budget-friendly options for men.

  - **Women's Products**:
      - **Nike** and **Adidas** continue to lead with higher-priced products for women.**Skechers** and **Vans** are also 
 more affordable for women.
 - [Sales Chart Visualization](./Sales_Analysis/avg_price_distrubation.png)
  
- **Actionable Recommendations**:
   - **Price Differentiation Strategy**: Consider offering gender-specific discounts or promotions for budget-conscious consumers, particularly with brands like **Skechers** and **Vans**.
   - **Brand Positioning**: High-end brands such as **Nike** and **Adidas** can target a premium market by maintaining higher prices, while exploring potential product diversification at lower price points to cater to a wider customer base.


### 5. Material and Price Relationship
- **Objective**: Analyze the relationship between different materials used in product manufacturing and their average price 
    to uncover trends in material costs.
- **Steps**:
    - Filtered data to group products by their material types.
    - Calculated the average price for each material type using pivot tables.
    - Visualized the data using a bar chart to compare the average price of products by mat
- **Outcome**:[Sales Chart Visualization](./Sales_Analysis/material_price.png)
    - **Primeknit/Synthetic** has the highest average price at **$220**.
    - **Flyknit** follows closely with an average price of **$158.82**.
    - **Nylon** and **Canvas** are the least expensive materials, with average prices around **$63**.
    - **Mesh/Leather** shows a significantly higher average price of **$180**, indicating a premium for this material 
        combination. 

- **Actionable Recommendations**:
    - **Pricing Strategy**: Materials like **Primeknit** and **Flyknit** are associated with higher prices. Brands using 
        these materials could emphasize performance and premium design in their marketing campaigns.
    - **Cost Optimization**: **Nylon** and **Canvas** products are priced lower, suggesting opportunities for cost- 
        effective product lines targeting budget-conscious consumers.

## Conclusion: Strategic Recommendations Focused on Sales Optimization

   The **Footwear Sales Analytics** project offers valuable insights into customer buying behaviors and sales trends across different product categories and brands. By 
    analyzing sales data, we have identified Nike, New Balance, and Fila as the leading brands, with Running Shoes being the most popular category for both men and women.
    
   -Key recommendations to improve sales and optimize business strategy include: 
   
  **1. Enhanced Marketing Campaigns:** The strong demand for **Running Shoes** across both genders suggests the need for focused marketing campaigns. For men, promoting the 
       performance benefits, while for women, highlighting style and versatility could help increase sales further.
       
  **2. Inventory Planning:** **Running Shoes and Casual** Shoes should receive more inventory to meet demand, while underperforming categories like **Hiking** and 
      **Crossfit** may need to be de-prioritized or adjusted based on inventory turnover.
      
  **3. Pricing Optimization:** The analysis revealed a significant variation in prices by brand. High-end brands like **Nike** and **Adidas** should continue targeting the 
       premium market, while lower-priced options like **Skechers** and **Vans** could attract more budget-conscious customers.
       
  **4. Material Cost Strategy:** The analysis of material types and their associated prices suggests that products using high-performance materials such as **Primeknit** 
       and **Flyknit** are priced higher. These premium materials can be leveraged to position the brand as a high-quality, performance-driven footwear company.
       
Further work could include predictive analytics to forecast future sales trends, enabling better long-term planning.

