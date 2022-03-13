
# Bellabeat Case Study

### Introduction
Welcome to the Bellabeat data analysis case study! In this case study, you will perform many real-world tasks of a junior data analyst. You will imagine you are working for Bellabeat, a high-tech manufacturer of health-focused products for women, and meet diﬀerent characters and team members. In order to answer the key business questions, you will follow the steps of the data analysis process: ask, prepare, process, analyze, share, and act. Along the way, the Case Study Roadmap tables —
including guiding questions and key tasks — will help you stay on the right path.

By the end of this lesson, you will have a portfolio-ready case study. Download the packet and reference the details of this case study anytime. Then, when you begin your job hunt, your case study will be a tangible way to demonstrate your knowledge and skills to potential employers.

### Scenario
You are a junior data analyst working on the marketing analyst team at Bellabeat, a high-tech manufacturer of health-focused products for women. Bellabeat is a successful small company, but they have the potential to become a larger player in the
 

global smart device market. Urška Sršen, cofounder and Chief Creative Oﬃcer of Bellabeat, believes that analyzing smart device ﬁtness data could help unlock new growth opportunities for the company. You have been asked to focus on one of Bellabeat’s products and analyze smart device data to gain insight into how consumers are using their smart devices. The
insights you discover will then help guide marketing strategy for the company. You will present your analysis to the Bellabeat executive team along with your high-level recommendations for Bellabeat’s marketing strategy.

### Characters and products
●	**Characters**
○	Urška Sršen: Bellabeat’s cofounder and Chief Creative Oﬃcer
○	Sando Mur: Mathematician and Bellabeat’s cofounder; key member of the Bellabeat executive team
○	Bellabeat marketing analytics team: A team of data analysts responsible for collecting, analyzing, and
reporting data that helps guide Bellabeat’s marketing strategy. You joined this team six months ago and have been busy learning about Bellabeat’’s mission and business goals — as well as how you, as a junior data analyst, can help Bellabeat achieve them.
●	Products
○	**Bellabeat app**: The Bellabeat app provides users with health data related to their activity, sleep, stress,
menstrual cycle, and mindfulness habits. This data can help users better understand their current habits and make healthy decisions. The Bellabeat app connects to their line of smart wellness products.
○	**Leaf**: Bellabeat’s classic wellness tracker can be worn as a bracelet, necklace, or clip. The Leaf tracker connects to the Bellabeat app to track activity, sleep, and stress.
○	**Time**: This wellness watch combines the timeless look of a classic timepiece with smart technology to track user activity, sleep, and stress. The Time watch connects to the Bellabeat app to provide you with insights into your daily wellness.
○	**Spring**: This is a water bottle that tracks daily water intake using smart technology to ensure that you are appropriately hydrated throughout the day. The Spring bottle connects to the Bellabeat app to track your hydration levels.
 

○	**Bellabeat membership**: Bellabeat also oﬀers a subscription-based membership program for users.
Membership gives users 24/7 access to fully personalized guidance on nutrition, activity, sleep, health and beauty, and mindfulness based on their lifestyle and goals.

### About the company
Urška Sršen and Sando Mur founded Bellabeat, a high-tech company that manufactures health-focused smart products.
Sršen used her background as an artist to develop beautifully designed technology that informs and inspires women around the world. Collecting data on activity, sleep, stress, and reproductive health has allowed Bellabeat to empower women with knowledge about their own health and habits. Since it was founded in 2013, Bellabeat has grown rapidly and quickly positioned itself as a tech-driven wellness company for women.

By 2016, Bellabeat had opened oﬃces around the world and launched multiple products. Bellabeat products became available through a growing number of online retailers in addition to their own e-commerce channel on their website. The company has invested in traditional advertising media, such as radio, out-of-home billboards, print, and television, but focuses on digital marketing extensively. Bellabeat invests year-round in Google Search, maintaining active Facebook and Instagram pages, and consistently engages consumers on Twitter. Additionally, Bellabeat runs video ads on Youtube and display ads on the Google Display Network to support campaigns around key marketing dates.

Sršen knows that an analysis of Bellabeat’s available consumer data would reveal more opportunities for growth. She has asked the marketing analytics team to focus on a Bellabeat product and analyze smart device usage data in order to gain insight into how people are already using their smart devices. Then, using this information, she would like high-level
recommendations for how these trends can inform Bellabeat marketing strategy.

### Ask
Sršen asks you to analyze smart device usage data in order to gain insight into how consumers use non-Bellabeat smart
devices. She then wants you to select one Bellabeat product to apply these insights to in your presentation. These questions will guide your analysis:
 
1.	What are some trends in smart device usage?
2.	How could these trends apply to Bellabeat customers?
3.	How could these trends help inﬂuence Bellabeat marketing strategy?

### Deliverables:
1.	A clear summary of the business task
2.	A description of all data sources used
3.	Documentation of any cleaning or manipulation of data
4.	A summary of your analysis
5.	Supporting visualizations and key ﬁndings
6.	Your top high-level content recommendations based on your analysis

### Prepare:

Sršen encourages you to use public data that explores smart device users’ daily habits. She points you to a speciﬁc data set:
●	FitBit Fitness Tracker Data (CC0: Public Domain, dataset made available through Mobius): This Kaggle data set
contains personal ﬁtness tracker from thirty ﬁtbit users. Thirty eligible Fitbit users consented to the submission of personal tracker data, including minute-level output for physical activity, heart rate, and sleep monitoring. It includes information about daily activity, steps, and heart rate that can be used to explore users’ habits.
Sršen tells you that this data set might have some limitations, and encourages you to consider adding another data to help address those limitations as you begin to work more with this data.

