# Project Background

This project analyzes non-profit donations for an organization that serves the San Francisco Bay Area. The data contains records of donations made from July 2024 to June 2025 including data on donation dates, donation amounts, donor id, donor type, campaign id, fund allocation destination, records for recurring or annual donations. This project aims to use Excel, SQL, and Tableau to discover how donations are allocated, donation sources, investigating the effectiveness of different events in gathering donations. This project will also help identify the biggest donors in the system and identify seasonal patterns in donations to better understand donation patterns and increase future fundraising efforts during certain times like holidays or hosted events. 

Summary:
## Insights and Recommendations 


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
An analysis of donations made during July 2024 to June 2025 found that a total of $6.83 M were donated to this non-profit organization. The top performing months occurred during May 2025, July 2024, June 2025, and December 2024. A large portion of donations were made by Foundation donors, followed by Individual donors. Some events hosted during these high impact months also certainly have an impact on donation amounts such as hosted galas, or holiday season donations. Notably, in May, the Chef Gala increased funding efforts resulting in a peak in donation volume and amount. Throughout this project, we will uncover inisghts about donor types, campaigns, and events in order to gain a better understanding of the July 2024 - 2025 donation performance. We will also learn how donations are allocated towards different departments throughout the organization. Using this data, we can make data-informed recommendations for our organization for fundraising strategies and increasing donation efforts for future years. 


## Dashboard Overview 

<img width="1998" height="1598" alt="Non-Profit Donations Dashboard (2)" src="https://github.com/user-attachments/assets/db76b78c-8f25-4107-99bf-eb4474ca3c52" />


### Overall Donation Trends

Taking a look at the overall donation trends, we see that July 2024, May 2025, and June 2025 performed exceptionally well compared to other months. Notably, the donor counts vary quite widely across these top performing months. We see that May received 203 unique donations where June 2024, at similar donation totals, received only 46 unique donations. This is interesting as we investigate further into the events, distribtuion of donor type, or even the introduction of a new partnership. Furthermore, even though December had a high volume of donations, it didn't receive the same total amounts as compared to May and June.

<img width="1802" height="1590" alt="monthly donations" src="https://github.com/user-attachments/assets/1c51d89f-a1a8-4f63-b217-e5fdbe8805d1" />

### Month over Month Changes in Donations 

<img width="2704" height="302" alt="percentage change in donation amount" src="https://github.com/user-attachments/assets/edf2dd8f-fda9-45c6-8a58-a66c7c459805" />

* There were strong fluctuations in donations throughout the year.
  
* The June fiscal year starts off strong with a total donation amount of $1,341,794 but over the next following months, donations had decreased quite a bit compared to July 2024. During the holiday season (ie November and December) we see a strong increase in donations. Notably, December 2024 experienced a 302% increase in donations.
  
* In the new year, donations again slowed down but picked right back up in April and May 2025 with May donations increasing by 801.59%.
  
### Month over Month Changes in Donation Volume

<img width="2224" height="342" alt="Percentage Change in Donation Volume" src="https://github.com/user-attachments/assets/1c53d001-2ca1-4158-935e-8b18a75563dd" />


* Analyzing the donation volumes, we again see similar fluctuation patterns.
* We see a peak in total donation volume in May and another peak in December. This can be explained by the hosted Chef Gala in May and holiday operations in December.
* These peaks show how campaing events can impact our donations throughout the year. It could be important to consider how we can implement smaller scale campaigns to encourage further donations throughout the year, especially during low donations times. 


#### Impacts of certain events like Chef Gala, Holiday Gift Drive.

Donations peaked in May 2025 and it seems that a portion of donations were made made in support of the Chef Gala designed to support educational and workforce programs. This graph shows how the chef gala accounted for $261,510 of donations made during May 2025. The rest are a variety of funding efforts from different organizations. 

<img width="2106" height="1590" alt="chef gala fundraising efforts" src="https://github.com/user-attachments/assets/8cf79012-1367-4aad-81cf-c7bec6c52625" />


# Donor Insights

* 80% of donations are covered by foundations
  
* 7.22% are made by Individual donors.
  
