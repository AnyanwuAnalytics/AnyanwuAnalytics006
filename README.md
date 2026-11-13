<img width="629" height="311" alt="Screenshot 2026-11-13 232438" src="https://github.com/user-attachments/assets/1ceb948d-a51c-4844-b299-dc610efd99f7" />


Introduction

This project is an Excel dashboard built on a global conflict and terrorism incident dataset. Here is what is in it:

29,180 incidents after cleaning, and each row is one incident
98 countries and 6,499 cities
Incidents from 1 January 2002 to 18 July 2016
7 columns in the raw file, which became 10 after cleaning
195,319 people killed and 275,889 injured, a total of 471,208 casualties
An average of 6.69 people killed and 16.15 casualties per incident
Iraq alone accounts for 43% of all casualties

Data Story

This dataset tells the story of how terrorism and armed conflict ripple across nations. Each row records one incident: when it happened, in which country and city, and how many people were killed and injured. It does not say who carried out an attack or what kind of attack it was, so the numbers can only tell us how much, where and when, not why.

What the numbers do show is that the harm is very uneven. A handful of countries carry most of the toll. A small share of attacks causes a huge share of the casualties. And one year, 2014, stands out from all the rest.

Data Tool and Source

Tool: Microsoft Excel.

Source: https://www.kaggle.com/datasets/argolof/predicting-terrorism


Cleaning Process

Kept the raw data safe. I left the original in the Before sheet.
Removed columns I did not need. The raw file had an unnamed index column and a long Description column. I dropped both.
Removed repeated rows. 184 rows repeated the same date, country, city, killed and injured counts as another row, so I removed them. That took the data from 29,364 rows to 29,180.
Added five columns to make the analysis possible:
Total Casualties per Incident (Killed + Injured)
Attack Severity Index (2 × Killed + Injured, so a death counts double)
Fatality Ratio (Killed ÷ Total Casualties, which is 0 where nobody was harmed)
Year and Month, taken from the date
Checked the basics. No blank cells, and the calculated columns match their formulas on every row.

Columns Within the Data

Date: the day of the incident
Country: where it happened
City: the city or town
Killed: number of people killed
Injured: number of people injured
Total Casualties per Incident (added): Killed + Injured
Attack Severity Index (added): 2 × Killed + Injured
Fatality Ratio (added): the share of casualties who were killed, from 0 to 1
Year (added): the year of the incident
Month (added): the month of the incident

Pre Analysis Board

Data Splitting

Independent variables (what I group by): Date, Country and City.

Dependent variables (what I measure): Killed, Injured, Total Casualties per Incident, Attack Severity Index and Fatality Ratio.

Industry Type

This dataset falls under the Security & Defense / Counter-Terrorism Analytics industry. It captures incidents of violence, terrorism and armed conflict. Data like this is used in risk intelligence, national security, humanitarian response and policy analysis, and it sits where data journalism, law enforcement intelligence and conflict studies meet.

Stakeholders

Government & Security Agencies (ministries of defence, police, intelligence services) use the data to find hotspots, assign resources and prevent future attacks.
International Organizations (the UN, NGOs, humanitarian groups) track civilian harm and aid needs.
Researchers & Analysts study the patterns, causes and effects of terrorism.
Media & Public Policy Makers (journalists and think tanks) use the data to inform the public and shape policy debates.
Local Communities are the people directly affected, and they want transparency, accountability and safety.
What Success Means

For governments, success means fewer incidents, fewer casualties and a better ability to predict and prevent attacks. For international organizations, it means accurate reporting of civilian harm, a better humanitarian response and evidence for peace-building. For researchers, it means clean, well-structured data that reveals trends. For communities, it means fewer attacks, safer places to live, and trust that authorities are acting on the data.


Potential Questions
I wrote 20 planning questions. These are the ones the dashboard answers:

Which country had the highest total casualties?
Which country had the most incidents?
Which city had the most incidents?
How many people were killed, and how many were injured?
How many people are killed per incident on average?
Which month had the most incidents?
Does the fatality ratio change from month to month?
Which years were the deadliest?
Which cities saw the most severe attacks?
Which single incident caused the most casualties?
How many incidents had no casualties at all?


In Analysis

Here is what I found after building each chart:

The Key Numbers

Observation: 29,180 incidents caused 471,208 casualties, with 195,319 people killed and 275,889 injured. The Average Fatalities card shows 6.69, which means that on average 6.69 people are killed per incident, and 16.15 people are harmed.

Insight: the average hides a big gap. The typical incident has only 5 casualties, and 52% of incidents have between 1 and 5. But 676 incidents (2.3%) caused 100 or more casualties each, and together they account for 30% of all casualties. Only 14 incidents had no casualties at all.

1. Top 5 Countries by Total Casualties
<img width="750" height="450" alt="image" src="https://github.com/user-attachments/assets/c1b5e3b1-f0ff-4169-8834-6f474ca89ec5" />

Observation: Iraq leads with 203,430 casualties, followed by Pakistan (49,196), Nigeria (36,289), Afghanistan (35,107) and Syria (26,711).

Insight: these five countries carry 74% of all casualties. Iraq alone carries 43%, more than four times Pakistan’s total. Iraq also has 30% of all incidents, so it is both the most attacked and the most affected. Nigeria and Syria are different. They have far fewer incidents (1,313 and 898), but each incident is much deadlier, at about 28 and 30 casualties per attack, against about 11 for Pakistan and Afghanistan.

2. Monthly Trend of Incident Activity
<img width="751" height="566" alt="image" src="https://github.com/user-attachments/assets/b8d1b898-4f4c-4230-9e9a-bf5d1b1f787b" />


