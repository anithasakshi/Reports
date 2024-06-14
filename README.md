# Sales-Report

### Report Link : https://app.powerbi.com/groups/me/reports/078f5249-d926-4074-bdca-c6b8d3addcce/7023529ec20cda426568?experience=power-bi

## Abstract :

This Report gives a detailed Analysis Of Tax Implementation in present and past orders of given Cities. It Helps the suppliers to know the tax implemented in each cities. We can also get to know the Total Sales of each Consumer the supplier supplies to, with including and excluding the tax amount for each Consumer within the City. The Report contains the Consumer(s) under each City. This gives a Descriptive analysis on the Sales of Supplier.

This Report helps to Visualize the Total Sales of each City Including Tax and Excluding Tax with Tax Percentage.

The Tax Implemented in Each City is Different such as Alanta imposes 5.8%, Miami imposes 6.5%, Chicago imposes 4.8%.

### Steps followed  : 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : In the report view, under the view tab, theme was selected.
- Step 5 : Visual filters (Slicers) were added for Two fields named "Customer/Organization", "Cities".
- Step 6 : Cards were added in each page to show the total sales of each city with including and excluding the tax, the Count of number of order in each City. Card added in the Overview page represent Currency used, sales person code and email id of each Organization(consumer).
           Using the page level filer from filters pane, basic filtering was used and Cities which is not being visualized here were unselected.
- Step 7: The Line Chart was also added to each page of the report design area representing the Sum of Including and Excluding Tax Using present and past orders of the Organization are the Consumers here for City. Here the the each Line chart contains the the trend line of total sales of including and excluding amount according to the tax.
    The Pie Chart in each city page represent the status of payment.
- Step 8 : The Multicard chart is added to pages which contains the visualization of each City to show the Details of Orders placed in each Date.  
- Step 9 : The Pie Chart Visual is added to Overview page which shows the Count of No of Order in each City.
- Step 10 : The Tree Map visual is added to overview page to show the ranking of each organization(Consumer) based of the Tax Paid.
Snap of the Page 1:
![sales-page 1](https://github.com/anithasakshi/Reports/assets/114795941/918c043d-d9a2-4375-8ca2-50bb12fcb915)

Snap of the TreeMap Visual: 

![treemap-page1](https://github.com/anithasakshi/Reports/assets/114795941/0350d44d-dbb9-436c-88b3-0b28aa0b01aa)

- Step 11 : Measure  was created in which, Tax Percentage was applied to each City page Using DAX.

for creating new Measure following DAX expression was written;
       
        PercentageValue = DIVIDE(Sum(salesInvoices[Sum of totalTaxAmount]),SUM(salesInvoices[Sum of totalAmountIncludingTax]),0)

Snap of new Measure for Tax (only for Atlanta City)

![altanta tax percent](https://github.com/anithasakshi/Reports/assets/114795941/9d768937-b5b2-4721-b336-8d344d1ffa71)
        
- Step 12 : New measure was created to find total amount of Receivables from Consumer over all periods.

Following DAX expression was written for the same,
        
        Total_Receivables = SUM(agedAccountsReceivables[Sum of period1Amount])+
        SUM(agedAccountsReceivables[Sum of period2Amount])+
        SUM(agedAccountsReceivables[Sum of period3Amount])
        
The Snap of Card Visual representing total amount of receivables:

![receivables_total](https://github.com/anithasakshi/Reports/assets/114795941/1232259a-1abc-4221-8330-1545f6927805)

- Step 13 : The Table was created in receivables page to represent the organization(consumer) name, their Id and their Balance amount to pay to the supplier.

 The Snap of the Table: 
 
 ![table-receivables](https://github.com/anithasakshi/Reports/assets/114795941/b7ef28e3-6057-44d5-a0ae-8066ab6bd746)

 
 - Step 14 : New measure was created to calculate total sales amount of the present orders and Past orders of the Organization(consumers), separate DAX is used for Including and excluding tax sales amounts.
 
 Following DAX expression was written to find total distance,
 
         Total_Sales_By_City = SUM(salesInvoices[Sum of totalAmountIncludingTax])+ SUM(salesOrders[Sum of totalAmountIncludingTax])

         Total_Sales_By_City_EX = SUM(salesInvoices[Sum of totalAmountExcludingTax])+ SUM(salesOrders[Sum of totalAmountExcludingTax])
    
 A card visual was used to represent this total Sales(Including Tax-Atlanta):
 
  ![including_tax_atlanta](https://github.com/anithasakshi/Reports/assets/114795941/98687d27-cce3-4e8c-afc0-88187476d892)

A card visual was used to represent this total Sales(Excluding Tax-Atlanta):
![excluding tax-altanta](https://github.com/anithasakshi/Reports/assets/114795941/0e8e486b-26b3-4fb8-a40d-70c9f8d068eb)

 - Step 15 : Buttons are added to Overview Page with Drill Through Action for each City.
 The Snap of the Buttons:
 
 ![buttons-page1](https://github.com/anithasakshi/Reports/assets/114795941/04c2ca9b-31ba-4645-a06b-80de2f1dd6f4)

 - Step 16 : The report was then published to Power BI Service.
 
 
![publish-sales](https://github.com/anithasakshi/Reports/assets/114795941/404666dd-b6ea-4fd8-b149-8ff4bd6713dd)

![power-bi-service-report-page](https://github.com/anithasakshi/Reports/assets/114795941/c9cf11c9-be6b-4c66-84aa-9dc04267ba5e)


# Insights:

A report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the Report:

- Count of Orders in each city: 
   - Atlanta - 108
   - Miami - 61
   - Chicago - 52

- The School Of Fine Arts Organization(Consumer) pays the highest Tax amount.

- Currency Used - USD

- Postal Code of each City :
   - Atlanta - 31772
   - Miami - 61236
   - Chicago - 37125
- Total sales Including Tax :
   - Atlanta - 450.20K
   - Miami - 254.20K
   - Chicago - 63K

- Total sales Excluding Tax :
   - Atlanta - 424.03K
   - Miami - 237.57K
   - Chicago - 59.67K

- Total tax amount :
   - Atlanta - 24.97K
   - Miami - 16.27K
   - Chicago - 2.98K

- Tax Percentage : 
    - Atlanta - 5.8%
    - Miami -  6.5%
    - Chicago - 4.8%

- Count of each Status of Each Order in Each City :-
  - Atlanta:
    - Paid - 100
    - Draft - 4 
    - Open -  4 
  - Miami:
    - Paid - 53
    - Draft - 6
    - Open -  2
  - Chicago:
    - Paid - 48
    - Draft - 3 
    - Open -  1
- The Customer Number of each Consumer(organization):
  - Adatum Corporation - 10000
  - Trey Research - 20000
  - School of Fine Art - 30000
  - Alpine Ski House - 40000
  - Relecloud - 50000
- Receivable Amount With respect to each City : 
   - Atlanta - 13.15K
   - Miami - 53.83K
   - Chicago - 3.04K 
- Total Receivables - 70.02K .

  (This is the One of the Power BI challenges)


