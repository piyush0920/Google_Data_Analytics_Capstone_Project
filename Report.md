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

### A summary of my Analysis


