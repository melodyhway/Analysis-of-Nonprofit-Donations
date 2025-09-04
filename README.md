# Project Background

This project analyzes non-profit donations for an organization that serves the San Francisco Bay Area. The data contains records of donations made from July 2024 to June 2025 including data on donation dates, donation amounts, donor id, donor type, campaign id, fund allocation destination, records for recurring or annual donations. This project aims to use Excel, SQL, and Tableau to discover how donations are allocated, donation sources, and investigating the effectiveness of different events in gathering donations. This project will also help identify the biggest donors in the system and identify seasonal patterns in donations to better understand donation patterns and increase future fundraising efforts during certain times like holidays or hosted events. 


## Data Structure and Data Validation
The donations contains 1066 records on the donations made during the July 2024 - 2025 fiscal year. It contains the following columns. 

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

An analysis of donations made during July 2024 to June 2025 found that a total of $6.83 M were donated to our non-profit organization. The top performing months occurred during May 2025, July 2024, June 2025, and December 2024. A large portion of donations were made by Foundation donors, followed by Individual donors. Some events hosted during these high impact months also certainly have an impact on donation amounts such as hosted galas, or holiday season donations. Notably, in May, the Chef Gala increased funding efforts resulting in a peak in donation volume and amount. Throughout this project, we will uncover inisghts about donor types, campaigns, and events in order to gain a better understanding of the July 2024 - 2025 donation performance. We will also learn how donations are allocated towards different departments throughout the organization. Using this data, we can make data-informed recommendations for our organization for fundraising strategies, media campaigns, and increasing donation efforts for future years as well as ensure that we mitigate donations risks by diversifying potential donor types. 


## Dashboard Overview 
<img width="1998" height="1598" alt="offical dashboard" src="https://github.com/user-attachments/assets/8df050ac-2325-443c-86e4-2a085f1f29f9" />




### Overall Donation Trends

Taking a look at the overall donation trends, we see that July 2024, May 2025, and June 2025 performed exceptionally well compared to other months. Notably, the donor counts vary quite widely across these top performing months. 
* We see that May received 227 donations, whereas July 2024, with similar donation totals only received 47 donations.
* Even though December had a relatively high volume of donations, it didn't receive the same donations amounts as compared to May and June.
* This relationship between total donations and volume could be further explored by examining the campaigns that occurred during these months. 

<img width="2394" height="1590" alt="Monthly donation amt and volume" src="https://github.com/user-attachments/assets/4ada15b1-b609-4ffd-ac5f-a41583a3c079" />


### Month over Month Changes in Donations 

<img width="2704" height="302" alt="percentage change in donation amount" src="https://github.com/user-attachments/assets/edf2dd8f-fda9-45c6-8a58-a66c7c459805" />

* There were strong fluctuations in donations throughout the year.
  
* The July fiscal year starts off strong with a total donation amount of $1.3M but over the next following months, donations had decreased quite a bit compared to the beginning of the year. During the holiday season (i.e., November and December), we again see a strong increase in donations with close to $1M in donations seeing a 302% increase in total donations.
  
* In the new year, donations again slowed down but picked right back up in April and May 2025 with May donations increasing by 801% from the previous month.
  
### Month over Month Changes in Donation Volume

<img width="2224" height="342" alt="Percentage Change in Donation Volume" src="https://github.com/user-attachments/assets/1c53d001-2ca1-4158-935e-8b18a75563dd" />


* Analyzing donation volumes, we again see similar fluctuation patterns.
* We see a peak in total donation volume in May and another peak in December. This can be explained by the hosted Chef Gala in May and common holiday operations in December.
* These peaks show how campaingn events can impact our donations throughout the year. It could be important to consider how we can implement smaller scale campaigns to encourage further donations throughout the year, especially during low donations times. 


#### Digging Deeper into May and December

Donations/donation volume peaked in May 2025 and it seems that a portion of donations were made in support of the Chef Gala to support educational and workforce programs. This graph shows how the Chef Gala accounted for $261,510 of donations made during May 2025. However, it only accounts for a small portion of the total May donations. 

<img width="2116" height="1642" alt="Sheet 36 (1)" src="https://github.com/user-attachments/assets/72860ab1-561b-4bea-89e8-8c8f1c3ab3a9" />

* We see that there was a total of 181 donations made towards the chef gala accounting for 19% of donations made during May 2025. The other 81% are other donation types not accounted for in the Chef Gala function.
* The high volume of donations is explained by the Chef Gala where donations made were likely made in small amounts through ticket sales or merchandise sales.

# Donor Insights

<img width="1998" height="1598" alt="Donor Type Breakdown" src="https://github.com/user-attachments/assets/e6dd5a9f-c07d-443b-a60c-93944b1498dc" />

* 80% of donations are covered by foundations
  
* 7.22% are made by Individual donors.
  