Source: https://www.kaggle.com/arashnic/fitbit (From Kaggle). The data has recorded 33 fitbit users for 30 days. It has 18 CSV files. From which we have go for analysis by exploring each CSV files.

### ROCCC

* Reliability: This dataset generated by respondents to a distributed survey via Amazon Mechanical Turk between 03.12.2016-05.12.2016.
* Original: The data is from 33 FitBit users which is generated by the submission of users for personal tracker data via Amazon Mechanical Turk.
* Comprehensive: Heart rate, minutes calories narrow_merged, minutes calories wide_merged. The data is small, limited, and minimal and recorded only for 30 days.
* Current: Data is from March 2016 to May 2016 which is not current. The application should have come up with new features now and the tracking may differ now.
* Cited: Unknown.

### Process:

After exploring all the CSV files, I found that dailyActivity_merged, sleepDay_merged, and weightLogInfo_merged has covered almost all the factors in the 18 CSV files.

I merged the files dailyActivity_merged and SleepDay_merged and dailyActivity_merged and weightLogInfo_merged by merging Activity date and Id as the primary key

**=CONCAT(B2,"", LEFT(C2, 9)) for double digit of the day of the month
=CONCAT(B2,"", LEFT(C2, 8)) for single digit of the day of the month**

Used VLOOKUP with the formula for merging both files

DailyActivity_merged + SleepDay_merged:

=VLOOKUP(A2,sleepDay_merged.xlsx!$A$2:$J$414,8, FALSE) -TotalSleepRecords
=VLOOKUP(A2, sleepDay_merged.xlsx!$A$2:$J$414,9, FALSE) - TotalMinutesAsleep
=VLOOKUP(A2, sleepDay_merged.xlsx!$A$2:$J$414,10, FALSE) - TotalTimeInBed


DailyActivity_merged + WeightLogInfo_merged:

=VLOOKUP(A2,weightLogInfo_merged.xlsx!$A$2:$M$68,8, FALSE) -WeightKg
=VLOOKUP(A2,weightLogInfo_merged.xlsx!$A$2:$M$68,9, FALSE) -WeightPounds
=VLOOKUP(A2,weightLogInfo_merged.xlsx!$A$2:$M$68,10, FALSE) -Fat
=VLOOKUP(A2,weightLogInfo_merged.xlsx!$A$2:$M$68,11, FALSE) -BMI
=VLOOKUP(A2,weightLogInfo_merged.xlsx!$A$2:$M$68,12, FALSE) -IsManualReport
=VLOOKUP(A2,weightLogInfo_merged.xlsx!$A$2:$M$68,13, FALSE) -LogId

### Analyze:

By considering the total steps in the dailyActivity_merged.xlsx, I assumed that the average total steps of a daily users as 6500 and others as workout in the excel sheet by using IF formula.

Daily Users Vs Workout Persons:

<img width="582" alt="image" src="https://user-images.githubusercontent.com/84039199/158075147-8ac71e79-27bb-46d8-8f1e-dfb951edf3b8.png">

This graph represents the daily users have total steps till 6500 and workout persons has more than 6500

To justify this assumption, I took the sedentary minutes which means the total sitting posture of the user.

<img width="580" alt="image" src="https://user-images.githubusercontent.com/84039199/158075237-407a8a9b-e308-4f38-b3b9-8b32750e3703.png">

<img width="576" alt="image" src="https://user-images.githubusercontent.com/84039199/158075380-00158351-eeab-4168-958c-65cf5649a10e.png">


The graph shows the justification of my assumption that daily user/office users sits for a long time. Therefore, We can say workout users have used the fitbit more than the daily users.

![image](https://user-images.githubusercontent.com/84039199/158075434-9998ec83-a8d8-47d1-b44a-c11edd93f32c.png)

The more the user sleep, the calories are burned less. The average the sleep minutes lies between 400 to 600 minutes.

![image](https://user-images.githubusercontent.com/84039199/158075504-60dcafa4-6501-4f12-a899-27b866542ea3.png)

The more total steps the more calories burnt.

When merging the dailyActivity and sleepDay files, we can visibly see that not all users tracked their sleeping activity based on the count.

<img width="679" alt="image" src="https://user-images.githubusercontent.com/84039199/158076276-66f8ef8a-3a93-459b-9848-9a2a8e66e693.png">

This graph shows the weekdays and sleep tracked activities

<img width="585" alt="image" src="https://user-images.githubusercontent.com/84039199/158076505-00caf89b-c653-4ed0-955b-fb10e0e7575f.png">

From this graph, we can say that only 8 users out of 33 users have logged on the weight. 5 users have logged on manually and 3 user have logged on with some other devices.

### Share & Act:

### Conclusion:

* Compared to daily users, workout persons are using the fitbit more frequently. Also, the sedentary minutes and total are recorded mostly by the users compared to other factors.
* Users used to track their daily activities mostly than sleep tracker and weight record.
* Wednesday is the average days tracked for sleep and daily activites by all the users.

### Recommendations:

* Come with more features like food tracking daily and generate reports for each week or daily for user's insights
* Fitbit's user did not use the sleep tracker. It might be because od uncomfortable for wearing the smart device during sleep or low battery while sleeping. Bellabeat can think about it and come with a solution.
* Extend the trail days for the users with affordable price.
* Give suggestions and recommendations regarding the user's health by their daily activity.
* Bellabeat can think about new feature for avoiding manual weight logon info.

~[Theepeekaa](https://www.linkedin.com/in/theepeekaa-ramakrishnan-shanthi-4270aa1a3/)
