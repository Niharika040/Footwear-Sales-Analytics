# Footwear-Sales-Analytics

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
### 4.Pricing Analysis by Gender and Brand

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

- **Actionable Recommendations**:
   - **Price Differentiation Strategy**: Consider offering gender-specific discounts or promotions for budget-conscious consumers, particularly with brands like **Skechers** and **Vans**.
   - **Brand Positioning**: High-end brands such as **Nike** and **Adidas** can target a premium market by maintaining higher prices, while exploring potential product diversification at lower price points to cater to a wider customer base.


### 4. Material and Price Relationship
- **Objective**: Understand how material types influence pricing.
- **Steps**:
  - Summarized trends using a bar chart of average prices for each material.

- **File Name**: `EDA.xlsx`




