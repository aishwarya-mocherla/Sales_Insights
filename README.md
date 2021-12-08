
# **Sales Insights Using PowerBI**
# **This is bold text**
# About the project
I wanted to work on a project that would take me through the entire workflow of a real-time
 data analysis life cycle. I have tried my best to include every 
 day-to-day activity of a Data Analyst.

Ever since the pandemic has started, the market rates have kept 
changing dynamically, thus, making the process of data 
visualization and interpretation much harder. A one-stop platform
 of accurate, easy to understand insights on the subject and 
 activities is what I am willing to work on. This will not only 
 help the users get a clear big picture of the project, but will also help make the planning and decision
   making the process easier and faster.

# Problem Statement
Consider a trusted hardware company based in India, that supplies
its products throughout the country. The company has divided
 itself into 3 market regions, North, Central, and South. Each 
 region has its own regional manager.

Up until now, all the communication, discussions, and confirmations
 between the managing directors and the regional heads have been
  taking place verbally, which, for obvious reasons is not the
   most reliable way, especially to discuss numbers, trends and insights.
The data entry being done currently is also in the most
 primitive ways, by using various MS Excel files and spreadsheets
 . This is not only puzzling for the users to go through it for 
 the first time but is also very time-consuming. Not to mention,
  the amount of manual  work, which is a very important factor as
   more the manual work,
more the money spent.

Currently, the company works on a sales management system that 
is handled by the company's IT department. This software stores the required
data and all the other significant occurrences and records in a
database. This database is accessible to the data engineers
and data analysts of the company.

Thus, the **end product required** is a powerful dashboard that 
will help you track the revenue numbers and sales quantity numbers
 periodically. One must also be able to track down the revenue 
 breakdown regionally or product-wise. Another main objective that
  I am hoping to fulfill is to be open to suggestions, feedback
   and criticisms. Just like how it works in the real world, these
reports and dashboards created by data analysts are reviewed and 
tested by the various stakeholders such as the managing director,
 regional heads, investors, marketing leads, etc. This will not
  only help me improve my work but will also hel me understand what various
   authorities look for in such projects. 

# Objective
- Easily accessible, interactive, self-explanatory sales insights dashboards.
- Less arduous and time-consuming.
- Direct access to every required detail without having to coordinate with other people.
- Take data-driven decisions easily.

## The approach
The first step would be to set up a meeting with the stakeholders,
the IT Head, and the Data Department and brainstorm on the project. Here, we choose to let the **AIMS Grid** guide us.

**AIMS GRID** is a project management strategy that is divided into
 4 parts:

- **Aim/ Objective/ Purpose** : To unlock sales insights that were not visible before for the sales team, to reduce manual time spent in data gathering and interpretation.
- **Stakeholders/ Clients**
   - Marketing team
   - Sales Team
   - IT Department
   - Customer Service Team
   - Data and Analytics Team
- **End Result** : An automated dashboard providing quick and latest sales insights in order to support data-driven decision making.
- **Success Criteria** :
   - Best suitable dashboard
   - Cost to go down by a specific amount (10% in our case)
   - Reduce manual work
   - Increase revenue and sales by a certain amount (5% in our case)
     
One of the main purposes of the AIMS grid is to see the 
interdependence of the different factors mentioned above. This 
helps clarify any kind of task as all the work is now 
systematically broken down. It also helps present a project in a 
concise manner. Though, there is always a chance that the 
initial set success criteria and other factors might have to
 change depending on the stakeholders, clients, and various other
  constraints. This might lead to a significant change in the end
   result, which is what makes creating a fully flexible, adaptive
 , and interactive insight even more necessary.


# ETL (extract, transform, load)

## Extracting Data
In order to start the cleaning process, we first need to
import the data. Now Power BI lets us do it through 
many sources; Excel files and spreadsheets, CSV files, JSON Files,
 cloud platforms, and obviously the most popular means of storing
  data, through database systems such as IBM Dbl, SAP HANA, Oracle
  , SQL, etc. Today, we will be extracting our data from MySQL. 
  After collecting and importing the data from our desired
   database, we start with the data cleaning process.
   