* Foundations are largest donors to the non-profit allowing for the organization to host new events in partnership, increasing donation efforts. Interestingly, because Individuals are the next highest percentage, it is important to acknowledge the strong impacts that individual donors make on the organization. This means that the organization could further individual funding efforts through community outreach efforts using social media, or in person fundraising methods. 

* Planned Giving donations are often one-time gifts made in advance following a donor plan. Since it is a one off donation, further analysis may not yield significant results. Therefore, we will only focus on our top three constituent types: Foundation, Individual, and Corporate Donors. 
  
# Top Donors and Recurring Donors

Our recurring donors, defined by the donations made monthly throughout the year, were comprised of corporation, individual, and foundation donors. Most recurring monthly donations were made by Individual donor types. These donations tend to be smaller monthly amounts but over time, add up to account for a relatively strong portion of our total donations. It shows that Individual donors are still very important in our campaigning efforts as they are more likely to donate every month and continue demonstrating support for our cause.

<img width="1998" height="1598" alt="Recurring Donation Distribution" src="https://github.com/user-attachments/assets/c680b730-0ea6-4786-b07a-0f73b4d3e5a4" />

* Donor 1002, a foundation donor, donated 11 times over the year accounting for 772K in total donations.
* From the top donors chart, we see that donor 1010 donated over $2M but with 5 donations over the year. 
  
## Top Donors by Type

<img width="2104" height="640" alt="Top Foundations Donors" src="https://github.com/user-attachments/assets/ce142188-5614-47a4-ae2a-f7b1e15f434a" />

<img width="2104" height="640" alt="Top Individual Donors" src="https://github.com/user-attachments/assets/a76c557a-d1f7-4f44-90d8-a649c20c0269" />

<img width="2104" height="640" alt="Top Corporate Donors" src="https://github.com/user-attachments/assets/53f8a95d-a39e-404c-a54d-93afac5222be" />

In identifying our top 10 donors by donation type, it is important to go the extra step in thanking these donors for their contributions. 

## Overall Donation Allocation 

Most donations are designated towards general operations. $5M were reserved for general operations and $784K (about 11%) of donations were directed towards the SUPHS departments. 

<img width="2450" height="1590" alt="pie fund allocation (2)" src="https://github.com/user-attachments/assets/c650ed4a-0160-4005-8682-2a56a226135c" />

# Recommendations

### Diversify our donor base

* Foundation donors contribute 80% of total donations indicating strong relationships with Foundation partners. This could mean that we should containue to foster these relationships to continue partnerships and collaboration across the organization. However, since it does make up such a large portion of our donations, there is a risk that if we lose a partnership with some of the foundations, we risk a large portion of future donations. 
* Individual donors, while contributing smaller amounts each donation, still make up a large portion of donations and are important in the sustainability of the organization's fundraising efforts.
* We could increase outreach through community events, social media campaigns, or peer-to-peer fundraising to reach a larger variety of individual donors.
* It would increase the sustainability and diversify our donor portfolio rather than solely relying on Foundation donors.

### Work with our Recurring Donors
* Recurring donors have already shown strong engagement with our organization.
* We could increase appeal to our donors through personalized thank-yous, demonstrate appreciation, and provide updates on the impact of their donation. This increases donor retention and can possibly increase donor involvement in our program.

### Campaigns and Seasonal Strategies

* Events such as the Holiday Gift Drive or Chef Gala encourage seasonal peaks in donations that the organization could build on by hosting similar events throughout the year in support of a variety of fundraising efforts.
* We could work more effectively with marketing and donation teams to increase fundraising efforts especially with our individual donors.
  * For example, during the slower months, we could launch smaller, seasonally focused social media campaigns to encourage further involvement with the community. This would take less budget while still encouraging people to participate in fundraising efforts, further increasing donations throughout the year. 

### Demonstrate Donation Impacts

* Donors like to see how their donation has helped the organization so I recommend creating **impact stories** of how donations were distributed to different programs to encourage community involvement. Whether it be through news articles, social media updates on new program intiatives, or media demonstrating the impact of the donations, smaller community campaigns could drive retention and involvement in our organization.


Stakeholder Questions: 
1. What were the total donations during the July 2024 - June 2025 time period?
2. What is the monthly total and monthly average of donations? Are there months that receive higher donations than others?
3. What is the seasonlity in donations? Do certain months perform better than others? 
4. Who are the top 5 largest donors? Who are the top 5 individual donors, foundation donors, and corporation donors.
5. What is the donor retention rate month-to-month?
6. What is the average donation size by gift constituency?
7. Where are the funds typically allocated towards? What is the percentage distribution? 
8. What percentage of donations came from the top 10 donors?
9. How diverse are the donations? Meaning what portion of donations were made by individuals, corporations, and foundations? Is there a need to diversify?
10. Which campaigns were more effective in getting donations?
