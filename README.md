\# 🎮 Gaming Performance Analytics Dashboard



An interactive Power BI dashboard for analyzing player engagement, monetization, game genre performance, device performance, and player segmentation using mobile gaming data.



\## 📊 Project Overview



This project analyzes player-level mobile gaming data to understand gameplay activity, player engagement, and monetization performance.



The dashboard was designed from a game analytics perspective to surface patterns across player segments, game genres, devices, and engagement levels — helping stakeholders answer questions like \*"which genres and devices drive the most revenue?"\* and \*"which players are most engaged, and how does that translate into spend?"\*



\## 🎯 Objectives



\- Analyze overall player activity and engagement

\- Measure revenue and Average Revenue Per User (ARPU)

\- Compare revenue across game genres

\- Analyze revenue performance across devices

\- Segment players based on session activity

\- Compare sessions and revenue across engagement segments

\- Provide an interactive dashboard for exploring player behavior



\## 🛠️ Tools \& Technologies



| Tool | Purpose |

|---|---|

| \*\*Power BI\*\* | Dashboard development and visualization |

| \*\*DAX\*\* | KPI calculations and player engagement segmentation |

| \*\*Power Query\*\* | Data cleaning and transformation |

| \*\*CSV\*\* | Source dataset |



\## 📁 Dataset



The project uses a publicly available mobile game analytics dataset containing approximately \*\*3,024 player records\*\*, including:



\- User ID

\- Age

\- Gender

\- Country

\- Device

\- Game Genre

\- Session Count

\- Average Session Length

\- Spending Segment

\- In-App Purchase Amount

\- First Purchase Days After Install

\- Payment Method

\- Age Group

\- Spender Status



\*\*Source:\*\* \[Mobile Game Analytics Dataset](https://github.com/Elifzeynepedman/mobile-game-analytics)



\---



\## 🖥️ Dashboard Preview



!\[Gaming Performance Analytics Dashboard](dashboard.png)



\## 📌 Key Performance Indicators



| KPI | Description |

|---|---|

| \*\*Total Players\*\* | Distinct number of players |

| \*\*Total Revenue\*\* | Total in-app purchase revenue |

| \*\*ARPU\*\* | Average revenue generated per player |

| \*\*Total Sessions\*\* | Total recorded gameplay sessions |

| \*\*Average Session Length\*\* | Average duration of player sessions |



\## 📊 Dashboard Analysis



\### Revenue by Game Genre

Compares total revenue generated across different game genres to identify the strongest-performing genres. In the analyzed dataset, \*\*Racing\*\* generates the highest revenue, followed by \*\*Battle Royale\*\* and \*\*Strategy\*\*.



\### Revenue by Device

Compares revenue contribution across gaming devices. \*\*Android\*\* generates more total revenue than iOS in the analyzed dataset.



\### Sessions by Engagement Segment

Players are segmented based on their session activity, and total gameplay sessions are compared across engagement groups. The \*\*Moderate Engagement\*\* segment accounts for the largest share of gameplay sessions.



\### Revenue by Engagement Segment

Compares revenue contribution across player engagement segments. The \*\*Moderate Engagement\*\* segment contributes the largest share of revenue in the analyzed dataset.



> ⚠️ These observations describe relationships within the analyzed dataset and should not be interpreted as causal relationships.



\---



\## 👥 Player Engagement Segmentation



Players are segmented based on their total session count:



| Segment | Session Count |

|---|---:|

| \*\*Low Engagement\*\* | ≤ 5 |

| \*\*Moderate Engagement\*\* | 6–15 |

| \*\*High Engagement\*\* | > 15 |



This segmentation allows gameplay activity and revenue to be compared across different levels of player engagement.



```DAX

Engagement Segment =

SWITCH(

&#x20;   TRUE(),

&#x20;   GamingData\[SessionCount] <= 5, "Low Engagement",

&#x20;   GamingData\[SessionCount] <= 15, "Moderate Engagement",

&#x20;   "High Engagement"

)

```



\## 🔢 DAX Measures



\*\*Total Players\*\*

```DAX

Total Players = DISTINCTCOUNT(GamingData\[UserID])

```



\*\*Total Revenue\*\*

```DAX

Total Revenue = SUM(GamingData\[InAppPurchaseAmount])

```



\*\*ARPU\*\*

```DAX

ARPU = DIVIDE(\[Total Revenue], \[Total Players])

```



\*\*Total Sessions\*\*

```DAX

Total Sessions = SUM(GamingData\[SessionCount])

```



\*\*Average Session Length\*\*

```DAX

Avg Session Length = AVERAGE(GamingData\[AverageSessionLength])

```



\---



\## 🧹 Data Preparation



Power Query was used to prepare the dataset for analysis. Key steps included:



1\. Importing the player-level CSV dataset

2\. Reviewing fields and data types

3\. Cleaning the `InAppPurchaseAmount` field

4\. Removing the currency symbol from purchase amounts

5\. Converting purchase amounts into numeric values

6\. Preparing the dataset for DAX calculations



\## 🎛️ Interactive Filters



The dashboard includes interactive slicers for:



\- Device

\- Game Genre

\- Country

\- Engagement Segment



These filters allow users to explore player behavior and monetization across specific segments.



\---



\## 🔍 Key Insights



\- \*\*Racing\*\* is the highest-revenue game genre in the analyzed dataset.

\- \*\*Android\*\* contributes more total revenue than iOS.

\- \*\*Moderate Engagement\*\* players account for the largest share of gameplay sessions.

\- \*\*Moderate Engagement\*\* players also contribute the largest share of revenue.

\- Combining engagement and monetization metrics provides a more useful view of player behavior than analyzing revenue alone.



\## ⚠️ Limitations



The dataset does not contain a suitable transaction date field for a reliable revenue-over-time analysis. As a result, the current dashboard focuses on:



\- Player activity

\- Sessions

\- Revenue

\- ARPU

\- Genre performance

\- Device performance

\- Engagement segmentation



Retention, cohort analysis, and time-series revenue analysis are listed below as future improvements rather than current dashboard features.



\## 🚀 Future Improvements



\- Retention analysis

\- Cohort analysis

\- First-purchase timing analysis

\- Country-level revenue analysis

\- Payment method analysis

\- Player Lifetime Value (LTV) analysis

\- Advanced player segmentation

\- More detailed monetization analysis



\---



\## 📂 Project Structure



```

gaming-performance-analytics/

│

├── README.md

├── Gaming\_Performance\_Analytics.pbix

├── dashboard.png

└── .gitignore

```



\## 👩‍💻 Author



\*\*Mansi Dhiman\*\*

B.Tech Computer Engineering, Thapar Institute of Engineering and Technology



\## 🔗 Dataset Reference



\[Mobile Game Analytics Dataset](https://github.com/Elifzeynepedman/mobile-game-analytics)