![566f5789-e435-42f7-a2a0-70a96f07ffa9](https://user-images.githubusercontent.com/80768666/145198417-a68b1c74-c199-4125-bc72-36bdcf919d8c.jpg)


## The data 
The database consists of the following fields:
- **Sales customers**, which consists of the following data: 
    - Customer names
    - Customer codes
    - Customer type; where the customers are classified into their product of demand,brick&mortar or E-Commerce
- **Sales Markets**, which consists of the following data:
    - Market Codes
    - Market names
    - Zone (North, Central or South)
- **Sales Date**, which consists of the following data:
    - The exact date (dddd,d,mmmm,yyyy)
    - Cyclic date; the month and year when the new cycle starts (mmmm,yyyy)
    - Name of the month (mmmm)
    - The year (yyyy)
- **Sales Products**, which consists of the following data:
    - Product Codes
    - Product Type; whether the product has the company's own branding or if its a distributed product.
- **Sales Transactions**, which consists of the following data:
    - Product Codes
    - Customer Codes
    - Market Codes
    - Order Date (dd,mmmm,yyyy)
    - Sales Quantity; the number of products sold on that particular day
    - Sales Amount; the total revenue collected on that particular day
    - Currency 

All of this data can be accessed and viewed in the data section
of PowerBI desktop. 

![2ad568ff-28fa-46a6-b275-6e3f2affe8df](https://user-images.githubusercontent.com/80768666/145198801-17b49cb4-aeff-45eb-9b9c-828a93d0fe8b.jpg)

![3fdd7dd2-dc04-4487-be3d-53597b3dfba4](https://user-images.githubusercontent.com/80768666/145198853-bfaa9c34-a03a-4603-9af5-e3ad5fbd6360.jpg)


## Data Cleaning
Before we jump to creating the main report, or anything related 
to reading, studying, or analyzing our data, it is very important 
to ensure whether the data we have is completely optimized
and is in its best form for us to work with. This includes making sure
all the values are in the same unit, sign, and all the other 
factors are uniform. This ensures the smooth working of whatever tool you are using to perform your analysis and also in 
obtaining the right results and trends. Another advantage of 
doing this step is that the user gets to go through and 
understand the data at hand thoroughly before proceeding.

After connecting and importing the data, we now move on to
the PowerBI Query Editor to perform the required changes. 

![83d92b4e-d273-41ee-ae82-6a31bc2b8864](https://user-images.githubusercontent.com/80768666/145198987-bc2484dc-17c2-40d2-b2b9-06d649fea1de.jpg)


1. Markets table: As discussed earlier, the company associated with our project is based in India and is split across 3 regions.
But, the data also shows a few transactions taking place in regions
outside India such as New York and Paris.

![6630f32d-e8d2-4776-85dc-6bd6742228cc](https://user-images.githubusercontent.com/80768666/145199025-7d1e5beb-d28c-4b5b-984a-044c05287db5.jpg)


This wouldn't have been an issue but upon looking closely, it was observed that the number of
products sold is way higher than what the corresponding revenue shows. This clearly indicates that these are garbage 
values. Hence, we get rid of these from our data. We do this by 
deselecting all the rows which consist of blank spaces.

 ![afe6594f-1671-4f85-997b-2aff68680b84](https://user-images.githubusercontent.com/80768666/145199058-b2a7030d-c931-4d5b-bbca-54e2231154b1.jpg)

As you perform all these tasks, PowerBI keeps generating the 
queries generated, where you can make the rest of your changes depending on 
your needs.

![de9658cf-b831-48aa-9d5a-d280e378c8b0](https://user-images.githubusercontent.com/80768666/145199114-e7d618a9-23e1-49d3-9200-dae8d694d318.jpg)


*Every change or action made is recorded and displayed in 
the applied steps section*

![de321e2f-a20d-4977-807c-cfbb11553af5](https://user-images.githubusercontent.com/80768666/145199166-7cf6ab84-3247-4b44-a754-4d5c7439c34b.jpg)


#### Query generated:
    Table.SelectRows(sales_markets, each([zone] <> "))


2. Sales Transactions : A number of values in the sales_amount
 column are -1 and 0, which we consider as garbage values as the 
 number of goods sold are as high as 40 and 53
 
![c9d5a0d3-91a8-4223-999b-30e0246d50d8](https://user-images.githubusercontent.com/80768666/145199507-c2510ac6-71d2-46ef-89c6-1f34bdc455d6.jpg)


  So we deselect all the 0 and -1 values
  
![f307412f-f7b8-4df3-acc4-fc53aef3859c](https://user-images.githubusercontent.com/80768666/145199599-a034b815-323f-47bd-886d-adac12d32535.jpg)


![aa6f123c-46f8-4252-875b-8ee698429096](https://user-images.githubusercontent.com/80768666/145199626-2c8273f8-a82e-40f7-8bd9-ab07312d6546.jpg)

#### Query generated:
    Table.SelectRows(sales_transactions, each ([sales_amount] = -1 or [sales_amount] = 0))

3. Sales Transactions (USD to INR): There will be  times where we'll need to calculate the sum of the total revenue. 
 That can not be done directly as the USD values are different from the INR values. 

![d8be703a-104a-4971-8213-626bee2fbbf9](https://user-images.githubusercontent.com/80768666/145199672-86ab6cc6-72fc-4930-9b54-b81c6d9382a5.jpg)

 In order to fix this, we create a new column called the *normalized currency*,
 which will consist of all the values in INR. This will be a conditional column by using the if-else condition, 
 such that if the currency is USD, the corresponding
  sales value is  1, otherwise 0.
  
![7f51c64e-16bb-4243-a93c-83ed459a1756](https://user-images.githubusercontent.com/80768666/145199716-73e06fc2-ed20-49c4-8089-e5fb532ff8e6.jpg)

![9ea4f4cf-e414-4b06-8356-bae4d549be1a](https://user-images.githubusercontent.com/80768666/145202272-2632d5dc-e689-4c01-8fcf-f2f563d03967.jpg)



#### Query generated: 
    Table.AddColumn(#Removed Columns1", "Custom", each if [currency] = "USD" then 1 else 0)

Once the column is created, we can now improvise the 
column by making the required changes in the query. Since our
 aim is to convert the USD values into INR, we simply perform the
  following conversion in the query. 

#### Improvised Query : 
    Table.AddColumn(#Removed Columns1", "Custom", each if [currency] = "USD" then [sales_amount]*75 else [sales_amount])


Here, if the currency is USD, the value of the sales amount is converted value of INR and is added to the normalised_currency column but if the currency 
value is in INR itself, it is directly added to normalised_currency.

![7ea0153a-f92f-4b91-a5cb-f681a3125c7b](https://user-images.githubusercontent.com/80768666/145202665-f4333e3c-2a06-40ac-87a1-7aa91ccb5084.jpg)

![bc623b1e-2fdd-44b1-bb81-3b5a5b4407a5](https://user-images.githubusercontent.com/80768666/145202686-12e68811-d56d-4edd-a8e9-c68391a99326.jpg)


Now we have a normalized currency column where all the values are in INR

![b76ad356-bd37-4aea-8d23-7bc5c0c1fe78](https://user-images.githubusercontent.com/80768666/145202727-e3e160b6-63ee-4e7b-8921-650ac6344417.jpg)


**With this, we complete ETL**

# Data Modeling
A data model is a way of establishing relationships between the various fields 
in the provided data. As mentioned before, PowerBI generates default data models
but also gives us the liberty to make changes of our own. 

![aa314583-39bf-4948-b715-7732f6158846](https://user-images.githubusercontent.com/80768666/145202765-e4499a01-3a8f-4fc3-b509-316b754e041b.jpg)


Here, it has established a default relationship between the customers, transactions, and products. In addition to this, we create a relationship between date and markets 
as well. 

![86f70372-3fa8-4f36-a182-ce4b421b1c11](https://user-images.githubusercontent.com/80768666/145202805-f320f77e-1ce0-4e73-a878-9c33615574b7.jpg)

![48df467d-faa7-4b8b-9041-ecad050f6b24](https://user-images.githubusercontent.com/80768666/145202902-09d92d62-fecc-4598-a5ab-ea8537727520.jpg)


*Most of the time, the reason PowerBI is not able to establish a few obvious relationships
is because of the minor difference in data labels. This is an issue that has to be
reported to and handled by the IT department.*

# The Dashboard / Report
Based on the stakeholder requirements, we build the necessary visualizations
in our report using various statistical models.

In my report, I have built the following visualizations and graphs:

- A summation of the total revenue earned and the number of products sold by the company to date.
- A stacked bar chart of revenue based on individual customers.
- A stacked bar chart of the number of products sold based on individual customers. 
- A line chart displaying the revenue trends and sales quantity trends over the years 2017-2020.
- A stacked column chart showing the revenue gained by each product type regionally.
- A stacked bar chart of revenue by product type.
- Two separate bar charts showing the revenue gained by the top five and bottom five sold products.

All the above mentioned charts are completely interactive according to your desired
zone, customer, year, month, or product type.

*You can find the file to this dashboard along with this README file in my Sales_insights repository*

# Feedback and reviews
To complete my project, I consulted a few of my friends, seniors, and a professional BI developer to receive all kinds of feedback so I could improve my work. Here
my consultants played the role of various stakeholders. Given below are the issues they pointed out.

- Visually, the dashboard looked jam-packed, which made it difficult for the viewer to interpret the report unless they spent a good amount of time studying it.
- The report does not show values based on the cities. 
*The new improvised report by the name "improvised_dashboard" can be found in the same repository as this README file.*
