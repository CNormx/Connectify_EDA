# Project Background
Connectify, established in 2010, is a social media and content creation platform where content takes center stage in user feeds. Currently, the platform boasts 500 million monthly active users, generating over 100,000 pieces of content daily. The client has expressed that the scale and rate at which their data is growing has become unmanageable for their internal staff. They are seeking assistance in maintaining best data practices as the company expands.

Accenture was tasked with fufilling three requirements for this project:
- **Audit of big data practice**
- **Recommendations for IPO**
- **Analysis of content categories, highlighting the top 5 with the largest aggregate popularity**

The Data Analytics team was specifically tasked with analyzing a sample data set and creating visualizations to understand the popularity of different content categories. A deeper understanding of their growing user base and the popularity of platform features will shape the company's future, provide critical insights, and measure their success in a clear, tangible way.

Insights and recommendations are provided on the following key areas:
- **Category trend analysis: Evaluation of the top categories**
- **Top reaction types for each individual category**
- **Months with the highest number of posts and their respective counts**
- **Most popular content types among users (e.g., photos, videos)**

The functions and actions performed in Google Sheets to inspect and clean the data for this analysis can be found [here](https://github.com/CNormx/Accenture_analysis/blob/main/Social%20Buzz%20Data%20Quality%20Check%20and%20Clean.md).

Targeted SQL queries addressing various business questions are available [here](https://github.com/CNormx/Accenture_analysis/blob/main/Social%20Buzz%20Exploratory%20Data%20Analysis.md).

An interactive Looker Studio dashboard for reporting and exploring categorical trends can be accessed [here](https://lookerstudio.google.com/reporting/53d58549-3809-4069-adff-772184dec9ac).



# Data Structure & Initial Checks

Connectify's main database structure consists of 7 tables: User, Profile, Location, Session, Content, Reaction, Reaction types.</br>
Our relevant datasets are Reaction, Content, and Reaction Types.
To address the client's request for an analysis of their content categories—showing the top 5 categories with the largest popularity as measured by their score—we only need data that includes the `content ID`, `category`, `content type`, `reaction type`, and `reaction score` fields.
As explained in the data model [file](https://github.com/CNormx/Accenture_analysis/tree/main/Social%20Buzz%20Briefs%20and%20Data%20Model), popularity is quantified by the score assigned to each `reaction type` which connects to the `reactions` table via the `type` field.

A description of each table is as follows:
- **Content:** Content
ID: Unique ID of the content that was uploaded (automatically generated)</br>
Type: A string detailing the type of content that was uploaded</br>
Category: A string detailing the category that this content is relevant to

- **Reactions:**
Content ID: Unique ID of a piece of content that was uploaded</br>
Type: A string detailing the type of reaction this user gave</br>
Datetime: The date and time of this reaction

- **ReactionTypes:**
Type: A string detailing the type of reaction this user gave</br>
Sentiment: A string detailing whether this type of reaction is considered as positive, negative or neutral</br>
Score: This is a number calculated by Connectify that quantifies how “popular” each reaction is. A reaction type with a higher score
should be considered as a more popular reaction.

![image](https://github.com/CNormx/Accenture_analysis/blob/main/Accenture%20erd.JPG)

# Executive Summary

### Overview of Findings

Explain the overarching findings, trends, and themes in 2-3 sentences here. This section should address the question: "If a stakeholder were to take away 3 main insights from your project, what are the most important things they should know?" You can put yourself in the shoes of a specific stakeholder - for example, a marketing manager or finance director - to think creatively about this section.

[Visualization, including a graph of overall trends or snapshot of a dashboard]



# Insights Deep Dive
### Category 1:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 1]


### Category 2:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 2]


### Category 3:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 3]


### Category 4:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 4]



# Recommendations:

Based on the insights and findings above, we would recommend the [stakeholder team] to consider the following: 

* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  


# Assumptions and Caveats:

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

* Assumption 1 (ex: missing country records were for customers based in the US, and were re-coded to be US citizens)
  
* Assumption 1 (ex: data for December 2021 was missing - this was imputed using a combination of historical trends and December 2020 data)
  
* Assumption 1 (ex: because 3% of the refund date column contained non-sensical dates, these were excluded from the analysis)# Accenture_analysis
