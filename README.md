# Fundraising Impacts: Trends, Donors & Campaigns
# Executive Summary

I analyzed and created a dashboard to gain insights into the donations made to a non-profit organization. The goal was to identify donation trends, campaign effectiveness, fund allocation, identify the biggest donors to the organization, and uncover patterns and anomalies in donations. The aim of this project is to better understand how donations are made, develop a plan to encourage and sustain community support, and provide insights on campaign improvements and fundraising efforts for the organization. With over $6M in donations, this project provides insight into the organization's fundraising efforts to support the organization's goals in supporting workforce development. 

## Key Findings

* Total Donation Amount: **$6.83M**
* Total Donation Volume: **1066**
* Avg Donation Amount: $6,407
* Median Donation Amount: $127
* Best Performing Months: June, May, December, July
* Top Foundation Donors: 1010, 1002, 1049
* Top Individual Donors: 1045, 1523, 1037
* Campaign Successes: May Gala garnered over $219K in donations contributing to the highest donation amount of the year at 1.3M in May.

## Recommendations Summary

* diversify campaigns and encourage donor diversity increase organization's sustainability, especially working to encourage more individual donors.
* implement smaller social media and peer-to-peer campaigns to encourage donations during "off" months.
* demonstrate impact on social media to donors and interested parties to demonstrate the work that is being done and how donations are being used for the causes that people care about. 

# The Problem
In the non-profit sector, understanding and gathering donations is essential for sustaining operations. By indentifying patterns in doantion growth and decline, it provides critical insights to help organizations better support their communities and initiatives.

Suppose this is an organization focuses on supporting workforce development, with donations funding programs that help people build employable skills and support aging populations. To ensure that these programs are effective, funding must be tracked and analyzed, enabling campaign strategies and allocation decisions throughout the year and ensure sucessful operations. 

How can we increase donations throughout the year, what and when should campaigns be implemented to encourage donations? Who are the organization's biggest supporters and how can we encourage more support and leverage the organization's resources in an effective manner?

# Background

The data contains records of donations made from July 2024 to June 2025 and uses Excel, SQL, and Tableau to uncover insights into the organization's donations.

## Data Structure
The data contains 1,066 records on donations made during the 2024-2025 fiscal year with the following columns:

<img width="333" height="444" alt="data structure" src="https://github.com/user-attachments/assets/d8ca3d56-14b6-403b-b0d2-c7fba339d789" />

### Data Cleaning 
There were several instances of data logging errors including misaligned dates, total donation calculations, duplicate columns, errors, and blank values. These issues were addressed using data cleaning methods through Excel. 

