# The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot.

## In this project, I'll walk over every step of the process I went through to develop my solution and gather as many ideas as possible to use Excel Power Pivot, KPIs, and Excel Formular to create an excellent solution for the grocery store analysis project.


![Gocery store](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/f55a646e-45e0-4b0b-95dd-329bf5fea8de)



# The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot.

    1. Add Power Pivot to your Menu bar.
    2. Click on Manage.

![1659134662889](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/5f85e300-b13e-4b56-8122-ebff076db18c)
    3. Create a data model and establish a relationship with the three files.

    4. A new window opens. On the Home Click on Get Data from other sources.

    5. Scroll down and click Excel File.

![1659134662956](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/58329647-0f92-495e-b158-48feb1aaa7e9)

    6. On the next page, click on browse to choose you file.

![1659134663018](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/ed009164-f89b-400f-a568-7364119feaf0)

    7. Get the Customer file data and check Use first row as column headers. Click on Finish.

    8. To bring the two other files, repeat the steps above to bring in both the Order and Cookie Type files.


## Now we want to create relationship between the three files.

  1. Click on Diagram View

![1659134663085](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/c1cbec74-a12a-4ef5-a2b1-9d9ad01dab20)

 2. Click, drag, and drop the **Customer ID** in the **Orders table** on the **Customer ID** in the **Customer table.**

 3.  Repeat the step no. 10 for **Product** in **Orders table** on Cookie Type in **Cookies Type table.**

![1659134663319](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/65c313c1-2de9-4e61-8016-4d9c5277bfc8)

4. Click on Data View beside Diagram View to return to your data.


## Calculate the revenue made per order.

     1. In the Order tab, add three new columns called Revenue, Cost and Profit.
     2. To calculate the Revenue, click the first cell under Revenue, go to the formula bar and type **=RELATED(‘Cookie Type’[Revenue Per Cookie]) * Orders[Units Sold]** . Hit Enter.
     3. To calculate the Cost, click the first cell under Cost, go to the formula bar and type **=RELATED(‘Cookie Type’[Cost Per Cookie]) * Orders[Units Sold]**
     4. To calculate Profit, click the first cell under Profit, go to the formular bar and type **Orders[Revenue] – Orders[Cost]**


## Calculate Total Number of Customers

         1. Click on Measure

![1659134663641](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/607fa7d5-43a3-4da8-8de7-d8267045b513)

 2. Choose Customer Table, name the measure as Total Number of Customers.

![1659134663918](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/54fc2bf2-3c12-4dfd-b1ec-1ca028dfd581)

  3. In the formula space, type **=DISTINCTCOUNT([Customer ID])** and click OK.

  4. Click on Manage and navigate to the Customers tab. Below the table, you will see Total Number of Customers = 5

![1659134664225](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/c12b630a-4284-4477-a4fa-428f406c1f32)

## Calculate Total Profit using a Measure

   1. Click under the previous measure and type in the formular bar **=SUM(Orders[Profit])** and hit Enter.
   2. Rename the measure to **Total Profit** and format it to currency.

![1659134664505](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/bf9f4b74-f038-4d5a-985b-1498a9f81bac)

## Calculate Average Profit per Customer

    1. Click under the Total Profit and type in the formular bar **=[Total Profit]/[Total number of customers]** and hit Enter.
    2. Rename it to **Average Profit per Customer** and format it to currency.


## Calculate number of Orders each Customer has placed

    1. Close Power Pivot
    2. Go to Insert tab and click on **Pivot Tables.** Choose **New Worksheet.**
    3. Expand the **Customer table** on the far right under **PivotTable fields** and drag the **name** column into Rows. Do same for the **Order table** and drag **Order ID** into **Values.**
    4. Click the drop-down arrow on **Order ID** and go to **Value Field settings.** Change the **Sum** to **Count.**

![1659134664847](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/b34243e3-22cf-4d41-a604-f3597fd6a06c)

## Calculate Profit made on each Customer

    1. Click on **Customer table** and drag our **Total Profit** measure into the Values field.
    2. Click on **Power Pivot** and select **KPIs** just beside Measures. Click on **New KPI**
    3. Choose **Total Profit** as KPI base field (value)
    4. Make the **Absolute value** 600000 and click **OK.**

![1659134665117](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/c00fee94-b121-4e27-b26c-7229cfe216b3)

   5. A new column named **Total Profit Status** should be added.

   6. Go to the **Customers table** under **PivotTable fields** and scroll down until you see a new icon with traffic symbol  named **Total Profit.**

   7. Uncheck **fx Value (Total Profit), Goal** and Status and recheck only Status. You should see the values under **Total Profit Status** changed into color scale.
      
![1659134665449](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/9be8e3e0-66e8-473b-8a5c-11a893220d33)

  8. Check both the Goal and fx Value (Total Profit).
     
## Visualize our Results

        1. Go to PivotChart Analyze and click on Pivot Chart
        2. Select Pie Chart and click OK

![1659134665732](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/77da64eb-498c-4577-bb65-4304d1b4e99d)


    3. Add a slicer by clicking Insert Slicer under the PivotTable Analyze

    4. The Slicers should be Cookie Type and Date.

![1659134666062](https://github.com/justinjabo250/The-Grocery-store-analysis-project-makes-use-of-Excel-Formular-KPIs-and-Power-Pivot./assets/115732734/4a540582-ef13-4e81-889e-86d2343c6098)