Observation: incidents peak in July (2,785) and are lowest in December (2,192). June (2,729) and August (2,556) are also high.

Insight: there is a summer surge. One thing to keep in mind is that the data ends in July 2016, so January to July have 15 years of data while August to December have 14. Adjusting for that, July still leads at about 186 incidents a year, against about 143 in February, the quietest month. That makes July about 30% busier than February.

3. Global Fatality vs. Injury
<img width="750" height="450" alt="image" src="https://github.com/user-attachments/assets/3c99a15b-95e4-474e-b96b-9200e667a070" />

Observation: the donut shows 195,319 people killed (41.5%) and 275,889 injured (58.5%).

Insight: for every person killed, about 1.4 were injured. Most victims survived, and many of them will need long-term medical care and rehabilitation. Looking at deaths alone would miss more than half of the human impact.

4. Monthly Fatality Ratio
<img width="752" height="452" alt="image" src="https://github.com/user-attachments/assets/ff07ea18-51ac-40d0-9f6a-23a731f8855d" />


Observation: the average fatality ratio is 0.645. It ranges only from 0.630 in April to 0.661 in August, a spread of 3 points.

Insight: how deadly an attack is does not change with the season. The number of attacks goes up in summer, but the share of casualties who die stays almost the same. You may wonder why 0.645 is higher than the 41.5% killed share. The ratio is an average of every incident counted equally, and 45% of incidents had only deaths and no injuries. The very large attacks, which injure many people, are much rarer, so they pull the overall killed share down.

5. Top 10 Cities by Average Attack Severity
<img width="752" height="452" alt="image" src="https://github.com/user-attachments/assets/3577e676-3e46-46e1-8cf6-dd757c35a56c" />


Observation: the highest average severity (2 × Killed + Injured) is in Dogo Nahauwa (1,656), followed by Camp Speicher (1,222), Madrid (1,128), Baghaliyeh (1,000), Taza (937), Beslan (667), Baga (661), Jableh (660), Urumqi (615) and Tuz Khurmatu (567).

Insight: this chart shows one-off mass-casualty attacks, not the most dangerous cities overall. Six of the ten cities appear only once or twice in the data, and Baga is the only one with more than three incidents (7). The city with the heaviest overall toll is Baghdad, with 2,412 incidents and 77,516 casualties, which is 16.5% of all casualties. Its attacks average about 32 casualties each.

6. Top 10 Deadliest Years
<img width="752" height="452" alt="image" src="https://github.com/user-attachments/assets/9d8968ae-3605-4e3e-bb6c-b58a79e08d30" />


Observation: 2014 was the deadliest year with 32,852 people killed, followed by 2015 (27,570), 2007 (20,441), 2013 (16,764) and 2006 (15,209).

Insight: 2014 and 2015 together account for 31% of everyone killed in the whole dataset. 2014 also had the most incidents of any year (3,003), so there were more attacks and each was deadlier. In 2014, an average of 10.9 people were killed per incident, against about 4.6 in 2009 to 2012. 2016 only runs to mid-July and it is already the sixth deadliest year.


Post Analysis

After completing the dashboard creation, Here are the few observations and insights that I put together:

Observations

The harm is concentrated. Five countries carry 74% of casualties, and Iraq alone carries 43%. Within the data, 2.3% of incidents cause 30% of casualties.
Frequency and deadliness are different things. Thailand has 2,355 incidents (8% of the total) but only 1.8% of casualties. Nigeria and Syria have fewer incidents, but much deadlier ones.
The summer surge is real. Incidents peak in July, and it holds up after adjusting for the data ending in July 2016.
Deadliness stays steady through the year. The fatality ratio moves only 3 points between the best and worst month.
2014 was a turning point. The number of people killed per incident more than doubled compared with 2009 to 2012.
Injuries outnumber deaths by about 1.4 to 1.


Insights

The risk is steady through the seasons, but not through the years. The monthly pattern is stable, while 2014 and 2015 show how quickly the picture can change.
Counting attacks alone can mislead. A country with many small attacks and a country with a few very large ones need different responses.
The cities in the severity chart tell us about single extreme events, so a security plan cannot be based on them alone.
A word of caution about the data. It has no attack type, no group responsible, and it ends in July 2016. Descriptions read like news summaries, so I cannot tell how complete the reporting is in each country. I can show where and when the harm happened, but not why.


Overall Recommendations

Plan for total casualties, not only deaths. Injuries are 41% higher than deaths, so emergency medical capacity, blood supply and rehabilitation support should be a priority in high-risk areas.
Prepare for the summer. Scale up readiness from June to August, when incidents are about 30% higher than in the quietest months.
Build deep-dive dashboards for the top countries. Iraq and Pakistan carry the largest totals. Nigeria and Syria should be added because their attacks are the deadliest per incident.
Set a baseline for each country. The global fatality ratio is 0.645, but countries differ a lot (Thailand averages 0.78 and Iraq 0.57). An alert should compare a country with its own normal, not with the global average.
Track mass-casualty events separately. The 676 incidents with 100 or more casualties cause 30% of the harm, so they need their own review and response plan.
Study 2014 as a case study. Find out what changed that year, because it shows how conflict can move from manageable to critical.



Conclusion

I started this project asking where attacks happen most. I ended it asking why a few of them do so much damage. The data showed me that harm is not spread evenly. Five countries carry 74% of the casualties, 2.3% of the attacks cause 30% of them, and 2014 alone changed the whole picture. For every person killed, 1.4 were injured, so the toll goes far beyond the deaths.





