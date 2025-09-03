# Project Background

This project analyzes non-profit donations for an organization that serves the San Francisco Bay Area. The data contains records of donations made from June 2024 to June 2025 including data on donation dates, donation amounts, donor id, donor type, campaign id, fund allocation destination, records for recurring or annual donations. This project aims to use Excel, SQL, and Tableau to discover how donations are allocated, donation sources, investigating the effectiveness of different events in gathering donations. This project will also help identify the biggest donors in the system and identify seasonal patterns in donations to better understand donation patterns and increase future fundraising efforts during certain times like holidays or hosted events. 

Summary:
## Insights and Recommendations 


## Data Structure and Data Validation
The donations contains 1066 records on the donations made during the June 2024 - 2025 fiscal year. It contains the following columns. 

| Column Name | Data Type | Descriptor |
| :------- | :------: | :-------|
| Gift_Date  | Date  | Donation Date |
| Gift_Amount| float  | Donation Amount (USD)|
| Donor_id | string  | Donor (anonymized) |
| Gift_Constituency | string  | Donor Type (individual, foundation, corporation, etc) |
| Campaign_id| string  | AN24/AN25 |
| Fund List| string  | Donation Allocation data |
| Appeal List| string  | Information on recurring or annual donations |

### Caveats with the data
While the data contains a rich variety of information, there were several instances of data logging errors including misaligned dates, total donation calculations, duplicate columns, errors, and blank values. These issues were addressed using data cleaning methods through Excel. 

