# Pwc-Switzerland-virtual-internship

## Task 2-Call Centre Trends


Visualizing customer and agent behavior
Create a dashboard in Power BI for Call Centre Manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset. 


###  *Table of Contents:

#### •		Problem Statement

#### •		Flow of work-:
```             
Step 1- Upload Data
             
Step 2-Cleaning data
            
Step 3-Transform data
             
Step 4-Load data 
```
#### •	Data Preparation
```
Data Modelling

Writing DAX 
```
#### •		Data Visualization

#### •		Data Analysis

#### •		Insights

#### •		Shareable link

#### •Problem Statement

The purpose of this analysis is to create a dashboard in PowerBI for call canter manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset. Get creative!

Possible KPIs include (but are not limited to):

•	Overall customer satisfaction

•	Overall calls answered/abandoned

•	Calls by time

•	Average speed of answer

•	Agents performance quadrant -> average handle time(talk duration) vs calls answered


#### •	Flow of work

##### Step 1- Upload Data

The Dataset used for this analysis was presented by PWC_Switzerland and available at their official website page - [Dataset_link]

##### Step 2-Cleaning data

Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modelling.The call canter dataset is given by a table named:

•	Call Center which has 10 columns and 5000 rows of observation

The tabulation below shows the Call center table with its column names and their description:

| Column Name	    | Description     | 
| ------------- | ------------- | 
| `Call Id`        |Represents every unique observation in the dataset         | `NewYork`   |
| `Agent	  `         | Describes the name of the agent           | `Toronto`   |
| `Date` |    	                  Describes the date of the call|
| `Time` |	                        Represents the time of the call|
|`Topic` |                       Describes the topic of the caller|
| `Answered`                     |(Y/N)	Describes if the call was Answered or not|
|  `Resolved`	                    |Describes if the problem was Resolved or not|
| `Speed of answer(in seconds)`	|Represents the speed of answer in seconds|
| `AvgTalkDuration`              |	Represents the average talk duration of call|
| `Satisfaction rating`	        |Represents the satisfaction rating of the agent during the call|

##### Step 3-Transform data
Data Cleaning and transformation for the dataset were done in power query as follows:
•	Unnecessary columns were removed
•	Each of the columns in the table was validated to have the correct data type
•	Unnecessary rows were removed

#### Data preparation: -

##### Data Modelling
After the dataset was cleaned and transformed, it was ready to be modelled.
•	The official dataset is marked as the `FACT` table in the dataset.

•	A separate Agent Table is created by using the DAX function-
Agent table = `DISTINCT` ('Fact Table'[Agent])

•	A separate Topics table is created by using the DAX function
        Topics = `DISTINCT` ('Fact Table'[Topic])
        
•	Along with this, a separate table- All Measuress is created to store all the measures which we have used in this model.

##### Data Visualization
Data visualization for the datasets was done in Microsoft Power BI Desktop:
•	The Call Center Manager Page: Shows KPIs including overall customer satisfaction, overall calls answered/abandoned, calls by time, average speed of answer, 
agents performance quadrant -> average handle time(talk duration) vs calls answered

#### Data Analysis
Measures used in visualization are:

•	`Answered_call` = CALCULATE(COUNT('Fact Table'[Call Id]),FILTER('Fact Table','Fact Table'[Answered (Y/N)]="Y"))

•	`Resolved count` = CALCULATE(COUNT('Fact Table'[Call Id]),'Fact Table'[Resolved]="Y")

•	`Avg_rating` = AVERAGE('Fact Table'[Satisfaction rating])

•	`Average speed of answer` = AVERAGE('Fact Table'[Speed of answer in seconds])

•	`Target Value Satisfaction` = 4.5

•	`%Call Answered` = DIVIDE('All Measuress'[Answered_call],[Total_calls],0)

•	`%call resolved` = DIVIDE([Resolved count],[Total_calls],0)

•	`%Call Unanswered` = DIVIDE([Not_answered],[Total_calls],0)

•	`%call unresolved` = DIVIDE('All Measuress'[Unreolved count],[Total_calls],0)

•	`Agent_slicer` = DISTINCTCOUNT('Fact Table'[Agent])

•	`Average speed of answer(IN MIN)` = DIVIDE('All Measuress'[Average speed of answer],60,0)

•	`Avg duration of talk` = AVERAGE('Fact Table'[AvgTalkDuration])