* Foundations are likely the largest partners in the non-profit allowing for the organization to host new events in partnership increasing donation efforts. Interestingly, because Individuals are the next highest percentage, it is important to acknowledge the strong impacts that individual donors make on the organization. This means that the organization could further individual funding efforts through community outreach efforts using social media, or in person fundraising methods. 

<p align = "middle">
  <img width="450" height = "700" alt = "Monthly Donor Distribution" src="https://github.com/user-attachments/assets/875ba0bb-89f5-4c31-bf10-cb0a4ef64b0d" />
  <img width="450" height = "700" alt = "Total Donor Distribution" src="https://github.com/user-attachments/assets/9e481305-cc06-4749-b587-9d5ae949dbd5" />
</p>

# Top Donors and Recurring Donors

Our recurring donors, defined by the donations made monthly throughout the year, were comprised of corporation, individual, and foundation donors. Most recurring monthly donations were made by Individual donor types. These donations tend to be smaller monthly amounts but over time but add up to account for a relatively strong portion of our total donations. It does show that individual donors are still very important in our campaigning efforts as they are more likely to donate every month and continue demonstrating support for our cause.


<img width="1998" height="1598" alt="Dashboard 3" src="https://github.com/user-attachments/assets/16577993-7022-4efa-9dc9-747b86a3f2d9" />

## Top Donors by Type

<img width="1916" height="640" alt="Top Foundation Donors" src="https://github.com/user-attachments/assets/2f8b34f9-5090-4a05-aabe-3a40843d6012" />

<img width="1916" height="640" alt="Top Individual Donors" src="https://github.com/user-attachments/assets/4178d7f6-f543-437c-b96d-125278fbf0b1" />

<img width="1916" height="640" alt="Top Corporate Donors" src="https://github.com/user-attachments/assets/24811b5c-d677-44d4-b4ec-04fa83d829aa" />

This data could help identify our largest donors and partnerships. We may want to work with the donations team to show appreciation for the donors that show up for the organization in this way. 

## Overall Donation Allocation 

Most donations are designated towards general operations. $5M were reserved for general operations and $784K (about 11%) of donations were directed towards the SUPHS departments. 

<img width="2450" height="1590" alt="pie fund allocation (2)" src="https://github.com/user-attachments/assets/c650ed4a-0160-4005-8682-2a56a226135c" />



# Recommendations

### Diversify our donor base

* Foundation donors contribute 80% of total donations indicating strong relationships with Foundation partners. This could mean that we should containue to foster these relationships to continue partnerships and collaboration across the organization. However, since it does make up such a large portion of our donations, there is a risk that if we lose a partnership with some of the foundations, we risk a large portion of future donations. 
* Individual donors, while contributing smaller amounts each donation, still make up a large portion of donations.
* We could increase outreach through community events, social media campaigns, or peer-to-peer fundraising to reach a larger variety of individual donors.
* It would increase the sustainability and diversify our donor portfolio rather than solely relying on Foundation donors.

### Work with our Recurring Donors
* Recurring donors have already shown strong engagement with our organization.
* We could increase our efforts in showing appreciation to our donors through personalized thank-yous, demonstrate appreciation, and provide updates on the impact of their donation. This increases donor retention and can possibly increase donor involvement in our program. 


### Campaigns and Seasonal Strategies

* Events such as the Holiday Gift Drive or Chef Galas encourage seasonal peaks in donations that the organization could build on by hosting similar events throughout the year in support of a variety of fundraising efforts.
* We could work more effectively with marketing and donation teams to increase fundraising efforts especially with our individual donors.
  * For example, during the slower months, we could launch smaller, seasonally focused social media campaigns to encourage further involvement with the community. This would take less budget while still encouraging people to participate in fundraising efforts, further increasing donations throughout the year. 

### Demonstrate donation impacts

* Donors like to see how their donation has helped the organization so I recommend creating **impact stories** of how donations were distributed to different programs to encourage community involvement whether it be through news articles, or social media updates on new program intiatives, media demonstrating the impact of the donations could drive retention and involvement in the non-profit organization.
* 

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
