# Restaurant-Analysis-SQL
This analysis was carried out using mysql.The dataset used was gotten from the weekly Data analysis challenge by Data in Motion, LLC. I decided to take it beyond visualization of data to generating queries in order to gain insights on the data. 
Some questions were personally generated and queries were written to generate answers.
Functions used for this analysis are: Aggregation, Min and Max, Average, And operator, Where clause, Limit, etc.

## Analysis for AB Restaurant

![Restaurant Analysis](https://github.com/OpeyemiJagunmolu/Restaurant-Analysis-USING-SQL/assets/122671659/7c3cf2be-1048-4794-80c8-390e3738abf3)

### INSIGHTS
There were 244 guests who visited the restaurant, 157 were male and 87 were female.
93 of the guests were smokers and 151 were non smokers.
$4827.77 was the sum of total bill received by AB Restaurant while $731.58 was the total tip received.
176 people patronised AB Restaurant for dinner while 68 opted for lunch.
The maximum tip was $10 while the minimum tip was $1.
Thursday, Friday, Saturday and Sunday were the days people visited for dinner. Saturday had the highest guests while Thursday had the least.

## PROBLEM STATEMENT
Writing of queries to return answers to various questions.

#### Questions and Queries

-- CREATE A DATABASE
CREATE DATABASE restaurant;

-- SELECT ALL FROM TABLE?
SELECT * 
FROM restaurant;
 
 -- COUNT ALL THE GUESTS AT THE RESTAURANT?
SELECT sex, 
COUNT(sex) AS total_guests
FROM restaurant;

-- RETURN ALL ROWS WITH MALE GENDER?
SELECT * 
FROM restaurant 
WHERE sex 
LIKE "male"; 
 
-- WHAT IS THE NUMBER OF MALE GUEST?
SELECT sex 
FROM restaurant 
COUNT WHERE sex 
LIKE "male";
 
 -- RETURN ALL ROWS WITH FEMALE GENDER?
SELECT sex
FROM restaurant 
WHERE sex 
LIKE "female";
 
-- HOW MANY GUEST DON'T SMOKE?
SELECT smoker 
FROM restaurant 
COUNT WHERE smoker 
LIKE "No";
 
-- ARE THERE GUESTS WHO SMOKE?
SELECT smoker 
FROM restaurant 
COUNT WHERE smoker
LIKE "yes";

-- WHAT IS THE SUM TOTAL OF BILL?
SELECT total_bill, 
SUM(total_bill) 
AS bill_total 
FROM restaurant;
 
-- WHAT IS THE AVERAGE OF THE BILL RECEIVED?
SELECT total_bill, 
AVG(total_bill)
AS avg_bill 
FROM restaurant;
 
 -- WHAT ARE THE THREE MOST RECEIVED BILL?
SELECT * 
FROM restaurant 
ORDER BY total_bill DESC
LIMIT 3;
 
 -- WHAT ARE THE THREE LEAST RECEIVED BILL?
SELECT * 
FROM restaurant 
ORDER BY total_bill ASC
LIMIT 3;

-- EVALUATE THE TOTAL TIP RECEIVED BY THE RESTAURANT?
SELECT tip, 
SUM(tip) 
AS total_tip 
FROM restaurant;
 
 -- WHAT IS THE AVERAGE TIP?
SELECT tip,
AVG(tip) 
AS avg_tip 
FROM restaurant;
  
-- WHAT IS THE MAXIMUM TIP PAID BY GUESTS?
SELECT tip, 
MAX(tip) 
AS max_tip 
FROM restaurant;
   
-- WHAT IS THE MINIMUM TIP PAID BY GUESTS?
SELECT tip, 
MIN(tip) 
AS min_tip 
FROM restaurant;
    
-- WHAT IS THE AVERAGE SIZE?
SELECT tip, 
AVG(size) 
AS avg_size 
FROM restaurant;
 
-- HOW MANY GUEST HAD DINNER AT THE RESTAURANT?
SELECT time 
FROM restaurant 
COUNT WHERE time 
LIKE "Dinner";
 
  -- HOW MANY GUEST HAD LUNCH AT THE RESTAURANT?
SELECT time 
FROM restaurant 
COUNT WHERE time 
LIKE "lunch";

-- WHAT DAYS DID GUESTS TAKE DINNER AT THE RESTAURANT?
SELECT DISTINCT day 
FROM restaurant 
WHERE time 
LIKE "dinner";
  
    -- HOW MANY GUEST HAD DINNER AT THE RESTAURANT ON SUNDAY?
SELECT day, time 
FROM restaurant 
WHERE time 
LIKE "dinner" 
AND day 
LIKE "sun";

-- HOW MANY GUEST HAD DINNER AT THE RESTAURANT ON SATURDAY?
SELECT day, time 
FROM restaurant 
WHERE time
LIKE "dinner" 
AND day 
LIKE "sat";

-- HOW MANY GUEST HAD DINNER AT THE RESTAURANT ON FRIDAY?
SELECT day, time 
FROM restaurant 
WHERE time 
LIKE "dinner" 
AND day 
LIKE "fri";

-- HOW MANY GUEST HAD DINNER AT THE RESTAURANT ON THURSDAY?
SELECT day, time 
FROM restaurant 
WHERE time 
LIKE "dinner" 
AND day 
LIKE "thur";

-- WHAT DAYS DID GUESTS TAKE LUNCH AT THE RESTAURANT?
SELECT DISTINCT day 
FROM restaurant 
WHERE time 
LIKE "lunch";

-- HOW MANY GUEST HAD LUNCH ON THURSDAY?
SELECT day, time 
FROM restaurant 
WHERE time 
LIKE "lunch" 
AND day 
LIKE "thur";

-- HOW MANY GUEST HAD LUNCH ON FRIDAY?
SELECT day, time 
FROM restaurant 
WHERE time 
LIKE "lunch" 
AND day 
LIKE "fri";

-- HOW MANY MALE GUEST SMOKE?
SELECT sex, smoker 
FROM restaurant 
WHERE sex 
LIKE "male" 
AND smoker 
LIKE "yes";

-- WHAT IS THE NUMBER OF MALE GUEST WHO DON'T SMOKE?
SELECT sex, smoker 
FROM restaurant 
WHERE sex 
LIKE "male" 
AND smoker 
LIKE "no";

-- HOW MANY FEMALE GUEST SMOKE?
SELECT sex, smoker 
FROM restaurant 
WHERE sex 
LIKE "female" 
AND smoker 
LIKE "yes";

-- WHAT IS THE NUMBER OF FEMALE GUEST WHO DON'T SMOKE?
SELECT sex, smoker 
FROM restaurant 
WHERE sex 
LIKE "female" 
AND smoker 
LIKE "no";

-- HOW MANY FEMALE GUEST HAD DINNER ON SATURDAY?
SELECT sex, day, time 
FROM restaurant 
WHERE sex 
LIKE "female" 
AND day 
LIKE "sat" 
AND time 
LIKE "dinner";

-- HOW MANY FEMALE GUEST HAD DINNER ON SUNDAY AND DON'T SMOKE?
SELECT sex, day, time, smoker 
FROM restaurant 
WHERE sex 
LIKE "female"
AND day 
LIKE "sun"
AND time 
LIKE "dinner" 
AND smoker 
LIKE "no";

-- HOW MANY MALE GUEST HAD DINNER ON SUNDAY AND DO SMOKE?
SELECT sex, day, time, smoker 
FROM restaurant 
WHERE sex 
LIKE "male"
AND day 
LIKE "sun"
AND time 
LIKE "dinner" 
AND smoker 
LIKE "yes";

-- HOW MANY MALE GUEST HAD DINNER ON SUNDAY AND DON'T SMOKE?
SELECT sex, day, time, smoker 
FROM restaurant 
WHERE sex 
LIKE "male"
AND day 
LIKE "sun"
AND time 
LIKE "dinner" 
AND smoker 
LIKE "no";


_Disclaimer: The dataset used is a dummy and the Restaurant company does not exist in reality._

[RESTAURANT.csv](https://github.com/OpeyemiJagunmolu/Restaurant-Analysis-USING-SQL/files/11842987/RESTAURANT.csv)

[Restaurant Analysis in mysql.pdf](https://github.com/OpeyemiJagunmolu/Restaurant-Analysis-USING-SQL/files/11842990/Restaurant.Analysis.in.mysql.pdf)
