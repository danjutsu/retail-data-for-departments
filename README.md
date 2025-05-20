# retail-data-for-departments
manipulating retail data for different departments live environment

first request
From: Sarah Johnson, Retail Operations Manager
To: Data Analytics Team
Subject: Q2 Sales Analysis Project
Date: May 2, 2025 | 9:14 AM

I've attached the raw data extract from our POS system. You'll need to clean it up before analysis - there are several data quality issues typical of our retail environment that need addressing:
*Missing values in some fields
*Inconsistent formatting (especially dates and categories)
*Duplicate transactions (some legitimate, some errors)
*Pricing anomalies that need to be identified
Once you've analyzed the data, please prepare a summary of key findings with appropriate visualizations. This will be presented to our regional managers next week.
The deadline for this analysis is May 9th, so we have time to review before the presentation.

first I'll examine the data in sheets then clean the necessary data.
I immediately saw Weather_Impact had NULLs.
so I started with a JOIN. weather_impact with Date and Region.

there were still nulls because some regions were null too. I found a pattern. Region and Store_Id correspond so I filled those missing values quickly then re-ran the JOIN.
///JOIN (
///    SELECT DISTINCT Store_ID, Region
///    FROM retail_data
    WHERE Region IS NOT NULL AND Region != ''
///)
