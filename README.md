# Project Background
Social Buzz established in 2010 is a social media and content creation platform where content is at the forefront of user feeds. Currently the platform has 500 million active users monthly creating over 100,000 pieces of content daily. The client stated that scale is becoming a big problem of theirs and they are struggling to manage with the resources that they currently have. They are looking for help with the management of their data and journey at a larger size.

Accenture was tasked with fufilling three requirements for this project:
- **Audit of big data practice**
- **Recommendations for IPO**
- **An analysis of their content categories that highlights the top 5 categories with the largest aggregate popularity**

The Data teams task is to analyze a data set with visualizations to understand the popularity of different content categories. A further understanding of their growing user base and the populartiy of features on the platform will shape the companies future, provide critical insights, and measure their successes in a clear tangible way.


Insights and recommendations are provided on the following key areas:

- **Category trend analysis -evaluation of the top categories:** 
- **Category 2:** 
- **Category 3:** 
- **Category 4:** 

The SQL queries used to inspect and clean the data for this analysis can be found here [link].

Targed SQL queries regarding various business questions can be found here [link].

An interactive Tableau dashboard used to report and explore sales trends can be found here [link].



# Data Structure & Initial Checks

The Social Buzz's main database structure consists of 7 tables: User, Profile, Location, Session, Content, Reaction, Reaction types.</br>
Reaction, Content, and Reaction Types are our relevant data sets.
We only need data that shows the content ID, category, content type, reaction type, and reaction score in order to answer the clients request for an analysis of their content categories showing the top 5 categories with the largest popularity.
As explained in the data model [file], popularity is quantified by the Score given to each reaction type.

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
Score: This is a number calculated by Social Buzz that quantifies how “popular” each reaction is. A reaction type with a higher score
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
