
# Table Example
```
SELECT * FROM donations LIMIT 7;
```

<img width="843" height="259" alt="Screenshot 2025-08-26 at 10 34 52 PM" src="https://github.com/user-attachments/assets/2bcd1a20-7b5d-4988-ae4f-4c9bdfa92af0" />



### 1. Total Donations 
```
SELECT sum(gift_amount) as TOTAL_DONATIONS FROM donations;
```
<img width="153" height="67" alt="Screenshot 2025-08-26 at 10 35 08 PM" src="https://github.com/user-attachments/assets/d0339be2-aedb-4e44-8017-3484ea6c1750" />


The amount of donations totaled $6,830,130 for a period of 1 year from June 2024 to June 2025. 

### 2. What is the monthly total and monthly average of donations?
```
SELECT Year, Month, 
sum(gift_amount) AS donation_total, 
avg(gift_amount) AS avg_donations 
FROM donations
GROUP BY Year, Month
ORDER BY Year, Month;
```


<img width="860" height="404" alt="Screenshot 2025-08-26 at 10 35 42 PM" src="https://github.com/user-attachments/assets/312a741e-a071-4ac4-a2c2-8fe0ee5fa66b" />

Organized by year and month, sum of donations range from $36,045.01 to $1,349,623.52. The least amount of total donations occured in January 2025 and the highest amount of total donations occured in May 2025. Average monthly donations ranged from $655.36 from January 2025 to $28548.81 from June 2024. This might indicate that there are some factors at play. Considering the non-profit's fiscal year occurs in June, there may have been more events or new campaigns welcoming the new year impacting the range in average donation amounts. 

### 3. What is the seasonlity in donations? Do certain months perform better than others? 
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

### 4. Who are the top 5 donors? Who are the top 5 individual donors, foundation donors, and corporation donors.

```
SELECT donor_id,
sum(gift_amount) as sum_donation, 
gift_constituency, 
count(donor_id) as donation_count
FROM donations
GROUP BY donor_id
ORDER BY sum_donation DESC
LIMIT 5
```

<img width="870" height="198" alt="Screenshot 2025-08-26 at 10 27 28 PM" src="https://github.com/user-attachments/assets/a1656f87-331c-49c7-8d3c-c39958b01ccc" />

The top donors all seem to be donations made from Foundations. 
Donor 1010 donated the most money under a foundation at 5 seperate donations throughout the year. They donated a sum of $ 2,352,500. 

#### Indentifying the top 5 biggest INDIVIDUAL donors:
```
SELECT donor_id, 
sum(gift_amount) as sum_donation, 
gift_constituency, 
count(donor_id) as donation_count
FROM donations
WHERE gift_constituency = 'Individual'
GROUP BY donor_id
ORDER BY sum_donation DESC
LIMIT 5
```

<img width="821" height="198" alt="Screenshot 2025-08-26 at 10 40 59 PM" src="https://github.com/user-attachments/assets/d1493561-af29-4dc9-a614-1a924e5e6759" />

Donor 1045 was the biggest individual donor donating a total of $26048.40 with 3 donations. 

#### Indentifying the top 5 biggest CORPORATE donors:

<img width="803" height="196" alt="Screenshot 2025-08-26 at 10 43 11 PM" src="https://github.com/user-attachments/assets/5e552cff-b358-4e40-b857-7e044618abf1" />

The top corporate donor was donor 1297 with a total of $40,000 with 3 total donations. 

### 5. What is the average donation size by gift constituency?
```
SELECT gift_constituency,
ROUND(avg(gift_amount),2) as avg_donation
FROM donations
GROUP BY gift_constituency
ORDER BY avg_donation DESC
```
<img width="854" height="442" alt="Screenshot 2025-08-27 at 12 36 13 AM" src="https://github.com/user-attachments/assets/f7fc0924-86c3-4372-8479-dc55e8a15af9" />

Planned Giving donors have the highest average donation amounts at $158,821.71, followed by Foundation donations at an average donation amount of $50,618.74. 

### 6. What is the percentage of donations made by each donor type?

```
SELECT gift_constituency,
SUM(gift_amount) as total_donations, 
(SUM(gift_amount)*100.0) / (SELECT SUM(gift_amount) FROM donations) AS percentage
FROM donations
GROUP BY gift_constituency
ORDER BY percentage DESC
```

<img width="859" height="438" alt="Screenshot 2025-08-27 at 12 44 31 AM" src="https://github.com/user-attachments/assets/0cbf9943-7e93-4eb1-93fb-b72691aa1c2d" />

This query shows that ~80% of the total donations made this fiscal year came from Foundations with a total of $5517442.89 in donations. This indicates high potential for community involvement with other foundations by facilitating potential partnerships and initiatives for community support through this non-profit and partnering Foundations. Furthermore, the next highest is at the individual level indicating that people in the community care about the needs that the non-profit addresses and could potentially focus on increasing this percentage by investigating new methods of fundraising with more market research, creating more community involvement events or others. 

### 7. Where are the funds typically allocated towards? What is the percentage distribution? 

Taking a look at the fundList column, we can get a sense for where the donations are distributed towards whether it be for general operations, work development programs, aging support programs, etc. Most of the funds are directed towards general operations where funds can be allocated where they are needed rather than directed to a specific department.

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

### 8. What percentage of donations came from the top 10 donors?



# Recommendation