A log of fixes can be found [here](https://github.com/melodyhway/Donations-Analysis-using-SQL/blob/ec97ac7fdaa82c0d7fb66a9f593de10ed51d0878/datafixes.md).


An Interactive Tableau Dashboard can be found [here](https://public.tableau.com/views/Analysisofnon-profitdonations/Dashboard5?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

Find the SQL queries for answers to specific stakeholder questions [here](https://github.com/melodyhway/Donations-Analysis-using-SQL/blob/8f98b82866f7878f72b89d0c21ab47cf334d4a83/SQLqueries.md).


# Overview

A total of $6.83M was donated to our non-profit organization in the July 2024-June 2025 FY. The top-performing months occurred during May 2025, July 2024, December 2024, June 2025. Foundation donors made up the largest portion of donations followed by Individual donations. Gala and holiday events certainly have an impact on the donations made to the org. Notably, in May, the hosted Gala resulted in a peak in donation volume and amount. By diving deeper into insights into donor types, campaigns, and funding efforts for the organization, we can better understand the needs of the organization in increasing fundraising efforts to cover the organization's needs. Using this data, we can make data-informed recommendations for our organization for future fundraising strategies, media campaigns, and increasing donation efforts and diversifying potential donor types to maintain the organization's sustainability in supporting its community.


# Dashboard Overview 
<p align="center">
<img width="3198" height="1798" alt="Dashboard" src="https://github.com/user-attachments/assets/c2948bdf-b1b1-4814-9e98-9b9b508c23c4" />

</p>


# Insights and Analysis

### Overall Donation Trends
<p align="center">
  <img width="60%" class="center" alt="monthly donations" src="https://github.com/user-attachments/assets/a168418d-09c2-415f-acb8-6e660069431b" >
</p>


**July 2024, May 2025**, and **June 2025** performed exceptionally well with over $1M in donations per month. However, donation volume fluctuates a lot across these months. 

* May received 227 donations, whereas in July 2024, with similar totals, received only 47 donations.
* Even though December had a relatively high volume of donations, the total donations did not reach the same peaks as May and June.
* It is suspected that year beginning and year end events/donations may contribute to these month's successes. 


### Month-over-Month Changes in Donations 

<table >
  <tr>
    <td style="vertical-align: top; width: 50%;">
      <img src="https://github.com/user-attachments/assets/9d14e369-fd40-4a13-b060-4d8108aa82db"
           alt="MoM Change in Donations"
           width="100%">
    </td>
    <td style="vertical-align: top; padding-left: 20px;">
      <p>
        This chart shows the month-over-month change in donations.  
        <ul>
          <li>July starts off strong with 1.3M in donations. However, donations significantly dipped in the following months. </li>
          <li>In December, donations significantly increased by 402% likely due to Holiday events and gifting.</li>
          <li>Once again, in the year calendar year, donations dipped by hit the highest monthly change in April and Continued to grow in May. </li>
          <li>May reports the highest donation total with a 149% growth in donations from April. </li>
        </ul>
      </p>
    </td>
  </tr>
</table>

  
### Month-over-Month Changes in Donation Volume


<table>
  <tr>
    <td style="vertical-align: top; width: 50%; padding-right:16px;">
      <img
        src="https://github.com/user-attachments/assets/cdc26357-71d3-4757-8f55-bc4d82fdfb20"
        alt="MoM Change in Volume (1)"
        style="width:100%; height:auto; max-height:640px; object-fit:contain;">
    </td>
    <td>
      <p>This chart shows the month-over-month change in donation volume. </p>
      <ul>
          <li>Donations in the beginning of the fiscal year stayed consistent with ~40 unique donors in July-September. </li>
          <li>There was a steady increase in donation volume from Oct - Dec. However with consistent donor growth, donation amounts did not reach its peak.</li>
          <li>Donations volume vary widely in Jan - April. </li>
          <li>May reports the highest donation volume with a 149% growth with 227 donations made. 
            <ul>
              <li>May had 227 donations with a high of $1.3M. This is due to a gala event that encouraged more individual donations through ticket sales and gifts in support of the hosted event.</li>
            </ul>
          <li>Larger campaigns and events bring in more donors but smaller campaigns can bring in more consistent small donations which sustain the organization throughout the year. </li>
        <ul>
           <li> I recommend smaller scale campaigns throguhout the year especially in slow months, like January and Februrary to encourage smaller donations to help sustain and develop the organization's programs.</li>
          <li>Deploying small social media campaigns, especially during off season times can encourage further community involvement from small donations or social support </li>
        </ul>
      </ul>
    </td>
  </tr>
</table>



## May 2025

Why did May 2025 receive so many donations in terms of amount and volume? And what attributed to these increases?

Donations/donation volume peaked in May 2025 with a total of $1.3M in support of a fundraising gala to support educational and workforce programs. 
<p align="center">
  <img width="75%" alt="chef gala_may investigation" src="https://github.com/user-attachments/assets/259fcbaa-16ac-4168-9c8d-060137994e70">
</p>



* In May 2025, Gala gifts totaled $261,510 (19%) of the month's donation amount. The remaining 81% of donations came from non-Gala gifts. While the Gala drove much of the donation volume at 181 gifts, the average donation amount was smaller than the non-gala gifts.
* Big campaign events encourage more participants and higher donation volumes. 


# Donor Insights

<table >
  <tr>
    <td style="vertical-align: top; width: 50%;">
     <img width="100%" alt="Dashboard 5 (3)" src="https://github.com/user-attachments/assets/5ccfc577-cf24-496c-848f-3635d2aa419f" />
    </td>
    <td style="vertical-align: top; padding-left: 20px;">
      <img width="100%" alt="proportion of donor types" src="https://github.com/user-attachments/assets/57f8eb68-4689-4784-a631-fe3bb1acba11">
    </td>
  </tr>
</table>


* 80% of donations come from foundations at an accumulated $5M worth of donations.
  
* 7.22% of donations were made by Individual donors at $500K. While individuals donors make up a smaller percentage of the total donations, they are still impactful to the organization. It shows community outreach efforts are very impactful in garnering financial support for the organization. This means that the organization should both focus on developing foundational partnerships and encourage individual donations at the same time.
  
* Recommendations: I would suggest that in order to encourage individual donations, the organization could focus campaign efforts throughout the local community both in person and online through small social media campaigns or other methods. 

* Note: Planned Giving donations are often one-time gifts made in advance following a donor plan. Since it is a one-off donation, further analysis may not yield significant results for future projections. Therefore, we will only focus on our top three constituent types: **foundation, individual, and corporate donors**. 
  
# Top Donors and Recurring Donors

Our recurring donors, defined by the donations made monthly throughout the year, were comprised of corporation, individual, and foundation donors. Most recurring monthly donations were made by Individual donor types. These donations tend to be smaller monthly amounts but over time, add up to account for a relatively strong portion of our total donations. It shows that Individual donors are still very important in our campaigning efforts as they are more likely to donate every month and continue demonstrating support month over month to the organization.

<img width="1998" height="1598" alt="Recurring Donation Distribution" src="https://github.com/user-attachments/assets/c680b730-0ea6-4786-b07a-0f73b4d3e5a4" />

* Donor 1002, a foundation donor, donated 11 times over the year accounting for $772K in total donations.
  
## Top Foundation, Individual, and Corporate Donors

<img width="2104" height="640" alt="Top Foundation Donors" src="https://github.com/user-attachments/assets/ce142188-5614-47a4-ae2a-f7b1e15f434a" />

<img width="2104" height="640" alt="Top Individual Donors" src="https://github.com/user-attachments/assets/a76c557a-d1f7-4f44-90d8-a649c20c0269" />

<img width="2104" height="640" alt="Top Corporate Donors" src="https://github.com/user-attachments/assets/53f8a95d-a39e-404c-a54d-93afac5222be" />

* Our top foundation donor donated over $2M.
* Our top individual donor donated $26K.
* The top corporate donor donated $40K.

## Overall Fund Allocation 


<table >
  <tr>
    <td style="vertical-align: top; width: 50%;">
      <img width="100%" alt="pie fund allocation (2) (1)" src="https://github.com/user-attachments/assets/98bc46a8-b20f-47b4-b938-af2731840c92">
    </td>
    <td style="vertical-align: top; padding-left: 20px;">
      <p>
        Most donations are designated towards general operations.  
        <ul>
          <li>$5M (77.3%) was reserved for general operations</li>
          <li>$784K (~11%) of donations were directed towards the SUPHS departments.</li>
          <li>$411K (~6.23%) were allocated towards the Work Development department.</li>
        </ul>
      </p>
    </td>
  </tr>
</table>

# Recommendations

### Diversify our donor base

* Foundation donors contribute 80% of total donations indicating strong relationships with Foundation partners. This could mean that we should continue to foster these relationships to continue partnerships and collaboration across the organization. However, there is a risk that if we lose a partnership with some of the foundations, we risk a large portion of future donations indicating risk for the organization. 
* Individual donors, while accounting for 7% of funds, donate most consistently month-to-month. Even though the amounts are smaller for each donation, they still add up to a significant portion of donations and are imperative in the sustainability of the organization's fundraising efforts.
* We could increase outreach through community events, social media campaigns, or peer-to-peer fundraising to reach a larger variety of donors.
* This would increase the sustainability and diversify our donor portfolio, possibly reducing reliance on foundation donors.

### Work with our Recurring Donors
* Recurring donors have already shown strong engagement with our organization.
* We could appeal to our donors through personalized thank-yous, demonstrate appreciation, and provide updates on the impact of their donation. This increases donor retention and donor involvement in our program as it allows them to see how they can help drive change and impact. 

### Campaigns and Seasonal Strategies

* Events such as the Holiday Gift Drive and Chef Gala encourage seasonal peaks in donations. Following this pattern, the organization could host similar but smaller scale events throughout the year in support of a variety of fundraising efforts.
* The marketing and fundraising teams would work to create effective campaigns in engaging more individual donors through focused social media campaigns. 
  * For example, during the slower months, we could launch smaller, seasonally focused social media campaigns to encourage further involvement with the community. For example, in February, while donations typically seem to decrease, the marketing and fundraising teams could implement mini social media "Spread the Love" campaigns to encourage donations while accounting for budget and spending. 

### Demonstrate Donation Impacts

* Donors like to see how their donation has helped the organization so I recommend creating **impact stories** of how donations were distributed to different programs to encourage community involvement. Whether it be through news articles, social media updates on new program initiatives, or media demonstrating the impact of the donations, smaller community campaigns could drive retention and involvement in our organization.

  ### Future Direction

  * Implement different campaigns throughout the next year and compare how donations changed across the year.
  * Assess the patterns in donations.
  * If implementing new campaigns, we can test how different campaigning methods work in encouraging new donors.