•	`Avg talk of duration (IN MIN)` = DIVIDE('All Measuress'[Avg duration of talk],60,0)

•	`No of agent` = CALCULATE(DISTINCTCOUNT('Fact Table'[Agent]))

•	`Not_answered` = CALCULATE(COUNT('Fact Table'[Call Id]),FILTER('Fact Table','Fact Table'[Answered (Y/N)]="N"))

•	`Total_calls` = COUNTROWS('Fact Table')

•	`Unreolved count` = CALCULATE(COUNT('Fact Table'[Resolved]),'Fact Table'[Resolved]="N")


#### Insights

As shown by Data Visualization, It can be deduced that:

•	The average satisfaction rating is 3.40

•	81.08% of total calls were answered and 18.92% of total calls were not answered

•	72.92% of total calls were resolved and 27.08% of total calls were not resolved

•	The average speed of answer is 67.52 seconds

•	Jim has answered total 536 call which is highest whereas Stewart answered lowest number of calls i.e. 477



#### Dashboard image


![image]




## Task 3-Customer Retention-Customer demographics and insights.



###  *Table of Contents:

#### •		Problem Statement

#### •		Flow of work-:
```             
Step 1- Upload Data
             
Step 2-Cleaning data
            
Step 3-Transform data
             
Step 4-Load data 
```
#### •	Data Preparation
```
Data Modelling

Writing DAX 
```
#### •		Data Visualization

#### •		Data Analysis

#### •		Insights

#### •		Shareable link






#### •Problem Statement
The telecom Retention Manager has scheduled a meeting with the engagement partner at PwC to cover these points:

 •		Customers in the telecom industry are hard-earned: we don’t want to lose them.
 
 •		The retention department is here to get customers back in case of termination.
 
 •		Currently, we get in touch after they have terminated the contract, but this is reactionary: it would be better to know in advance who is at risk.
 
 •		We  have done customer analysis with Excel: it has always ended in a dead-end.
 
 •		We would like to know more about our customers: visualised clearly so that it’s self-explanatory for our management.

Your colleague, the engagement partner, asks you to do the following tasks:

 1)	Define proper KPIs

 2)	Create a dashboard for the retention manager reflecting the KPIs

 3)	Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed

Here are some inputs:

 •		Customers who left within the last month
 
 •		Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
 
 •		Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical
 
 •		Demographic info about customers – gender, age range, and if they have partners and dependents
 
 
#### •	Flow of work

##### Step 1- Upload Data

The Dataset used for this analysis was presented by PWC_Switzerland and available at their official website page - [Dataset_link]

##### Step 2-Cleaning data

Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modelling.The Customer Retention dataset is given by a table named:

•	Customer retention which has `23 columns and 7043 rows` of observation

The tabulation below shows the Customer retention table with its column names and their description:

| Column Name	    | Description     | 
| ------------- | ------------- | 
| `customerID`        |Represents the unique number of the customer in the dataset|
| `gender`         | Describes the gender of the customer |
| `SeniorCitizen` |    	                Describes if the customer is a senior citizen|
| `Partner` |	                       Describes if the customer has a partner|
|`Dependents` |                      	Describes if the customer has a dependent|
| `tenure`                     |Describes how long as a customer|
|  `PhoneService`	                    |Describes if the customer has registered a phone service|
| `MultipleLines`	|Describes if the customer has registered multiple lines|
| `InternetService`              |	Describes if the customer has registered for internet service|
| `OnlineSecurity`	        |Describes if the customer has registered for online security|
| `OnlineBackup`	        |Describes if the customer has registered for online backup|
| `DeviceProtection`	        |Describes if the customer has registered for device protection|
| `TechSupport`	        |Describes if the customer has registered for tech support|
| `StreamingTV`	        |Describes if the customer has registered to stream tv|
| `StreamingMovies`	        |Describes if the customer has registered to stream movies|
| `Contract`	        |Describes if the length of the contract of the customer|
| `PaperlessBilling`	        |Describes if the customer has registered for paperless billing|
| `PaymentMethod`	        |Describes the payment method of the customer|
| `MonthlyCharges`	        |Represents the monthly charge incurred by the customer|
| `TotalCharges`	        |	Represents the total charge incurred by the customer|
| `numAdminTickets`	        |Represents the number of admin tickets opened by the customer|
| `numTechTickets`	        |Represents the number of tech tickets opened by the customer|
| `Churn`	        |Describes if the customer is at risk of churn|



