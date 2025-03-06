**Analysis of Chicago Bicycle Rental Usage**
**Data Source:** https://divvy-tripdata.s3.amazonaws.com/index.html

**Objective**
The primary goal of this case study is to explore how Cyclistic, a bike-sharing company, can increase its annual memberships by converting casual riders into members. Specifically, we aim to answer:

**1. How do annual members and casual riders use Cyclistic bikes differently?/n
2. What factors would motivate casual riders to purchase annual memberships?
3. How can Cyclistic leverage digital media to encourage casual riders to become members?**

**Data Preparation**
The dataset consists of monthly trip data provided in .zip format. For this analysis, I downloaded and extracted 12 months of data, each contained in a separate .csv file. Since the data is readily available, there was no need for additional data mining or web scraping.

**Data Processing**
Given the large dataset (approximately 4,073,561 records), I used PySpark SQL in Jupyter Notebook for efficient processing. PySpark, an interface for Apache Spark in Python, enables fast and distributed data handling, making it well-suited for analyzing extensive datasets.

**Dataset Overview**
The dataset consists of 13 columns, as outlined below:

1. ride_id – Unique identifier for each trip (to be verified for uniqueness).
2. rideable_type – Type of bike used.
3. started_at – Start date and time of the ride.
4. ended_at – End date and time of the ride.
5. start_station_name – Name of the starting station.
6. start_station_id – Unique identifier for the starting station.
7. end_station_name – Name of the ending station.
8. end_station_id – Unique identifier for the ending station.
9. start_lat – Latitude of the starting location.
10. start_lng – Longitude of the starting location.
11. end_lat – Latitude of the ending location.
12. end_lng – Longitude of the ending location.
13. member_casual – Indicates whether the user is a member or a casual rider.

**Findings & Insights**
While the dataset does not provide longitudinal data on individual users transitioning from casual riders to members, it still offers valuable insights into user behavior patterns. Here’s what we discovered:

**Differences in Bike Usage Between Members and Casual Riders:**
**Weekly Trends:**
Members consistently use bikes throughout the week, with slightly lower usage on Sundays. This suggests that many members rely on bike-sharing as a part of their daily commute.
Casual riders, on the other hand, have significantly higher usage on weekends, particularly on Saturdays.
**Bike Type Preferences:**

Docked bikes are the most popular among both groups, but casual riders use them more frequently than members.
Trip Distance & Duration:

The average trip distance for both groups is relatively similar.
However, the average trip duration for members (~15 minutes) is nearly three times shorter than that of casual riders (~42 minutes).
Casual riders often take significantly longer trips, with some lasting over a month. The five longest trips recorded were 38, 37, 36, 35, and 35 days, all taken by casual riders.
**Trip Start and End Patterns:**
Casual users tend to start and end trips at the same station, whereas members show more variation in their trip destinations.
Data Quality Issues:

Around 200,000 trips have missing start or end station names, and all of these instances involve electric bikes. Out of 888,224 electric bike rides, approximately 200,000 lack location data.
**Recommendations for Converting Casual Riders into Members**
**Based on these insights, we propose the following strategies to encourage casual riders to purchase memberships:**
1. Adjust Pricing for Casual Users on Weekends
Since casual riders prefer using bikes for longer durations and mostly on weekends, increasing rental prices during peak weekend hours could encourage them to consider the cost-effectiveness of a membership. This strategy could be particularly effective for docked bikes, which are more popular among casual users.

2. Offer Exclusive Perks for Members
Introducing value-added services for members can make memberships more attractive. Some potential perks include:

Priority Access: Fast-track rentals with no waiting in line.
Member-Exclusive Discounts: Reduced pricing on long rides or electric bikes.
Freebies & Experiences: Complimentary ice cream, lemonade, or even guided city bike tours for members.
3. Leverage Digital Media & Personalized Marketing
To effectively promote memberships, Cyclistic should utilize digital marketing strategies such as:

Targeted Ads & Email Campaigns: Personalized promotions based on riding patterns (e.g., offering membership discounts to frequent weekend riders).
Social Media Engagement: Sharing member testimonials, exclusive perks, and community events to highlight the benefits of joining.
In-App Promotions: Displaying pop-ups or notifications showing how much casual riders could save if they switched to a membership.
**Conclusion**
Although our dataset does not track users transitioning from casual to member status, our analysis provides valuable insights into user behavior. By implementing strategic pricing, enhancing member perks, and leveraging digital media for personalized marketing, Cyclistic can increase its annual memberships and maximize customer retention.
