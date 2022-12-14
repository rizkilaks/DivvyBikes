# DivvyBikes

### Tools
- SQLite
- Tableau

[Tableau Dashboard](https://public.tableau.com/app/profile/rizki.laksmana/viz/BikeSharingFixed/Dashboard12)

[Dataset Source](https://divvy-tripdata.s3.amazonaws.com/index.html)

![](Charts/DivvyBikes.jpg)

## **Introduction**
In 2016, Divvy Bikes launched a successful bike-sharing offering. Since then, the program has grown to a fleet of 5,824 bikes that are geo-tracked and locked into a network of 692 stations across Chicago. Bikes can be accessed from one station and returned to another at any time in the system.

To date, Divvy Bikes's marketing strategy has relied on efforts to build general awareness and attract a broad consumer segment. One approach that helps make this happen is price flexibility: one-way tickets, full-day passes, and annual memberships. Customers who purchase a one-way ticket or a full day ticket are referred to as casual rider. Customers who purchase an annual membership are referred to annual member. 

Divvy Bikes financial analysts have concluded that annual member are much more profitable than casual rider. While pricing flexibility is helping Divvy Bikes attract more customers, they believes that maximizing the number of annual member will be the key to future growth. Rather than creating a marketing campaign targeting new customers, they believes there is an opportunity to convert casual rider into member. He noted that casual drivers are familiar with the Divvy Bikes program and have chosen Divvy Bikes for their mobility needs.

They has set a clear goal: Designing a marketing strategy aimed at converting casual rider into annual member. However, to do so, the marketing analyst team needs to better understand the differences between annual member and casual rider, and why a rider would be willing to buy a membership. They were interested in analyzing Divvy Bikes's bicycle trip data to identify trends.

From there, we can turn it into business questions that will be used as a guide for our analysis.

<ol>
    <li>How do annual member and casual rider use bicycles differently?</li>
    <li>Why do casual rider buy Divvy Bikes annual memberhip?</li>
    <li>What types of bicycles are used the most?</li> 
    <li>How did Divvy Bikes perform throughout the year?</li> 
</ol>

## **Data Validation**
The data consists of 15 .csv files from October 2020 until December 2021, totaling 6,375,005 and 5,913,054 rows, before and after cleaning, respectively. All data cleaning was performed using SQL and is summarized below.

<ol>
<li>Combined all .csv files</li>
<li>Assigned the correct data type to each column</li>
<li>Added 'day_of_week' column</li>
<li>Eliminated outliers</li>
<li>Made a new table and exported it to .csv</li>
</ol>

## **Data Discovery and Visualization**

### **BQ 1 - How do annual member and casual rider use bicycles differently?**

![](Charts/Casual%20Rider.png)
![](Charts/Annual%20Member.png)

- Casual rider mostly use bicycles on weekends with peak hours at 10 am to 6 pm. Meanwhile, on weekdays, casual rider use bicycles mostly in the afternoon, which is 4 pm to 7 pm.
- Annual member use bicycles mostly on weekdays, with peak hours from 6 to 8 am, and 3 to 7 pm. Meanwhile, on weekends, the trend is the same as for casual rider, namely peak hours from 10 am to 6 pm.
- Casual rider mostly use bicycles on weekends with peak hours at 10 am to 6 pm. Meanwhile, on weekdays, casual rider use bicycles mostly in the afternoon, which is 4 pm to 7 pm.
- Annual member use bicycles mostly on weekdays, with peak hours from 6 to 8 am, and 3 to 7 pm. Meanwhile, on weekends, the trend is the same as for casual rider, namely peak hours from 10 am to 6 pm.

![](Charts/Average%20Ride%20Duration%20and%20Total%20Ride%20per%20Day.png)

- Casual rider have an average trip duration that ranges from 16 to 20 minutes, with the highest trip duration obtained on weekends.
- Annual member have an average trip duration that ranges from 12 to 14 minutes, with the highest trip duration obtained on weekends.
- Total ride per day for casual rider range from 272 thousand to 365 thousand on weekdays, and eventually increases to 545 thousand on weekends.
- Total ride per day for annual member range from 465 thousand to 532 thousand on weekdays, but on weekends this figure decreases to a merely 415 thousand.

![](Charts/Total%20Ride%20per%20Ride%20Duration.png)

Both have the pretty much the same trend, but with different peaks. Number of ride for annual member peak at 3 to 6 minutes, while casual rider peak at 6 to 9 minutes. In addition, 0-30 minutes rides is dominated by annual member, while 30+ minutes rides is dominated by casual rider.

Long story short, annual member and casual rider behave differently. On average, annual member tend to have a shorter ride than casual rider and mainly use the bike on weekdays, whereas casual rider use the bike on weekends. If we notice on the last graph, in terms of total ride, casual rider beat annual member in longer ride durations. This is partly because there are casual rider who buy Day Pass and have much longer ride duration than the annual member as we can see in the information provided in the next business question. Unfortunately, the data is limited, so we can't be sure.

### **BQ 2 - Why do casual rider buy Divvy Bikes annual memberhip?**

It is quite clear that they bought annual membership because they need to commute within the city frequently, it is not hard to believe that most of the annual member are local workers, given the trend shown in the chart from the previous business question. 

For casual users, paying an annual membership is definitely much cheaper and time-saving than paying as casual rider. But how about other transportation? Well, we can take a look at the information below, which was obtained from Divvy Bikes official website, [click here](https://ride.divvybikes.com/pricing).

- Annual Membership costs $108/year for unlimited 45-minute ride
- Day Pass costs $15 for unlimited 3-hour ride in a 24-hour period
- Single Ride costs $3.30 for a 30-minute ride
- After reaching the time limit, all plans above costs extra $0.15/minute
- A single train and bus ride costs $2.50 and $2.25, respectively. There are also 1 Day Pass and 1 Month Pass that costs $5 and $75, respectively

Annual membership is a must buy for casual users if the price is that low in compared to other options. In addition, Divvy Bikes also has University Membership and Divvy for Business programs that makes the pricing even cheaper.

### **BQ 3 - What types of bicycles are used the most?**

<p align="center">
    <img src="Charts/Total%20Ride.png">
</p>

Classic bikes are the most frequently used with a total of 3,117,175 rides with the most users being annual member, namely 63.15%, followed by electric bikes with a total of 2,189,147 rides with the most users being annual member, namely 54.93% and finally docked bikes with the most users being casual rider, namely 57.43%.

![](Charts/Monthly%20Performance-Bike.png)

Based on the chart above, before December 2021, riders prefer to use the docked bike. However, since Classic Bike's releases on the same month, the riders' preference has shifted from docked bike to the classic bike.    

<p align="center">
    <img width="50%" src="Charts/CHI-E-Bike-Zone-Map.png">
</p>

On the other hand, some areas can only be reached by using electric bike. That's why, when the trend falls in August 2021 and beyond, eletric bike still get good results.

### **BQ 4 - How did Divvy Bikes perform throughout the year?**

![](Charts/Quarterly%20Performance.png)
![](Charts/Monthly%20Performance.png)

Total rides decreased in the fourth quarter of 2020 to the lowest point in February 2021 with a total of 46,432 rides, then the trend reversed from the end of the first quarter to its peak at the beginning of the third quarter of 756,258. decreased again in the following month until the end of the year. Unfortunately, the data is limited so we cant track what happened before October 2020, but it it seems that the trend that occurred in the fourth quarter of 2020 continues into 2021.

## **Conclusion**
The conclusions that can be drawn from the Divvy Bikes data are as follows:
<ol>
<li>Annual member are locals who use bicycles mainly to commute within the city on weekdays from home to office and vice versa.</li>
<li>casual rider are both locals and tourists who mainly use bicycle on weekends, though rarely.</li>
<li>casual rider buy a Divvy Bikes membership because its a lot cheaper than other public transportation.
<li>Classic bike is the most widely used, followed by electric bike and docked bike.
<li>They did good on the first half, but went bad on the second half, just like the second half of 2020.</li>
</ol>

## **Recommendation**
From the conclusion, we recommend the marketing team to consider the following options:
<ol>
<li> Create a new plan that is shorter than annual membership as casual rider may not want to be tied to annual membership, this can be 1, 3 or 6-month membership. Then, after they plan ends, send them a promotion containing discount code for an annual membership. This plan could encourage casual rider to become annual member if they feel the need to use the service frequently. </li>
<li> Introduce some discounts in certain months for monthly membership (for example, months where total ride decreases). </li>
<li> Just like many subscription-based services, we can also introduce a family plan, this will bring us more new member at once.</li>
</ol>