                                                      # Computer Network Data Usage Analysis

**Tools:** PostgreSQL | Power BI  
**Project Type:** Personal Computer Network Usage Analytics  
**Focus:** Network Traffic Analysis | Process-Level Usage | Time-Based Patterns

---

                                                        ## Project Overview

My computer had been consuming a significant amount of internet data, and I wanted to understand which programs and system processes were associated with that usage, how much data was received and sent, and when network activity was recorded most frequently.

In this project, I used Windows System Resource Usage Monitor (SRUM) data, PostgreSQL, and Power BI to investigate network activity recorded on my computer between July and September 2026.

I organized the analysis around five business questions, using SQL to examine network traffic by process, data direction, time of day, and month. I then used Power BI to present the main findings in an interactive dashboard.

An important part of the analysis was identifying traffic records without a recorded executable name. These records represented a substantial share of the total network traffic and became a priority for further investigation.

---

                                                                     ## Goal

To understand the main sources and patterns of recorded network traffic on my computer, identify processes associated with higher usage, and recommend areas for further investigation to help manage data consumption.

---

                                                              ## Business Questions

The analysis focused on five questions:

1. Which programs and system processes account for the most total network traffic?
2. Which programs and system processes receive the most data?
3. Which programs and system processes send the most data?
4. When is network activity recorded most frequently, and which processes are associated with those periods?
5. Which programs show significant network activity over time?

---

                                                                          ## Key Findings

### 1. Total Recorded Network Traffic Reached 159.44 GB

The analysis recorded approximately **159.44 GB of total network traffic** during the period.

- Data received: 134.99 GB
- Data sent: 24.44 GB

The computer received substantially more data than it sent. This made incoming network traffic an important area to examine when investigating overall data consumption.

### 2. Unidentified Network Activity Accounted for 79.81 GB

Approximately **79.81 GB of network traffic had no recorded executable name** in the SRUM records.

This was the largest group of traffic in the final dashboard. However, a missing executable name does not establish that the activity was malicious or identify its source.

Further investigation is needed to determine which processes, services, or system activities may be associated with this traffic.

### 3. Unidentified Activity Had the Highest Recorded Incoming and Outgoing Traffic

Records with a blank executable name accounted for approximately:

- **67.55 GB received**
- **12.27 GB sent**

Google Chrome was another major identifiable contributor, accounting for approximately 39.23 GB received and 8.65 GB sent.

These findings helped prioritize unidentified traffic and browser-related activity for further examination.

### 4. Network Records Were Most Frequent During Early-Morning Hours

The hourly analysis showed recurring activity during the early-morning period, particularly around 1–4 AM in August and September.

In the final hourly record-count visual, 4 AM had the highest displayed count, at 1,857 records.

This identifies a period worth investigating, but it does not prove that the computer was continuously transferring data throughout that hour or establish which application caused the activity.

### 5. Unidentified Activity and Google Chrome Showed Significant Activity Over Time

The monthly analysis identified unidentified network activity and Google Chrome among the major contributors to recorded network activity.

The SQL analysis counted network records and measured their total traffic across July, August, and September 2026. This made it possible to compare recurring activity and changes across the period.

The findings highlight the importance of examining both network traffic volume and record frequency rather than relying on a single metric.

---

                                                                        ## Recommendations

Based on the analysis, I recommend:

- Investigate network records without a recorded executable name to determine whether they can be associated with specific processes or expected system activity.
- Examine activity recorded during the recurring 1–5 AM period and compare those timestamps with available application timeline and resource information.
- Review browser and VPN-related network activity to understand their contribution to overall traffic.
- Distinguish between data volume and record frequency when monitoring network usage.
- Continue monitoring network traffic over time to identify recurring patterns and changes.
- Before disabling or restricting any system process, verify its purpose and determine whether reducing its activity is appropriate.

These recommendations identify investigation priorities. The analysis does not establish that any particular process should be disabled or that all unidentified traffic can be reduced.

---

                                                                        ## Dashboard

The Power BI dashboard focuses on:

- Total network traffic, data received, and data sent
- Unidentified network activity
- Network traffic by process
- Hourly frequency of recorded network activity
- Network traffic trends over time

The dashboard is designed to answer one main question:

**Where is my computer's network data going, and when is network activity recorded most frequently?**

---

                                                                               ## Process

- I extracted Windows SRUM data using SrumECmd.
- I prepared the extracted data for analysis.
- I loaded the network usage data into PostgreSQL.
- I used SQL queries to investigate total traffic, received data, sent data, hourly patterns, and monthly activity.
- I used a process-mapping table to make executable paths easier to interpret.
- I investigated records with missing executable names separately from records that did not match a process-mapping pattern.
- I translated the findings into recommendations for further investigation.
- I used Power BI to build a dashboard communicating the main patterns and investigation priorities.

---

                                                                              ## Technical Approach

                                                                                ### PostgreSQL

The SQL analysis used:

- Aggregate functions, including `SUM()` and `COUNT()`
- `GROUP BY` and `ORDER BY`
- `LEFT JOIN`
- Regular-expression matching for process mapping
- Date and time extraction using `EXTRACT()`
- Date formatting using `TO_CHAR()`
- Monthly and hourly grouping
- Separate calculations for data received and sent

The SQL analysis helped move from overall traffic totals to more specific questions about the processes, time periods, and recurring patterns associated with network activity.

                                                                               ### Power BI

The dashboard uses:

- KPI cards
- Stacked horizontal bar charts
- Hourly column charts
- Monthly line charts
- Data modelling and DAX measures
- Presentation-friendly process names
- Visual emphasis to highlight important findings

The dashboard separates the volume of network traffic from the frequency of recorded activity so that each visual answers a clear analytical question.

---

                                                                   ## Data and Limitations

The project uses Windows SRUM network usage records extracted from my computer for July–September 2026.

The analysis focuses on recorded network traffic associated with executable information, timestamps, and byte counts.

A few limitations are important:

- SRUM executable information identifies recorded processes, not the specific websites or online services visited within a browser.
- A blank executable name does not reveal the underlying cause of the traffic.
- SRUM timestamps represent recorded usage information and should not automatically be interpreted as exact user-action times.
- The analysis identifies patterns and investigation priorities; it does not establish that a process caused excessive consumption or that a specific action will reduce future usage.

---

                                                                          ## Conclusion

This project helped me examine a practical data consumption problem using SQL and Power BI.

The main findings were that the computer recorded 159.44 GB of network traffic, a substantial amount had no recorded executable name, and network activity appeared to be used during a  certain early morning hours.

Rather than assuming the cause, I used the findings to identify where further investigation would be most useful.

The project demonstrates how I use SQL to investigate a real-world question, distinguish between different measures of activity, and communicate findings through a business-focused dashboard.

---

## Connect With Me

**Winner Donald**

- GitHub: https://github.com/winnerdonald158
- LinkedIn: https://www.linkedin.com/in/winner-donald
- Email: winnerdonald158@gmail.com
- Location: Abuja, Nigeria
