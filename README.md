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

The functions and actions performed in Google Sheets to inspect and clean the data for this analysis can be found [here](https://github.com/CNormx/Connectify_EDA/blob/main/Connectify%20Data%20Quality%20Check%20and%20Clean.md).

Targeted SQL queries addressing various business questions are available [here](https://github.com/CNormx/Connectify_EDA/blob/main/Connectify%20Exploratory%20Data%20Analysis.md).

An interactive Looker Studio dashboard for reporting and exploring categorical trends can be accessed [here](https://lookerstudio.google.com/reporting/53d58549-3809-4069-adff-772184dec9ac).



# Data Structure & Initial Checks

Connectify's main database structure consists of 7 tables: User, Profile, Location, Session, Content, Reaction, Reaction types.</br>
Our relevant datasets are Reaction, Content, and Reaction Types.
To address the client's request for an analysis of their content categories—showing the top 5 categories with the largest popularity as measured by their score—we only need data that includes the `content ID`, `category`, `content type`, `reaction type`, and `reaction score` fields.
As explained in the data model [file](https://github.com/CNormx/Connectify_EDA/tree/main/Connectify%20Briefs%20and%20Data%20Model), popularity is quantified by the score assigned to each `reaction type` which connects to the `reactions` table via the `type` field.

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

The top 5 user post categories were clearly defined and displayed Animals in the top spot with 1,897 posts. This accounted for 21.4% of the top 5 category popularity. Analysis of the reaction patterns across categories revealed distinct preferences which indicated the highest level of user engagement and emotional response. The following sections will explore additional views into the post categories showcasing features that resonate most strongly with our user base, while simultaneously highlighting areas primed for optimization to drive increased engagement and user satisfaction.</br>
[link to Dashboard](https://lookerstudio.google.com/s/gA_Uv2xolHs)

![image](https://github.com/CNormx/Connectify_EDA/blob/main/Looker%20Studio%20Dashboard/Connectify%20Dashboard%202.jpg)  

# Insights Deep Dive

### Top reaction types for each individual category:

* Analysis of the reaction patterns across categories revealed distinct preferences: the Technology category predominantly drew 'Adore' reactions, while 'Want' emerged as the primary response for Science-related content. Notably, the top-performing category Animals, consistently garnered 'Super Love' reactions, indicating each of the categories highest level of user engagement and emotional response.

![image](https://github.com/CNormx/Connectify_EDA/blob/main/Looker%20Studio%20Dashboard/chart%20cattypes.JPG)

### Months with the highest number of posts and their respective counts:

* The dataset started in the month of May in 2020 and ended in June 2021. The resulting graph showed very little variation in the amount of user post throughout the year, with a high of 781 posts in 2021 occurring in the month of January. Correlating the amount of posts to traditional holiday seasonality patterns is difficult, as the second highest month of posts occurs in July 2020, with just 778 posts. 
  
![image](https://github.com/CNormx/Connectify_EDA/blob/main/Looker%20Studio%20Dashboard/chart%20months.JPG)

### Most popular content types among users (e.g., photos, videos):

* The results for the most popular content types resulted in a near tie, with Photo and Video coming out on top. 
![image](https://github.com/CNormx/Connectify_EDA/blob/main/Looker%20Studio%20Dashboard/chart%20contenttype.JPG)


# Recommendations:

Based on the insights and findings above, we would recommend the Connectify team to consider the following: 

* **User Sentiment and Content Strategy:** The amount of 'Super Love' reactions in the Animal category indicates strong positive user sentiment. This data suggests potential for increased engagement through strategic partnerships with animal shelters, zoos, and conservations. Implementing an animal-centric campaign could leverage this affinity to drive platform growth and user interaction.
  
* **Trends over time and Campaign Planning:** Examination of monthly post volume over a one-year period shows minimal fluctuation. It is recommended to continue monitoring these trends on monthly and quarterly bases to establish long-term patterns. The current data does not support seasonally targeted campaigns due to the lack of significant variation. Further marketing analysis is advised to inform future strategies.
  
* **Content Type Optimization:** With photo and video content emerging as the dominant media types, prioritizing the enhancement of these formats is crucial. Focusing on improving the quality and delivery efficiency of photo and video content could significantly impact user retention and acquisition
  
* **Reaction Nulls:** A 3% null reaction rate was observed, indicating a small subset of users who do not engage with certain posts. While this finding was not central to the current analysis, it presents an opportunity for future investigation. Tracking this metric over time could provide valuable insights into user engagement patterns and content relevance.

# Caveats:

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

* Since this sample dataset only covers a year, predictive charts could be made in order to see a better example of user trends and what to expect for the future
 
* 3% of reaction post had null reactions which were excluded from the analysis