##### Step 3-Transform data
Data Cleaning and transformation for the dataset were done in power query as follows:
•	Each of the columns in the table was validated to have the correct data type
•	Unnecessary rows were removed

#### Data preparation: -

##### Data Modelling
After the dataset was cleaned and transformed, it was ready to be modelled.
•	The official dataset is marked as the `01 CHURN-Dataset` table in the dataset.
       
•	Along with this, a separate table- All Measuress is created to store all the measures which we have used in this model.

##### Data Visualization
Data visualization for the datasets was done in Microsoft Power BI Desktop:

•	`Demographic` Info : Shows the male-female distribution,churn by senior citizen,dependents impact,partner impact effect of internet service provider recommendations and a short insight on the report

•	`Account Info` : shows contrct type payment method tenuraity impact on customer count total charges, average monthly charges etc

•	`Services` : shows customer count by streamingTV,customer count by streamingmovies,churn by phoneservice,online security device protection,Tech support etc

•	`Email / Insights and suggestion` :Insights ans suggestions to the engagement partner explaining  findings, and include suggestions as to what needs to be changed

#### Data Analysis
Measures used in visualization are:

•	`%churn` = ([churn count]/COUNT('01 Churn-Dataset'[customerID]))*100

•	`Avg_monthly charges` = AVERAGE('01 Churn-Dataset'[MonthlyCharges])

•	`Avg_tenure` =AVERAGE('01 Churn-Dataset'[tenure])

•	`churn count` = CALCULATE(COUNT('01 Churn-Dataset'[customerID]),'01 Churn-Dataset'[Churn]="yes")

•	`Female_customers` = CALCULATE(COUNT('01 Churn-Dataset'[customerID]),'01 Churn-Dataset'[gender]="female")

•	`Male` = CALCULATE(COUNT('01 Churn-Dataset'[customerID]),'01 Churn-Dataset'[gender]="Male")

•`Total no of customers` = COUNT('01 Churn-Dataset'[customerID])

•	`Retained count` = CALCULATE([Total no of customers],'01 Churn-Dataset'[Churn]="No")

•	`Revenew lost` = CALCULATE(SUM('01 Churn-Dataset'[TotalCharges]),'01 Churn-Dataset'[Churn]="yes")


#### Insights

As shown by Data Visualization, It can be deduced that:

•	Out of all the 7043 customers, 26.54 i.e overall 27 % of the customers churned last month. 

• Customers having short tenure are more frequently switching than customers having longer tenure.

• If no  Tech Support, Device Protection, and Online Security are provided then the chances of customers churning are high.

•  payment method like Electronic check also makes a significant impact on the churning decision.

• There is no relation between gender with churning.  

• senior citizens are less likely to churn rate.

• Customers with any dependents or partners are churning less likely, whereas the non-dependents and non-partners customers are more likely to shift.

• Tenure and contract play an important role in determining whether the customer will churn. Customers with monthly contracts i.e. lower tenure will switch frequently.

• Customers with Fiber Optic internet service will churn more compared to DSL internet service holders.


#### Suggestions
•	Increasing the basic contract plan from 1 month to 3 months or  6 months can be a good starting point. This will help customers to be with us for a longer tenure.

•	Starting special offers or schemes for customers who are single and have no family responsibility. They can become a permanent customer of the company. 'Catch them Young' is key to success here.

•	provide some offers to the senior citizens as they are stable customers like overall offer some discounts on long tenure plans.

•	Offering basic services like device protection, tech support, and online security should be the primary goal. This will help the customer stay longer with the brand.

#### Dashboard image

| Figure 1 shows visualizations from `Demographic` Info |
| ----------- |
| ![image]

|Figure 2 shows visualizations from `Account Info` |
| ----------- |
|![image]


|Figure 3 shows visualizations from `Services` |
| ----------- |
|![image]

|Figure 4 shows visualizations from `Email / Insights and suggestion` |
| ----------- |
|![image]|





##Task-04 Diversity & Inclusion





###  *Table of Contents:

#### •		Problem Statement

#### •		Flow of work-:
```             
Step 1- Upload Data
             
Step 2-Cleaning data
            
Step 3-Transform data
             
Step 4-Load data 
```
#### •	Data Preparation
```
Data Modelling

Writing DAX 
```
#### •		Data Visualization

