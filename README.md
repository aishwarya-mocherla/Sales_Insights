
# **Sales Insights**
## About the project
I wanted to work on a project that would take me through the entire workflow of a real-time
 data analysis life cycle. I have tried my best to include every 
 day-to-day activity of a Data Analyst.

Ever since the pandemic has started, the market rates have kept 
changing dynamically, thus, making the process of data 
visualization and interpretation much harder. A one stop platform
 of accurate, easy to understand insights on the subject and 
 activities is what I am willing to work on. This will not only 
 help the users get a clear big picture and answer to what they are
  looking for, but will also help make the planning and decision
   making process easier and faster.

## Problem Statement
Consider a trusted hardware company based in India, that supplies
its products through out the country. The company has divided
 itself into 3 market regions, North, Central and South. Each 
 region has ts own regional manager.

Up until now, all the communication, discussions and confirmations
 between the managing directors and the regional heads have been
  taking place verbally, which for obvious reasons is not the
   most reliable way, especially to discuss numbers and insights.
The data entry being done currently is also being done in the most
 primitave ways, by using various MS Excel files and spreadsheets
 . This is not only puzzling for the users to go through it for 
 the first time but is also very time consuming. Not to mention,
  the amount of manual  work, which is a very important factor as
   more the manual work,
more the money spent.

Currently, the company works on a sales management system that 
is handles bt the IT depertment. This software stores the required
data and all the other significant occourancesand records in a
data base.This data base is accisible to the data engineers
and data analysists of the company.

Thus, the **end product required** is a powerful dashboard that 
will help you track the revenue numbers and sales quantity numbers
 periodically. One must also be able to track down the revenue 
 breakdown regionally or product-wise. Anther main objective that
  I am hoping to fullfill is to be open to suggestions, reedbacks
   and critisizms. Just like how it works in the real world, these
reporst and dahsboards created by data analystsare reviewd and 
tested by the various stakeholders such as the managing director,
 regional heads, inverstors, marketing leads etc.This will not
  only help me improve my work but will also as to what various
   authorities look for in such projects. 

# Objective
- Easily accesible, interactive, self explainatory sales insights dashboards.
- Less arduous and time consuming.
- Direct access to every required detail without having to coordinate with other people.
- Take data driven decsions easily.

## The approach
The first step would be to set up a meeting with the stakeholders,
the IT Head and the Data Department and brainstorm on the project. Here, we choose to let the **Aims Grid** gude us.

**AIMS GRID** is a project management strategy that is divided into
 4 parts:

- **Aim/ Objective/ Purpose** : To unlock sales insights that were not visible before for the sales team , to reduse manual time spent in data gathering and interpretation.
- **Stakeholders/ Clients** : Marketing team, Sales Team, IT Department, Customer Service Team, Data and Analytics Team
- **Stakeholders/ Clients**
   - Marketing team
   - Sales Team
   - IT Department
   - Customer Service Team
   - Data and Analytics Team
- **End Result** : An automated dashboard providing quick and latest sales insights in order to support data driven decsion making.
- **Success Criteria** :
   - Best suitable dashboard
   - Cost to go down by a specific amount (10% in our case)
   - Reduce manual work
   - Increase revenue and sales by a certain amount (5% in our case)
     
One of the main purposes of the AIMS grid is to see the 
interdependence of the different factors mentioned above. This 
helps clarify any kind of task because all the work is now 
systematically broken down. It also helps present a project in a 
consise manner. Though, there is always a chance that the 
initially set success criteria and other factors might have to
 change depending on the stakeholdrs, clients, and various other
  consstrains. This might lead to a significant change in the end
   result. This is what makes creating a fully fexible, adaptive
 and interactive insight even more necessary.


# ETL (extract, transform, load)

## Extracting Data
In order to start the cleaning process, we first need to
import the data. Now Power BI, like mentioned, lets us do through 
many sources. Excel files and soreadsheets, CSV files, JSON Files,
 cloud platforms, and obviously te most popular means of storing
  data, through database systems such as IBM Dbl, SAP HANA, Oracle
  , SQL etc. Today, we will be extracting our data from MySQL. 
  After collecting adn importing the data from our desired
   database, we start with the data cleaning process.

**_insert get data screenshot_**

# The data 
The data base consists of the following fields:
- **Sales customers**, which consists thefollowing data: 
    - Customer names
    - customer codes
    - customer type, where the custores are classified into their product of demand,brick&mortar or E-Commerce