A log of fixes can be found [here](https://github.com/melodyhway/Donations-Analysis-using-SQL/blob/ec97ac7fdaa82c0d7fb66a9f593de10ed51d0878/datafixes.md)


An Interactive Tableau Dashboard can be found [here](https://public.tableau.com/views/Analysisofnon-profitdonations/Non-ProfitDonationsDashboard2?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link](https://public.tableau.com/views/Analysisofnon-profitdonations/Non-ProfitDonationsDashboard2?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)](https://public.tableau.com/views/Analysisofnon-profitdonations/Non-ProfitDonationsDashboard2?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)).


Find the SQL queries for answers to specific questions [here](https://github.com/melodyhway/Donations-Analysis-using-SQL/blob/8f98b82866f7878f72b89d0c21ab47cf334d4a83/SQLqueries.md)

# Overview of Findings 
This dataset on the donations made during June 2024 to June 2025 found that a total of $6.83 M was donated to the organization. The top performing months occured during May 2025, June 2024, June 2025, and December 2024. A large portion of donations were made by Foundation donors indicating possible partnerships that could further increase donation efforts. Some events hosted during these high impacts months also certaintly have an impact on donation amounts such as hosted galas, or holiday season donations. Notably, in May, the Chef Gala increased funding efforts resulting in a peak in donation volume. Throughout this project, we will uncover inisghts about donor types, campaigns, and events in order to gain a better understanding of the June 2024 - 2025 donation performance. We will also learn how donations are allocated towards different departments throghout the organization. 

\{Summary of Findings after being done\}

## Dashboard Overview 

<img width="1998" height="1598" alt="Non-Profit Donations Dashboard (2)" src="https://github.com/user-attachments/assets/db76b78c-8f25-4107-99bf-eb4474ca3c52" />


### Overall Donation Trends

Taking a look at the overall donation trends, we see that June 2024, May 2025, and June 2025 performed exceptionally well compared to other months. Notably, the donor counts vary quite widely across these top performing months. We see that May received 203 unqiue donations where June 2024, at similar donation totals, received only 46 unique donations. This is interesting as we investigate further into the events, distribtuion of donor type, or even the introduction of a new partnership. Furthermore, even though December had a high volume of donations, it didn't receive the same total amounts as compared to May and June.

<img width="1802" height="1590" alt="monthly donations" src="https://github.com/user-attachments/assets/1c51d89f-a1a8-4f63-b217-e5fdbe8805d1" />

### Month over Month Changes in donations and donors

<img width="2704" height="302" alt="percentage change in donation amount" src="https://github.com/user-attachments/assets/edf2dd8f-fda9-45c6-8a58-a66c7c459805" />

* There were strong fluctuations in donations throughout the year.
  
* The June fiscal year starts off strong with a total donation amount of $1,341,794 but over the next following months, donations had decreased quite a bit compared to July 2024. During the holiday season (ie November and December) we see a strong increase in donations. Notably, December 2024 experienced a 302% increase in donations.
  
* In the new year, donations again slowed down but picked right back up in April and May 2025 with May donations increasing by 801.59%.
  
### Donor Fluctuations

<img width="2224" height="342" alt="Percentage Change in Donation Volume" src="https://github.com/user-attachments/assets/1c53d001-2ca1-4158-935e-8b18a75563dd" />


* Analyzing the donation volumes, we again see a similar pattern in fluctuations.

* There is a peak in total donation volume in May and another peak in donation volume in December.

* Knowing that the Chef Gala was hosted in May, it would explain the higher number of donations as compared to the other months. Furthermore, reasonably, during holiday times like in the December months, increased fundraising efforts and holiday activities could also explain why donation volume increased. 


#### Impacts of certain events like Chef Gala, Holiday Gift Drive.

Donations peaked in May 2025 and it seems that a portion of donations were made made in support of the Chef Gala designed to support educational and workforce programs. This graph shows how the chef gala accounted for $261,510 of donations made during May 2025. The rest are a variety of funding efforts from different organizations. 

<img width="2106" height="1590" alt="chef gala fundraising efforts" src="https://github.com/user-attachments/assets/8cf79012-1367-4aad-81cf-c7bec6c52625" />

* 80% of donations are covered by foundations
  
* 7.22% made by Individual donors.
  
* Foundations are likely the largest partners in the non-profit allowing for the organization to host new events in partnership oundations increasing donation efforts. Interestingly, because Individuals are the next highest percentage, it is important to acknowledge the strong impacts that individual donors make on the organization. This means that the organization could further individual funding efforts through community outreach efforts using social media, or in person fundraising methods. 

<p align = "middle">
  <img width="450" height = "700" alt = "Monthly Donor Distribution" src="https://github.com/user-attachments/assets/875ba0bb-89f5-4c31-bf10-cb0a4ef64b0d" />
  <img width="450" height = "700" alt = "Total Donor Distribution" src="https://github.com/user-attachments/assets/9e481305-cc06-4749-b587-9d5ae949dbd5" />
</p>




## Overall donation Allocation 

Most donations are designated towards general operations. $5 M were reserved for general operations and $784K (about 11%) of donations were directed towards the SUPHS departments. 

<img width="2450" height="1590" alt="pie fund allocation (2)" src="https://github.com/user-attachments/assets/c650ed4a-0160-4005-8682-2a56a226135c" />

# Top Donors and Recurring Donors

Our recurring donors, where recurring counts as donations made monthly over the year, were comprised of corporation, individual, and foundation donors. Most monthly donations were made by Individual donor types. Due to the nature of Individual donors, these tend to be smaller monthly amounts accounting for the smaller portion of the total donation amount. However, it does show that individual donors are still very important in our campaigning efforts.

<img width="804" height="1328" alt="Recurring Donors" src="https://github.com/user-attachments/assets/bf83ec4f-878f-4be1-acd9-ee2901357cdf" />


# Recommendations

* make recommendations based on the data. focus on what donor types, can we encourage more foundation donors, individual donors?

* what can we look for in donations

* can we host more events during down times.

* work with marketing and fundraising teams to increase donations 

Stakeholder Questions: 
1. What were the total donations during the June 2024 - June 2025 time period?
2. What is the monthly total and monthly average of donations? Are there months that receive higher donations than others?
3. What is the seasonlity in donations? Do certain months perform better than others? 
4. Who are the top 5 largest donors? Who are the top 5 individual donors, foundation donors, and corporation donors.
5. What is the average donation size by gift constituency?
6. Where are the funds typically allocated towards? What is the percentage distribution? 
7. What percentage of donations came from the top 10 donors?
8. How diverse are the donations? Meaning what portion of donations were made by individuals, corporations, and foundations? Is there a need to diversify?
9. Which campaigns were more effective in getting donations?