#### •		Data Analysis

#### •		Insights

#### •		Shareable link






#### •Problem Statement
Task is to do the following:

 •		Define relevant KPIs in hiring, promotion, performance and turnover, and create a visualisation.
 Write what you think some root causes of their slow progress might be.
 
 •		Currently, we get in touch after they have terminated the contract, but this is reactionary: it would be better to know in advance who is at risk.
 
Calculating the following measures could help to define proper KPIs:

 • # of men
 
 • # of women
 
•# of leavers

• % employees promoted (FY21)

• % of women promoted

• % of hires men

• % of hires women

• % turnover 

• Average performance rating: men

• Average Performance rating: women


#### •	Flow of work

##### Step 1- Upload Data

The Dataset used for this analysis was presented by PWC_Switzerland and available at their official website page - [Dataset_link]

##### Step 2-Cleaning data

Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modelling.The Customer Retention dataset is given by a table named:

•	Cdiversity and inclusion which has `32 columns and 500 rows` of observation

The tabulation below shows the Customer retention table with its column names and their description:

| Column Name	    | Description     | 
| ------------- | ------------- | 
| `Employee ID`        |Represents the unique number of the employee in the dataset|
| `Gender`         |Describes the gender of the employee |
| `Job Level after FY20 promotions` | Describes the job level of the employee after being promoted in FY20|
| `New hire FY20?` |	Describes if the employee is a new hire in FY20|
|`FY20 Performance Rating` |   Represents the performance rating of the employee in FY20|
| `Promotion in FY21?`                     |Describes if the employee is being promoted in FY21|
|  `In base group for Promotion FY21`	                    |Describes if the employee is being selected for promoted in FY21|
| `Target hire balance`	|Describes the target hire balance of the employee|
| `FY20 leaver?`              |	Describes if the employee is a leaver in FY20|
| `In base group for turnover FY20`	        |Describes if the employee is in a group for turnover in FY20|
| `Department @01.07.2020`	        |Describes the department each employee belongs to as at January 7, 2020|
| `Leaver FY`	        |Describes if the employee is a leaver in a FY|
| `Job Level after FY21 promotions`	        |Describes the job level of the employee after being promoted in FY21|
| `Last Department in FY20`	        |Describes the last department each employee belongs in FY20|
| `FTE group`	        |Describes if the employee belongs to a FTE group|
| `Time type`	        |Describes the contract type employee|
| `Department & JL group PRA status`	        |Describes the department and JL group PRA status of the employee|
| `Department & JL group for PRA`	        |Describes the department and JL group PRA of the employee|
| `Job Level group PRA status`	        |Describes the job level group PRA status of the employee|
| `Job Level group for PRA`	        |Describes the job level group PRA of the employee|
| `Time in Job Level @01.07.2020`	        |Describes the time in job level of the employee|
| `Job Level before FY20 promotions`	        |Describes the job level employee before being promoted in FY20|
| `Promotion in FY20?`	        |Describes if the employee is being promoted in FY20|
| `FY19 Performance Rating`	        |Describes the performance rating of the employee in FY19|
| `Age group`	        |Describes the age group of the employee|
| `Age @01.07.2020`	        |Represents the age of the employee as at January 07, 2020|
| `Nationality 1`	                       |Describes the nationality of the employee in state level|
| `Region group: nationality 1`	  |Describes the nationality of the employee in country level|
| `Broad region group: nationality 1`	  |Describes the nationality of the employee in regional level|
| `Last hire date`	     |	Describes the last hire date of the employee|
| `Years since last hire`		 |Represents the number of years since last hire of the employee|
| `Rand`		|generates random number for each entry in the dataset|

##### Step 3-Transform data
Data Cleaning and transformation for the dataset were done in power query as follows:
•	Each of the columns in the table was validated to have the correct data type.
•	Unnecessary rows were removed.
•	Unnecessary rows were filtered.

#### Data preparation: -

##### Data Modelling
After the dataset was cleaned and transformed, it was ready to be modelled.
•	The official dataset is marked as the `Pharma Group AG` table in the dataset.
       
•	Along with this, a separate table- `Basic Measuress` is created to store all the measures which we have used in this model.

`MEN_new_HIRES`-  it's  dim table which is created to store all the measures related to  men category in this model.

