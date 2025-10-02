
Stakeholder Questions: 
1. What were the total donations during the July 2024 - June 2025 time period?
2. What is the monthly total and monthly average of donations? Are there months that receive higher donations than others?
3. What is the seasonality in donations? Do certain months perform better than others? 
4. Who are the top 5 largest donors? Who are the top 5 individual donors, foundation donors, and corporation donors.
5. What is the donor retention rate month-to-month?
6. What is the average donation size by gift constituency?
7. Where are the funds typically allocated towards? What is the percentage distribution? 
8. What percentage of donations came from the top 10 donors?
9. How many donors make donations each month? Who are they?
10. How were donations accumulating throughout the year?


# Table Sample
```
SELECT * FROM donations LIMIT 7;
```

<img width="843" height="259" alt="Screenshot 2025-08-26 at 10 34 52 PM" src="https://github.com/user-attachments/assets/2bcd1a20-7b5d-4988-ae4f-4c9bdfa92af0" />


# Questions to Answer using SQL 

### 1. Total Donations and Yearly Donation Avg
```
SELECT ROUND(SUM(gift_amount),0) as TOTAL_DONATIONS,
ROUND(AVG(gift_amount),0) AS avg_donation FROM donations
```

<img width="533" height="70" alt="Screenshot 2025-09-03 at 9 20 23 PM" src="https://github.com/user-attachments/assets/89f29bba-706b-407e-a962-319fdc373cc9" />


The amount of donations totaled $6,830,130 for a period of 1 year from June 2024 to June 2025. 

### 2. What is the monthly total and monthly average of donations?
```
SELECT Year, Month, 
round(sum(gift_amount),0) AS donation_total, 
round(avg(gift_amount),0) AS avg_donations
FROM donations
GROUP BY Year, Month
ORDER BY Year, Month;
```
<img width="871" height="417" alt="Screenshot 2025-09-03 at 9 23 57 PM" src="https://github.com/user-attachments/assets/1e804a48-5ecc-4dfe-b053-a99800e73210" />

Organized by year and month, donations range from a min of $36,045 (Jan 2025) to $1,349,623 (May 2025). Average monthly donations ranged from $655.36 from January 2025 to $28548 from July 2024. 

### 3. What is the seasonality in donations? Do certain months perform better than others? 
```
WITH monthly AS (
    SELECT Year, Month,
    sum(gift_amount) AS donation_total
    FROM donations
    GROUP BY Year, Month)
SELECT Year, Month, donation_total,
RANK() OVER(ORDER BY donation_total DESC) as rank_overall
  FROM monthly
  ORDER BY rank_overall, Year, Month
```
<img width="898" height="416" alt="Screenshot 2025-08-26 at 10 37 04 PM" src="https://github.com/user-attachments/assets/cf72330a-00f3-4923-aabe-8d14221999fc" />


By ranking by the month and year, it has been found that the top 5 performing months in terms of total donations is May 2025, July 2024, June 2025, December 2024, and April 2025.  However, since the data only spans one year, it can be difficult to determine whether this is a seasonal pattern in donation behaviour and would require more data collection. It is also important to possibly consider the events that were running during these times as they may have an impact on the donation amounts. 

### 4. Who are the top 5 donors and at what frequency do they donate? Who are the top 5 individual donors, foundation donors, and corporation donors.

```
SELECT donor_id, 
gift_constituency, 
sum(gift_amount) as sum_donation, 
count(donor_id) as donation_count
FROM donations
GROUP BY donor_id
ORDER BY sum_donation DESC
LIMIT 5
```
<img width="850" height="191" alt="Screenshot 2025-09-03 at 9 26 00 PM" src="https://github.com/user-attachments/assets/f3839e5b-fa37-48b1-be1a-f09d2756f9de" />


The top donors all seem to be donations made by Foundations. 
Donor 1010 donated the most money under a foundation at 5 seperate donations throughout the year. They donated a sum of $2,352,500. 

#### Indentifying the top 5 biggest INDIVIDUAL donors:
```
SELECT donor_id, 
gift_constituency, 
sum(gift_amount) as sum_donation, 
count(donor_id) as donation_count
FROM donations
WHERE gift_constituency = 'Individual'
GROUP BY donor_id
ORDER BY sum_donation DESC
LIMIT 5
```

<img width="863" height="190" alt="Screenshot 2025-09-03 at 9 28 29 PM" src="https://github.com/user-attachments/assets/c8d6504b-0884-4f02-a7b7-0f5fd79f9375" />

Donor 1045 was the biggest individual donor donating a total of $26048.40 with 3 donations. 

