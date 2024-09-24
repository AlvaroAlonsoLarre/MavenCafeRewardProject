# Maven Cafe Reward Project

![Power Bi](https://img.shields.io/badge/power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![EXCEL](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

![Report](https://raw.githubusercontent.com/AlvaroAlonsoLarre/MavenCafeRewardProject/refs/heads/main/ImagenPantallas.png)

📊 **Link to the Report(https://app.powerbi.com/reportEmbed?reportId=272d0377-9a59-4b8a-9884-4a241551b632&autoAuth=true&ctid=b737ad62-dbe1-4e32-9914-a203a54d243e)**

## Foreword
After running a test by sending different combinations of promotional offers to existing rewards members, Maven Cafe needs to develop future marketing strategies. Using the 30-day period test I analysed the dataset to create a report that shows the conclusions and the proposal for the company. 

## Dataset
The dataset consists of three csv files:
  -	Customers: (Dimension table) – Personal information for each Maven Cafe member.
  -	Offers: (Dimension Table) – Details about the offer sent to customers during the test.
  -	Events: (Fact table) –Customer activity information related to the interaction to the offers and their transactions in the cafe.

## Data Prepare
Dataset was prepared in such a way that the no relevant or no coherent information was filtered from the tables:
  -	Customers filters
    o	Customers with null values for gender & age & income fields were deleted.
    o	118 y.o. customers were assumed as mistakes and they were not considered in the age segment analysis.
    o	Customer with “null” value just in gender field were no considered in the gender segment analysis.
  -	Event filters
    o	I assumed that the goal of the offers is to attack customers to buy. That is way I filtered out all the offers that had been completed before being viewed and/or being received. I also filtered out all the offers that appear as viewed before being received.
    o	Offers completed during a transaction where the amount is less than the “difficulty” of the offer were deleted.
    o	 When two or more completed offers appear in the same transaction, all the offers were deleted. I can not be sure which offer is correct or if all of them are wrong.

## Data Process
After filtering, it was necessary to modify the tables to shed some light on the information provided and be able to analyse in more detail.
  -	Customers table
    o	The dates of the column “became_memeber_on” were compared to the latest date of the same column. The difference between these dates were round down to a year.  Thus, the values of this column were grouped by 3 different values depending on the years of membership: “<1”, “1-2” and ”>2”.
    o	“age” column was grouped in 4 different study segments: “18 -24”, “25-44”, “45-64” and “>65” y.o.
    o	“income” column was also grouped in 4 different study segments: “<45”, “45-74”, “75-95” and “>95” thousand $ per year.
    o	In order to make the report easier to visualise, the different “channel” names were shortened. Just the first letter of each channel was use in the visualization.
  -	Events table
    o	“value” column was divided in three different columns: “offer id”, “amount” and “reward”. 
    o	Each completed offer was associated with the amount of the transaction where the offer was used.  These amounts were added to the completed offer row.
    o	A new column called “time lapse” was created. In this column, it was calculated the number of hours from an offer was received to the offer was viewed and completed.

## Data Analysis
During the data analysis, I created many calculated columns, dynamic tables and visualizations that allowed me to compare and study the dataset.

I started calculating the average customer profile and I compared the different customer segments to three different parameters: nº transactions/customer, amount/transaction and amount/customer. I also compered the customer segments to the total amount spent and the total number of transactions.

The offers were also analysed. Firstly, I analysed the influence of the channels used to send the offers over the customers answer. This offer parameter was the only one which had any relevance about the visualization of the offers.
Channels were compared and analysed among them and were also compared to the different customer segments. The % offers viewed and the hours until be viewed were the parameters considerate.

Secondly, the different offers were analysed. In this case, difficulty, reward and duration were compared to conclude which offer was the most successful, which was the fastest completed and which was the most profitable.
Moreover, I analysed which parameter (difficulty, reward and duration) had more impact on completing the offer.

Finally, time between offer campaigns and their influence customer’s transactions was studied.

Once customers and offers were analysed separately, I analysed both together. The correlation between the different offer parameters and customers answer was calculated to find out the best offer type and the best channel for each customer segment.

## Summary
The last part of the research was the recommendations for the company. It includes the best offer channel, the best timing between offer campaigns and three different offer campaign recommendations: Loyalty campaign, New young customers campaign and Increase revenue campaign.
