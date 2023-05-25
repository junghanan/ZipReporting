# ZipReporting

**A Purpose of the Project**
This project was initiated because a previous process involved manual data pulls using OData with Excel and utilized Excel functions (SUMIFS and XLOOKUP) to calculate the amount of sales that needed to be reported to manufacturers.

**SQL/Automation**
1. Utilized SQL Server (involved writing SQL codes: Purchase_data & Sales_data) to instantly retrieve data. Pulling data with OData took more than one hour and caused crashes multiple times during the data pull.

2. Used KNIME (<a href="https://www.knime.com/software-overview">Analytics Platform</a>) to automate calculations that determine which sales need to be reported to the manufacturers each month and create final reports with different formatting automatically. 

3. Created data archives on Excel with timestamps (no internal or cloud storage options were available) to track previously reported sales data, ensuring that previously reported sales would not be counted for the current month.

**Logic** 
1. Purchase data was pulled via SQL server. The data needs to be pulled until the month for which the report is being run to compare the total number of units purchased per SKU.

2. Sales data was pulled via SQL server (data range only applies to the report month).

3. Filtered Sales data to include SKUs that were purchased only by executing an inner join using SKU as a primary key with the purchase data.

4. Used the equation: Sales qty - Purchase qty - Reported qty.

5. If the final number is equal to or greater than 0, it should be reported.

**Results**

1. Automated 2 processes: Zip Reporting for US and Canada (2 different companies).

2. Reduced 16 hours of work to 15 minutes every month. 

3. All reports were generated with 100% accuracy ((manually validated multiple times to ensure proper automation). 

**Screenshot of KNIME Workflow**

<img width="1176" alt="Screen Shot 2023-05-25 at 12 36 18 PM" src="https://github.com/junghanan/ZipReporting/assets/73127589/a06950bd-52b1-4767-bd28-e174784a6ceb">