#### Indentifying the top 5 biggest CORPORATE donors:
```
SELECT donor_id, 
gift_constituency, 
sum(gift_amount) as sum_donation, 
count(donor_id) as donation_count
FROM donations
WHERE gift_constituency = 'Corporation/Vendor/Business'
GROUP BY donor_id
ORDER BY sum_donation DESC
LIMIT 5
```
<img width="882" height="199" alt="Screenshot 2025-09-03 at 9 29 01 PM" src="https://github.com/user-attachments/assets/723a9289-3fe3-49ed-ba15-6a6c550d92ad" />


The top corporate donor was donor 1297 with a total of $40,000 with 3 donations. 

### 5. What is the total and average donation size by gift constituency and what percentage of the total donations do they occupy? How diverse are the donations by gift constituency.
```
SELECT gift_constituency,
SUM(gift_amount) as total_donations, 
ROUND((SUM(gift_amount)*100.0) / (SELECT SUM(gift_amount) FROM donations),2) AS percentage
FROM donations
GROUP BY gift_constituency
ORDER BY percentage DESC
```
<img width="934" height="445" alt="Screenshot 2025-09-03 at 9 31 58 PM" src="https://github.com/user-attachments/assets/211398bc-1194-44ba-af98-d16417cd2465" />


Planned Giving donors have the highest average donation amounts at $158,821.71, followed by Foundation donations at an average donation amount of $50,618.74. However, foundation donations comprise of 80% of the total donations indicating high potential for partnerships with these foundations and the non-profit. 
Furthermore, the next highest is at the **individual level** indicating that people in the community care about the needs that the non-profit addresses and the non-profit could potentially focus on increasing this percentage by investigating new methods of fundraising through market research, creating more community involvement events or social media campaigns. 

### 7. Where are the funds typically allocated towards? What is the percentage distribution? 

Taking a look at the fundList column, we can get a sense for where donations are distributed towards whether it be for general operations, work development programs, aging support programs, etc. Most of the funds are directed towards general operations where funds can be allocated where they are needed rather than directed to a specific department.

```
SELECT fund_list,
SUM(gift_amount) as total_donations, 
ROUND((SUM(gift_amount)*100.0) / (SELECT SUM(gift_amount) FROM donations),4) AS percentage
FROM donations
GROUP BY fund_list
ORDER BY percentage DESC
```

<img width="933" height="596" alt="Screenshot 2025-08-27 at 9 55 31 AM" src="https://github.com/user-attachments/assets/d7b1c9b9-30e4-4ceb-bb3b-99f3421dc613" />

This shows that ~74% of the donations are typically allocated towards general operations, followed by 11% of the donations allocated towards the SUPHS department.

8. What percentage of donations came from the top 10 donors?

```
-- table for total donations
WITH donor_totals AS (
    SELECT donor_id, SUM(gift_amount) AS total_donated
    FROM donations
    GROUP BY donor_id
), -- top 10 donors
top10 AS (
    SELECT donor_id, total_donated
    FROM donor_totals
    ORDER BY total_donated DESC
    LIMIT 10
), -- grand total
all_totals AS (
    SELECT SUM(gift_amount) AS grand_total
    FROM donations
), --top 10 total
top10_totals AS (
    SELECT SUM(total_donated) AS top10_total
    FROM top10
) --calculates the percentage
SELECT 
    (CAST(top10_total AS FLOAT) / grand_total) * 100 AS pct_from_top10
FROM top10_totals, all_totals;
```
<img width="124" height="66" alt="Screenshot 2025-09-03 at 9 45 29 PM" src="https://github.com/user-attachments/assets/a9676a00-1900-41cd-82a3-b280dccef819" />

The top 10 donors donated ~80% of our total donations for the 2024-2025 Fiscal Year 

9. How many donors make donations each month? Who are they?
```
WITH total_months AS (
SELECT COUNT(DISTINCT printf('%04d-%02d', Year, Month)) AS n_months
FROM donations
),
donor_months AS (
SELECT donor_id, gift_constituency, sum(gift_amount) AS total,
COUNT(DISTINCT printf('%04d-%02d', Year, Month)) AS months_donated
FROM donations
GROUP BY donor_id
)
SELECT d.donor_id, d.gift_constituency, d.months_donated, d.total
FROM donor_months d
CROSS JOIN total_months t
WHERE d.months_donated = t.n_months;
```
<img width="840" height="699" alt="Screenshot 2025-09-03 at 10 19 53 PM" src="https://github.com/user-attachments/assets/e7dbbf15-fa7d-43a4-8466-ff492de75381" />

10. How were donations accumulating throughout the year?

```
SELECT 
  month, Year,
  round(SUM(gift_amount),0) AS monthly_total,
  SUM(SUM(gift_amount)) OVER (ORDER BY Year, month) AS running_total
FROM donations
GROUP BY month, Year
ORDER BY Year, month
```
<img width="936" height="416" alt="Screenshot 2025-10-02 at 1 01 17 PM" src="https://github.com/user-attachments/assets/34af3508-ec5c-4922-85a6-9198b00f2403" />

There was an accumulated total of $6.8M in donations by June 2025.

