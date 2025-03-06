# ANALYSIS OF CHICAGO BICYCLE RENT USAGE

Data Used: https://divvy-tripdata.s3.amazonaws.com/index.html

The main objective of our case study is "How to convert casuals to members?" or to be specific, a successful bike-sharing company desires to increase the number of their annual memberships. 

# Ask
# The questions that needs to be answered are: 

1. How do annual members and casual riders use Cyclistic bikes differently? 
2. Why would casual riders buy Cyclistic annual memberships? 
3. How can Cyclistic use digital media to influence casual riders to become members?

# Prepare
In this step, we prepare the data by obtaining the dataset and storing it. The datasets are given as a monthly based trip data in a .zip file. I downloaded the last 12 months of trip data as 12 different .zip files and extracted them. We don't need to mine or scrape the data, its given as a .csv file for each month. 

# Process
In this step we process the data and prepare it for our next step where we will find answers to our questions. I used PySpark SQL with Jupyter Notebook for this step since the dataset is too large to merge and operate (around 4,073,561 observations). PySpark is an interface for Apache Spark in Python. It not only allows you to write Spark applications using Python APIs, but also provides the PySpark shell for interactively analyzing your data in a distributed environment. PySpark supports most of Spark’s features such as Spark SQL, DataFrame, Streaming, MLlib (Machine Learning) and Spark Core.

# We have 13 columns and we can infer their content:

ride_id: Id for each trip taken, as of now we are not sure if they are unique or not, we have to find out
rideable_type: Represents the type of a bike
started_at: Date and time of the start time
ended_at: Date and time of the end time
start_station_name: Name of the starting station
start_station_id: Id of the starting station 
end_station_name: Name of the ending station
end_station_id: Id of the ending station
start_lat: Latitude of the starting point
start_lng: Longitude of the starting point
end_lat: Latitude of the ending point
end_lng: Longitude of the ending point
member_casual: Represents the membership status

# Share
After tons of codes and analysis, it's time to share our results and to answer the question "How can we convert casuals to members?". 

We can't fully answer to this question and come up with a solution. Because the data given to us only shows one instance of each unique bike users. The best dataset we require is the instances of a user as casual and after becoming a member. Analyzing those observations, we could find some trend or pattern for users to convert from casual to members. 

However, we still have some observations and inferences from our analysis that it's possible to come up with a possible solution. Although, it might not be effective fully. Now, let's summarize what we have observed from our analysis:

-Member bike usage is quite similar throughout the week except Sunday, which is less than other days. We can infer that members are mostly working people that getting a membership is financially and time wise viable option.
-Casual usage is slow for weekdays but weekends are very popular especially Saturday. 
-Docked bike is the most popular for both members and casuals. But we can see that casuals prefer docked bike more than members do. 
-The average distance traveled by members and casuals are almost same, however, members average trip duration ~15 min. is almost three times less than casual mean trip duration ~42 min. 
-Casual users tend to start and end trips from the same station while its little different for members.
-Most lengthy trips are taken by casuals and they are abnormally long. For instance, top five lengthy trips are 38, 37, 36, 35, 35 days all taken by casuals.
-All occurrence of the missing data (around 200k) of start and end station names occurred with electric bikes only. In other words, out of total 888224 electric bikes in use, around 200k has missing start or end station name. 

**Considering the above observations and insights we can suggest the following:**

We see that members take shorter trips to work with bikes during Monday to Saturday, since it is financially viable and fast transportation. However, casuals prefer longer trips especially Saturday and Sunday. Thus:

1. We could increase the renting price of the bikes for the weekend to target casual users into having a membership especially for docked bikes, since they are preferred more by causal users.
2. Providing a special service or perks for only members might motivate casual users to have a membership. Services might include free ice cream or lemonade, free tour guide, or fast line for renting without any line etc.
