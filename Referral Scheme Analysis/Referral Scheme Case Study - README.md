## Customer Referrals Analysis

##### Problem: 'Increase signups from the company's referral scheme'

The aim of this analysis is to understand when members usually refer other people after joining and whether referring is impacted by other factors such as the sign up channel of the referrer.

Data provided:

 * The Customer Info CSV contains information on customers and metadata for each customer. It is a representative sample of the whole customer database.

 *  The Referral Info CSV is a log of sign-ups we have received from the referral channel.

   

1. When do members refer ?

*Assumption 1: the most future sign up date reflects today's date*

![img](https://i.ibb.co/dM77bdQ/Screenshot-2020-06-12-at-18-55-08.png)

The most frequent lag (mode) is 0 month, implying that most customers refer someone less than a month after joining while the median is about 3 months.



![img](https://i.ibb.co/X22NK6s/Screenshot-2020-06-12-at-18-55-41.png) 



From the above graph we can see a decline in referrals from the most recent customers. Given the continous growth in the company's members, most customers are recent and may not have had the chance to refer someone yet. This could induce a bias as we are missing potential future referrals of recent members, impacting the distribution of the time lags between signing up and referring.

The increase in referrals is consistent with the growth in members, which has started increasing significantly since winter 2020.



![img](https://i.ibb.co/3CZBD6M/Screenshot-2020-06-12-at-18-56-34.png)



Comparing samples including recent customers and without members who have joined in the last 90 days, it seems that the shape of the distribution remains similar. The mode is still 0 month and the median changed by less than 8 days.

Interestingly, the pick in referrals observed in July-2021 had the highest proportion of late referrers (lag over 5 months) which might be the result of a marketing campaign.



![img](https://i.ibb.co/XkM6jsy/Screenshot-2020-06-12-at-18-56-51.png)



2. Does the channel members are acquired from significantly impact how they refer? Do you think we need a larger sample size to be sure?

There are three sign up channels:

* Company's Website
* Price Comparision Website 
* Referrals

Looking at the data sample, it seems that the highest proportion of referrers is found among customers who were themselves referred. We now need to test if this difference is statistically significant.



<img src="https://i.ibb.co/9cCvh4W/Screenshot-2020-06-12-at-18-57-41.png" alt="img" style="zoom:50%;" />



A chi-square test was perfomed to assess the significance of the impact the sign up channel has on how members refer.

**Hypothesis testing:**

*H0: The sign up channel has no impact*

*H1: The sign up channel impacts the referral probability*

 **Contigency table:**

<img src="https://i.ibb.co/8zyp897/Screenshot-2020-06-12-at-18-57-53.png" alt="img" style="zoom:50%;" />



0 - Never referred
1 - Referred at least once



| Returns               | Output                 |
| --------------------- | ---------------------- |
| Chi2 (test statistic) | 169.19                 |
| P-value of test       | 1.8231341708718541e-37 |
| Degree of freedom     | 2                      |

With a significance value (alpha) of 0.05, the null hypothesis is rejected. The sign up channel has some effect.

A post hoc test using Bonferroni's method confirmed significance between all channels.

While having more data is always good, the sample size was big enough for my results to be conclusive.



3. The Target

The fact that so few customers who signed up through a price comparison website refer other people can be due to a lack of awareness of the scheme. The referral scheme may not be advertised on the price comparison website. Customers who have been referred are aware that the scheme exists and have already benefitted from it.

A broad approach would be to target customers who have been with the company for over 1 month. It will act as an invitation for those who have never referred and a reminder to the others as there is no referral limit.

A more targeted approach would be to focus on the non referrer customers from the price comparison website. Once informed that the scheme exists, the number of referrer for this group is likely to increase.

An alternative approach would be to target customers who have already referred. It might be more efficient to target individuals familiar with the scheme and the process, and with a financial incentive. 



4. Experiment Design Suggestion

Additional data collection:

* Referral page hit: total number of visits on page (unique visitors).

  > Insights on the accessibility and ease of use of the scheme.

* Recipient clickthrough: number of clicks on forwarded referral link.

  > Insights on the effectiveness of the email invitations.

* Referral link share: forwarded referral link count. 

  > Insights on the profile of referrers and activity. 

* Leaving customers info: time with the company, referral channel, number of referrals etc ..

* Previous marketing campaign information. 

All the above data should be available internally and easily collected.



Summary of findings and known information: 

* Most customers referrer within a month of joining.
* The sign up channel has a significant effect on individual channel referral rate.
* There's a limited case of multiple referrals: the probability of referring more than once is 1.15 %.
* 48% of the customers have referred at least once.
* Cost of referral incentive: £100 (£50 for both the referrer and referree).



The Goal & Metric:

* Increase signups through referrals 

* The signups through referrals rate:

  > How many customers who signed up were referred ? 
  * #. sign ups through referrals  / # total signups

* The Baseline rate:

  * 481 / 1371 = 35%

* Practical significance level: 5% ( default value - to be defined taking into account the benefits vs costs of the referral programme)



![img](https://i.ibb.co/Vjk9Tvc/Screenshot-2020-06-15-at-13-45-22.png)

The experiments using different targets as defined above (section 3) can be tested once further analysis using additional data are performed, the practical significance level is properly defined and samples are available. 