- **Sales Markets**, which consists of the following data:
    - Market Codes
    - Market names
    - Zone (North, Central or South)
- **Sales Date**, which consists of the following data:
    - The exact date (dddd,d,mmmm,yyyy)
    - Cyclic date, the month and year when the new cycle starts (mmmm,yyyy)
    - name of the month (mmmm)
    - the year (yyyy)
- **Sales Products**, which consists of the following data:
    - Product Codes
    - Product Type, whether the product has the companys own branding or fir its a distributed product.
- **Sales Transactions**, which consists of the following data:
    - Product Codes
    - Customer Codes
    - Market Codes
    - Order Date (dd,mmmm,yyyy)
    - Sales Quantity , the number of products sold on that particular day
    - Sales Amount , the total revenue collected on that particular day
    - Currency 

All of this data can be accessed and viewed in the data section
of PowerBI desktop. 

**_screenshot of highlighted data section**
**_screenshot of various fields on the right(highlight it) + add full screenshot with table_**

# Data Cleaning and ETL 
Before we jump to creating the main report, or anything related 
to reading, studying or analysing out data, it is very important 
to ensure whther th data data we have is completely optimised
and is in its best form for us to use. This includes making sure
all the values are in the same unit, sign, and all the other 
factors re uniform. This ensures the smooth wroking of what
ever tool you are using to perform your analysis and also in 
obtaining the right results and trends. Another advantage of 
doing this step isthat the user gets to go through and 
understand the data in hand thoroughly before proceeding.

After connecting and importing the data, we now move on to
the PowerBI Query Editor perform the required changes. 

**_picture of opening power query editor_**

1. Markets table : As discussed earlier, the company associated 
with our project is based in india and is split across 3 regions.
But, the data also shows a few transactions taking place in regions
outside india such as New York and Paris.

**_picture of before_**

This wouldnt have been an but if you look closely, the number of
products soled are way higher than what the corresponding revenue 
indiates. This clearly indicates that these are garbage 
values.Hence, we get rid of these from out data. We do this by 
deselecting all the rows which onsists of blank spaces.
 
**_pichture of deselcting_**

As you perform all these tasks, PowerBI keeps generating the 
queries, where you can make the rest of your changes depending on 
your needs.

**_final new picture + picture of query generated_**

*Every change or action made is recorded and displayed in 
the applied steps section*
**_picture of applied steps section_**

#### Query generated:
    Table.SelectRows(sales_markets, each([zone] <> "))


2. Sales Transactions : A number of values in the sales_amount
 column are -1 and 0.which we consider as garbage values as the 
 number of goods sold are as high as 40 and 53
 
 **_picture of 0 and -1, highlight amount and quantity_**

  So we deselect all the 0 and -1 values

**_picture of deselceting rows with 0 and -1_**

**_final picture_**

#### Query generated:
    Table.SelectRows(sales_transactions, each ([sales_amount] = -1 or [sales_amount] = 0))

3. Sales Transactions (USD to INR): There will be
 times where we'll need to calculate the sum of the total revenue. 
 That can not be done directly as the USD values are different from the INR values. 


 **_currency in usd screenshot_**

 In order fix this, we create a new column called the *normalised currency*,
 which will consist of all the values in INR.

 We create a conditional column and by using the if-else condition, 
 we create a column such that if the currency is USD, the curresponding
  sales value is  1 to INR, otherwise 0

**_creation of new conditional column_**
**_screenshot of newly generated column_**

#### Query generated: 
    Table.AddColumn(#Removed Columns1", "Custom", each if [currency] = "USD" then 1 else 0)

Once the column is created, we can now improvise the 
column by making the required changes in the query. Since our
 aim is the convert the USD values into INR,we simply perform the
  following conversion in the query. 

#### Improvised Query : 
    Table.AddColumn(#Removed Columns1", "Custom", each if [currency] = "USD" then [sales_amount]*75 else [sales_amount])


Here, if the currency value is USD, the value of the sales amount is 
converted value of INR and is added to the normalised_currency column nd if the currency 
value is in INR itself, it is directly added to the new column

**_picture of orignal query_**
**_picture of highlited changes in query_**

now this gives us a normalised currency column where all the values are in INR

**_new column photo_**

With this, we complete the process of data cleaning and ETL















 

                  
            