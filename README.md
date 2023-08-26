# Google Capstone Report

#### Case Study: How Does a Bike-Share Navigate Speedy Success?

### Business Task: Find that how can we convince casual riders to become annual members.

#### Problem/Challenge

How do annual members and casual riders use Cyclistic bikes differently? 
Cyclistic’s finance analysts have concluded that annual members are much more profitable than casual riders. 
Although the pricing flexibility helps Cyclistic attract more customers, 
Moreno believes that maximizing the number of annual members will be key to future growth. 
Rather than creating a marketing campaign that targets all-new customers, 
Moreno believes there is a very good chance to convert casual riders into members.

#### Objective
Design marketing strategies aimed at converting casual riders into annual members.

#### Stakeholders
This Project Involves Lily Moreno: The Director of Marketing Department(development of campaigns
and initiatives), Cyclistic marketing analytics team(collecting, analyzing, and
reporting data), Cyclistic executive team(approving the
recommended marketing program)

### Description of all data sources used in this Project

We will be using Cyclistic’s historical trip data from Past 12 Months to analyze and identify trends. [Download the previous 12 months of Cyclistic trip data
here](https://divvy-tripdata.s3.amazonaws.com/index.html). (Note: The datasets have a different name because Cyclistic is a fictional company. For the purposes of this case study,
the datasets are appropriate and will enable you to answer the business questions. The data has been made available by
Motivate International Inc. under this [license](https://ride.divvybikes.com/data-license-agreement).) 
This is public data that you can use to explore how different customer types are
using Cyclistic bikes. But note that data-privacy issues prohibit you from using riders’ personally identifiable information. This
means that you won’t be able to connect pass purchases to credit card numbers to determine if casual riders live in the
Cyclistic service area or if they have purchased multiple single passes.

### Documentation of any cleaning or manipulation of data

After downloading and unziping the files, converted all files format from CSV to XLS.

Also created two columns in all Excel Workbooks
* "ride_length" - Calculating the length of each ride by subtracting the
column “started_at” from the column “ended_at” (for example, =D2-C2) and format as HH:MM:SS using Formating.
* "days_of_week" - Calculating the day of the week that each ride started using the “WEEKDAY”
command (for example, =WEEKDAY(C2,1)) in each file. Format as General or as a number with no decimals, noting that
1 = Sunday and 7 = Saturday.

### A Summary of my Analysis

I have chosen R for my analysis because of various factors.
Note: Excel is not suitable as the dataset contains more than than a single worksheet can handle. So, you cannot combines the Monthly/Quarterly files into single file.

Here is my Summary:

#### STEP 1: COLLECT DATA
Upload Divvy datasets (csv files) into r.
* By using "read_csv()" function.


#### STEP 2: WRANGLE DATA AND COMBINE INTO A SINGLE FILE
1. Compared column names each of the files.
(While the names don't have to be in the same order, they DO need to match perfectly before we can use a command to join them into one file)
* By using "col_names()" function.

2. Inspect the dataframes and look for incongruencies

* By using str()

3. Stack individual month's data frames into one big data frame (data is from september 2022 to june 2023)

* By using "bind_rows()" function

4. Removed lat, long fields as this data was dropped beginning in 2020


#### STEP 3: CLEAN UP AND ADD DATA TO PREPARE FOR ANALYSIS

1. Inspected the new table that has been created
* By using colnames() ,nrow(), dim() , head(). Also tail(), str(), summary().

2. There were  few problems we needed to fix:
* The data can only be aggregated at the ride-level, which is too granular. We will want to add some additional columns of data -- such as day, month, year -- that provide additional opportunities to aggregate the data.
* We will want to add a calculated field for length of ride data did not have the "tripduration" column. We will add "ride_length" to the entire dataframe for consistency.
* We will also add day of week column as "days_of_week"


3. Added columns that list the date, month, day, and year of each ride(This will allow us to aggregate ride data for each month, day, or year ... before completing these operations we could only aggregate at the ride level, https://www.statmethods.net/input/dates.html more on date formats in R found at that link)


4. Added a "ride_length" calculation to all_trips (in seconds)

5. Inspect the structure of the columns
* By using str()

6. Converted "ride_length" from Character to numeric so we can run calculations on the data
           

7. Removed "bad" data
* The dataframe includes a few hundred entries when bikes were taken out of docks and checked for quality by Divvy or ride_length was negative
* We will create a new version of the dataframe (v2) since data is being removed

8. This above command led to some NA values so we droped them.


#### STEP 4: CONDUCT DESCRIPTIVE ANALYSIS

1. Find Descriptive analysis on ride_length (all figures in seconds)

2. Condensed the four lines above to one line on the specific attribute
* By using "summary()".

3. Compare members and casual users
* By using "aggregate()".

4. Calculated the average ride time by each day for members vs casual users

5. Noticed that the days of the week are out of order fixed that.

6. Calculated the average ride time by each day for members vs casual users

7. Analyzed ridership data by type and weekday

8. Created a visualization for average duration

9. Counting  how many electric, classic, docked bikes used by members and casual riders
#### STEP 5: EXPORT SUMMARY FILE FOR FURTHER ANALYSIS

Created a csv file that we will visualize in Excel, Tableau, or my presentation software

(N.B.: This file location is for a Mac. If you are working on a PC, change the file location accordingly (most likely "C:\Users\YOUR_USERNAME\Desktop\...") to export the data. You can read more here: https://datatofish.com/export-dataframe-to-csv-in-r/)


#### COMPLETED

I have also added the Rscript for detailed analysis.

### Supporting visualizations and key findings

![Click here to view](https://github.com/piyush0920/Google_Data_Analytics_Capstone_Project/blob/main/Dashboard%201.png)


### My top three recommendations based on my analysis
* Classic bike is popular among members. Offering discounts on classic bikes may be enticing for casual riders to take membership.
* Casual riders are most active on weekends so marketing events should be organized during weekends to inform them about the potential benefits.
* Casual riders tend to use their bikes for longer periods than members. By providing discounts for extended rides, we can motivate occasional riders and also encourage our members to ride for longer durations.
