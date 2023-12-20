# CouponAcceptancePredictor
Brief report that highlights the differences between customers who did and did not accept the coupon.ata comes to us from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc.

**Overview**
The goal of this project is to use what you know about visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those that did not.
Data
This data comes to us from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. Answers that the user will drive there ‘right away’ or ‘later before the coupon expires’ are labeled as ‘Y = 1’ and answers ‘no, I do not want the coupon’ are labeled as ‘Y = 0’. There are five different types of coupons -- less expensive restaurants (under $20), coffee houses, carry out & take away, bar, and more expensive restaurants ($20 - $50).

**Data Description**
Keep in mind that these values mentioned below are average values.
The attributes of this data set include:
	1	User attributes
	•	Gender: male, female
	•	Age: below 21, 21 to 25, 26 to 30, etc.
	•	Marital Status: single, married partner, unmarried partner, or widowed
	•	Number of children: 0, 1, or more than 1
	•	Education: high school, bachelors degree, associates degree, or graduate degree
	•	Occupation: architecture & engineering, business & financial, etc.
	•	Annual income: less than $12500, $12500 - $24999, $25000 - $37499, etc.
	•	Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
	•	Number of times that he/she buys takeaway food: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
	•	Number of times that he/she goes to a coffee house: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
	•	Number of times that he/she eats at a restaurant with average expense less than $20 per person: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
	•	Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
	2	Contextual attributes
	•	Driving destination: home, work, or no urgent destination
	•	Location of user, coupon and destination: we provide a map to show the geographical location of the user, destination, and the venue, and we mark the distance between each two places with time of driving. The user can see whether the venue is in the same direction as the destination.
	•	Weather: sunny, rainy, or snowy
	•	Temperature: 30F, 55F, or 80F
	•	Time: 10AM, 2PM, or 6PM
	•	Passenger: alone, partner, kid(s), or friend(s)
	3	Coupon attributes
	•	time before it expires: 2 hours or one day

**Data Transformation and Handling**

There are missing values in columns below:
car                     12576
Bar                       107
CoffeeHouse               217
CarryAway                 151
RestaurantLessThan20      130
Restaurant20To50          189

1. Amongst all, "car" column has over 99% null values. Hence, I plan to not use that column in any analysis.

3. Columns which have string values, there is no need to replace the "null"values with 0 or any other value for them.

4. Age is stored as string since there are two categories created such as "below21" and "50plus" which are strings. In order to be able to use the age column as numeric, I converted the "below21" to 20 and "50plus" category into "51". And finally converted this column to numeric to be able to perform numeric querying operations on age. It is ok to generalize "below21" to 20 in this case, since we dont have granularity into what other age groups exits that are under 21; we are considering those to be approximately 20 years old.

**Data Exploration, Analysis and Findings:**

1. Coupons of Coffee house were most offered and Restaurants where meals/person were expensive costing $20-50 were least offered.

2. The temperature condition that drivers were facing was varying between 20F to 90F. However, interestingly, no driver faced the temperature between 60F and 80F. 

3. Acceptance Summary of Bar Coupons: 
        3.1. Proportion of bar coupons were accepted: 0.41. 
        3.2 There are more number of people who went to bar fewer than 3 times a month. Hence, there is higher percentage of people (62%) who accepted coupons amongst those who went to bar fewer times than those     who went more and accepted coupons (19%).
        3.3 However, people who went to bar more than 3 times/month accepted coupons at 0.24 times higher than those who go to bar less than 3 times a month.
        3.4. Acceptance rate of drivers who are 25 plus and go to bar more than once a month is 40% more than all others
        3.5. Acceptance rate of drivers drivers who go to bar more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry is ~42% more than all others
      3.6. Acceptance rate of people who go to bars more than once a month, had passengers that were not a kid, and were not widowed OR
go to bars more than once a month and are under the age of 30 OR
go to cheap restaurants more than 4 times a month and income is less than 50K, is 61%.

4. Overall, majority people were offered "Coffee House" coupons followed by Restaurant<20 coupons. People who were offered "Coffee House" coupons and "Bar" coupons showed higher acceptance rate (over 40%) as well.

5. People who visited coffee house more than once have accepted coupons at the rate of 58% or higher.

6. People who were not going to any urgent place have accepted coupons more than others (52%), higher than those going to work or home.

7. Highest number of people accepted coupons when destination within 5 mins away and they were going to Non-urgent place (about 0.27 acceptance rate)

8.  Amongst people who accepted Bar & Coffee House coupons, more coupons were offered when direction of destination was on opposite side. However, when the destination was within 15 mins, people are highly probable to accept coupons and detour to redeem coupons.