`women_new hires`-it's dim table which is created to store all the measures related to  women category in this model

##### Data Visualization

Data visualization for the datasets was done in Microsoft Power BI Desktop:

•	`KPI-1_Hiring`  : Shows the hiring history,age group wise distribution,job role wise male-female distribution,nationality wise female-male departmental distribution,and men-female distribution by Job level after FY21 promotion etc.


•	` KPI-2_Promotion` : shows gender distribution for FY20 promotion and FY21 promotion,Promotion by age group nationwise promotion etc.

•	` KPI-3 Performance rating` : shows average rating for FY19 & FY20 ,age group wise performance rating with gender distribution etc.

•	`KPI-4 Turnover` : shows turnover rate, # of levaers by gender,# of levers by time type,by last department, by year etc.

•	`Insights`: Insights and suggestions figured out from the above analysis which will help to made changes.
 
#### Data Analysis

Measures used in visualization are:

•	`# of leavers` = CALCULATE([#Total No.of employees],'Pharma Group AG'[FY20 leaver?]="Yes")

•	`#Total_employees_promoted_in_FY20` = CALCULATE(COUNT( 'Pharma Group AG'[Employee ID]),'Pharma Group AG'[Promotion in FY20?]="Y")

•	`# Total_employees_promted_in_FY21` = CALCULATE(COUNT('Pharma Group AG'[Employee ID]),'Pharma Group AG'[Promotion in FY21?]="Yes")

•	`#count after hiring` = 'Basic Measuress'[#Total_men] + [#Total_female]

•	`#Total No.of employees` = COUNT('Pharma Group AG'[Employee ID])

•	`#Total_female` = CALCULATE(COUNT('Pharma Group AG'[Employee ID]),'Pharma Group AG'[Gender]="female")

• `#Total_men` = CALCULATE(COUNTROWS('Pharma Group AG'),FILTER('Pharma Group AG','Pharma Group AG'[Gender]="male"))

•	`#Total_promted` = SUMX('Pharma Group AG',[# Total_employees_promoted_in_FY20]+[# Total_employees_promted_in_FY21])

•	`% employees promoted (FY21)` = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[In base group for Promotion FY21]),FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY21?]="Yes")),[#Total No.of employees])*100

•	`% employees promoted in FY20` = DIVIDE(CALCULATE([#Total No.of employees],'Pharma Group AG'[Promotion in FY20?]="Y"),[#Total No.of employees])*100

•	`% employees promoted in FY21` = DIVIDE(CALCULATE([#Total No.of employees],'Pharma Group AG'[Promotion in FY21?]="Yes"),[#Total No.of employees])*100
•	`% MEN NEW HIRES` = DIVIDE(MEN_new_HIRES[men new hires count],[New_Hires])*100

•	`% of hires men` = DIVIDE([#Total_men],'Basic Measuress'[#Total_men]+[#Total_female])

•	`% of hires women` = DIVIDE([#Total_female],'Basic Measuress'[#Total_female]+[#Total_men])

•	`% of men promoted in FY20` = DIVIDE(CALCULATE([#Total No.of employees],FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male"),FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY20?]="Y")),[#Total No.of employees])

•	`% of men promoted in FY21` = DIVIDE(
CALCULATE([#Total No.of employees],
FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male"),   
FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY21?]="Yes")),[#Total No.of employees])

•	`% of women` = DIVIDE([#Total_female],([#Total_men]+[#Total_female]))*100

•	`% of women promoted in FY20` = DIVIDE(CALCULATE([#Total No.of employees],FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Female"),FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY20?]="Y")),[#Total No.of employees])

•	`% of women promoted in FY21` = DIVIDE(
    CALCULATE([#Total No.of employees],
    FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Female"),
    FILTER('Pharma Group AG','Pharma Group AG'[Promotion in FY21?]="Yes")),[#Total No.of employees])

•	`% total employees promoted` = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[In base group for Promotion FY21]),'Pharma Group AG'[Promotion in FY21?]="Yes"), CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]), 'Pharma Group AG'[In base group for Promotion FY21]="Yes"))

•	`% WOMEN NEW HIRES` = DIVIDE([total women hires count],[New_Hires])*100

•	`% women promoted` = DIVIDE(CALCULATE(COUNT('Pharma Group AG'[In base group for Promotion FY21]),'Pharma Group AG'[Promotion in FY21?]="Yes", 'Pharma Group AG'[Gender]="Female"), CALCULATE(COUNT('Pharma Group AG'[Promotion in FY21?]),'Pharma Group AG'[Promotion in FY21?]="Yes"))

•	`%_Turnover` = [# of leavers]/'Basic Measuress'[Avg of employee count]

•	`%Total_Promoted` = DIVIDE([#Total_promted],[#Total No.of employees])*100

•	`Average Performance Rating (men)` = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Male")

•	`Average Performance Rating (women)` = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Female")

•	`Average rating performance (FY19)` = AVERAGE('Pharma Group AG'[FY19 Performance Rating])

•	`Average rating performance (FY20)` = AVERAGE('Pharma Group AG'[FY20 Performance Rating])

•	`Avg of employee count` = ('Basic Measuress'[Count before hiring]+'Basic Measuress'[#count after hiring])/2

•	`Avg performance rating Men (FY19)` = CALCULATE(AVERAGE('Pharma Group AG'[FY19 Performance Rating]),'Pharma Group AG'[Gender]="Male")

•	`Avg Performance rating MEN(FY20)` = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Male")

•	`Avg performance rating women (FY19)` = CALCULATE(AVERAGE('Pharma Group AG'[FY19 Performance Rating]),'Pharma Group AG'[Gender]="Female")

•	`Avg performance rating women (FY20)` = CALCULATE(AVERAGE('Pharma Group AG'[FY20 Performance Rating]),'Pharma Group AG'[Gender]="Female")

•	`Count before hiring = CALCULATE(COUNT('Pharma Group AG'[Employee ID]),'Pharma Group AG'[In base group for turnover FY20]="Y")
•	`FTE = CALCULATE(COUNT('Pharma Group AG'[FTE group]), FILTER('Pharma Group AG','Pharma Group AG'[FTE group]="Full Time"))

•	`MEN_new_HIRES` = FILTER('Pharma Group AG','Pharma Group AG'[Gender]="Male" && 'Pharma Group AG'[New hire FY20?]="Y")

•	`New_Hires` = CALCULATE(COUNT('Pharma Group AG'[Employee ID]),FILTER('Pharma Group AG','Pharma Group AG'[New hire FY20?]="Y"))

•	`Not FTE` = CALCULATE(COUNT('Pharma Group AG'[FTE group]),FILTER('Pharma Group AG','Pharma Group AG'[FTE group] <> "Full Time" ))

•	`total women hires count` = COUNTROWS('women_new hires')

•	`Turnover_YES` = calculate(COUNT('Pharma Group AG'[In base group for turnover FY20]),FILTER('Pharma Group AG','Pharma Group AG'[In base group for turnover FY20]="Y"))


### Insights

####As shown by Data Visualization, It can be deduced that:

•	The average performance rating of the employees decreased from to in FY20.. 

• Maximum hiring of employees  is done from Switzerland ,France & Germany respectively, hence in order to increase diversity need to hire talented employees from different part of globe.

• The slow progress in the executive level is of the fact  that only less than 20% female is promoted to this  managerial and executive roles. 

• Employee promotion rate is increase by 3% in FY21 than FY20.

• Performance rating is drop by 0.57 in FY20 than FY19

• FTE's are more likely to leave  as well as male as highly leaver than females.



### Suggestions

####To ensure progress in diversity and inclusion  in the executive level; 

• More women should be hired and most especially promoted because the gap in the ratio of men to women is quite large. 

• Forthe  Executive and Director position ,female employee count as well as the promotio  count is too low compared to male employee     hence more women should be hired as well as promoted.

 • Age group 30-39 has more rate of promotion compared to 40-49 age group, experience should be consider as one of the the one of the criteria for promotion checklist.



#### Dashboard image

| Figure 1 shows visualizations from `KPI-1_Hiring`|
| ----------- |
| ![image]
|Figure 2 shows visualizations from ` KPI-2_Promotion` |
| ----------- |
|![image]

|Figure 3 shows visualizations from ` KPI-3 Performance rating` |
| ----------- |
|![image]


|Figure 4 shows visualizations from `KPI-4 Turnover` |
| ----------- |
|![image]

|Figure 5 shows visualizations from `Insights ` |
| ----------- |
|![image]
|Figure 6 shows visualizations from `Internship_Completion_Certificate` |
| ----------- |
|![image]
