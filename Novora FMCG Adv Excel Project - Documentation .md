# **Novora Mart Supply Chain Performance Analysis**

### Problem Statement

Novora Mart is a growing FMCG manufacturer headquartered in Gujarat, India. It currently operates in Surat, Ahmedabad, and Vadodara and plans to expand to other metro and Tier-1 cities within the next two years.

However, Novora Mart has been facing customer dissatisfaction as key clients have not renewed their annual contracts due to service issues. Specifically, some essential products were either not delivered on time or not delivered in full over a continued period, impacting customer service quality.

To address this, the Supply Chain team needs to track key service-level metrics daily, ensuring swift response to service issues before expansion. These key metrics include ‘On-time delivery (OT) %,’ ‘In-full delivery (IF) %,’ and ‘On-time in full (OTIF) %’ of customer orders against the target service levels.

* * *

### Data Source

The data used for this analysis comes from multiple sources:

*   **Dimension Tables:** Customers, Date, Products, Target Orders
*   **Fact Tables:** Order Lines, Order Aggregates

* * *

### Methodology & Workflow

The analysis was conducted in multiple steps to ensure comprehensive coverage of all discrepancies:

#### Step 1: Data Cleaning and Preparation

*   Imported and consolidated all datasets using Power Query.
*   Standardized column names and formats.
*   Removed duplicates and addressed missing values.

#### Step 2: KPI Calculation & Metrics Definition

The following key performance indicators (KPIs) were calculated:

1.  **Total Order Lines**

    *   **Definition:** The total number of order lines processed.
    *   **Formula:** Sum of all order lines.
    *   **Excel Function:** `SUM(range)`
2.  **Line Fill Rate (LIFR) %**

    *   **Definition:** The percentage of order lines fulfilled out of the total ordered.
    *   **Formula:** (Number of fulfilled order lines / Total order lines) \* 100
    *   **Excel Function:** `SUMIF(range, criteria, sum_range) / SUM(range) * 100`
3.  **Volume Fill Rate (VOFR) %**

    *   **Definition:** The percentage of order quantity delivered out of the total ordered quantity.
    *   **Formula:** (Total delivered quantity / Total ordered quantity) \* 100
    *   **Excel Function:** `SUM(range) / SUM(range) * 100`
4.  **Total Orders**

    *   **Definition:** The count of all unique orders processed.
    *   **Formula:** Count of unique order IDs.
    *   **Excel Function:** `COUNT(range)`
5.  **On-time Delivery (OT) %**

    *   **Definition:** The percentage of orders delivered within the expected delivery time.
    *   **Formula:** (On-time delivered orders / Total orders) \* 100
    *   **Excel Function:** `SUMIF(range, criteria, sum_range) / SUM(range) * 100`
6.  **In-full Delivery (IF) %**

    *   **Definition:** The percentage of orders delivered with full quantities as per the order request.
    *   **Formula:** (Fully delivered orders / Total orders) \* 100
    *   **Excel Function:** `SUMIF(range, criteria, sum_range) / SUM(range) * 100`
7.  **On-time In-full (OTIF) %**

    *   **Definition:** The percentage of orders that were both delivered on time and in full.
    *   **Formula:** (On-time and in-full delivered orders / Total orders) \* 100
    *   **Excel Function:** `SUMPRODUCT((range1=criteria)*(range2=criteria)) / SUM(range) * 100`
8.  **Target Metrics:**

    *   **On-Time Target %** - The expected on-time delivery percentage.
    *   **In-Full Target %** - The expected in-full delivery percentage.
    *   **On-Time In-Full (OTIF) Target %** - The expected OTIF percentage.


* * *

### Analysis & Insights

1.  **City-wise Performance:**

    *   Ahmedabad has the highest In-Full % (67%), followed by Surat (66%) and Vadodara (63%).
    *   Surat leads in On-Time % (73%), followed by Ahmedabad (70%) and Vadodara (69%).
    *   OTIF % is highest in Surat (50%), followed by Ahmedabad (48%) and Vadodara (45%).
2.  **Customer-wise Performance:**

    *   Several customers have significantly underperformed in IF %, OT %, and OTIF %.
    *   **Worst IF % Customers:** Vijay Stores (29.8% vs. 67% target), CoolBlue (29.19% vs. 65% target), Lotus Mart (30% vs. 66% target), among others.
    *   **Worst OT % Customers:** Multiple customers achieving <30% vs. a target of 75%+.
    *   **Worst OTIF % Customers:** Many customers performing significantly below the required targets.
    *   **VOFR %:** All customers maintain a VOFR % above 90%.
    *   **LIFR %:** Some customers have LIFR % below 30%.
3.  **Product Performance:**

    *   All products have an LIFR % above 60%.
    *   All products maintain a VOFR % above 90%.

* * *

### Business Recommendations

Based on the analysis, the following actions are recommended:

1.  **Improve Delivery Planning & Logistics**

    *   Implement route optimization techniques.
    *   Strengthen partnerships with logistics providers to enhance delivery reliability.
2.  **Customer-Specific Service Improvement Plans**

    *   Prioritize key customers with the lowest service levels for immediate corrective actions.
    *   Offer customized delivery windows to improve OT and IF performance.
3.  **Warehouse & Inventory Optimization**

    *   Invest in predictive inventory management tools to ensure product availability.
    *   Establish real-time tracking mechanisms for proactive issue resolution.
4.  **Performance-Based Supplier & Transport Contracts**

    *   Link supplier payments and transport contracts to service level adherence.
    *   Set up penalty/reward structures based on OT, IF, and OTIF targets.
5.  **Continuous Monitoring & Automation**

    *   Automate daily KPI tracking for proactive decision-making.
    *   Use alerts for service-level breaches to enable quick interventions.

By implementing these recommendations, Novora Mart can significantly enhance its supply chain efficiency, customer satisfaction, and readiness for expansion into new markets.

* * *

