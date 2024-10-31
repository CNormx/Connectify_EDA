# Social Buzz Exploratory Data Analysis

**Analysis and Insights**

First, I downloaded individual CSV files from the Accenture platform to obtain the `Content`, `Reactions`, and `ReactionTypes` tables. I then created the Social Buzz dataset in BigQuery and imported these tables into it. 

```sql
CREATE TABLE IF NOT EXISTS "Accenture".content
(
    "Content ID" character varying(50),
    "Content Type" character varying(10),
    Category character varying(50)
);

CREATE TABLE IF NOT EXISTS "Accenture".reactions
(
    "Content ID" character varying(50),
    Type character varying(50),
    Datetime date
);

CREATE TABLE IF NOT EXISTS "Accenture".reactiontypes
(
    Type character varying(50),
    Score integer,
    Sentiment character varying(10)
);
```

I approached the dataset with specific questions and a clear objective. My primary goal was to identify the top five post categories based on popularity, as measured by their aggregated score. 

**Additional questions formulated in order to build out a dashboard with the data were:**

### Obtain a distinct list of all categories

```sql
SELECT co.category, sum(rt.score)as total_score
FROM `october-portfolio-project.Accenture.content` co
	JOIN `october-portfolio-project.Accenture.reactions` r
		ON co.content_id = r.content_id
	JOIN `october-portfolio-project.Accenture.reaction_types` rt
		ON r.type = rt.type
group by co.category
order by total_score DESC
LIMIT 5;
```

![Top 5 Categories.JPG](Top_5_Categories.jpg)

### How many reactions did the top category receive?

```sql
SELECT co.category, sum(rt.score)as total_score, count(r.content_id) as num_reactions
FROM `october-portfolio-project.Accenture.content` co
	JOIN `october-portfolio-project.Accenture.reactions` as r
		ON co.content_id = r.content_id
	JOIN `october-portfolio-project.Accenture.reaction_types` rt
		ON r.type = rt.type
group by co.category
order by total_score DESC
LIMIT 1;
```

![number of reactions for top cat.JPG](number_of_reactions_for_top_cat.jpg)

### Which reaction type has the highest total score for each category?

```sql
WITH type_scores as (
SELECT co.category, r.type, SUM(rt.score) as total_score,
	RANK ()OVER(PARTITION BY co.category
   ORDER BY SUM(rt.score) DESC) as rank
FROM `october-portfolio-project.Accenture.content` co
	JOIN `october-portfolio-project.Accenture.reactions` r
		ON co.content_id = r.content_id
	JOIN `october-portfolio-project.Accenture.reaction_types` rt
		ON r.type = rt.type
	GROUP BY co.category
  , r.type
)
SELECT category
, type, total_score
FROM type_scores
	WHERE RANK = 1
	ORDER BY total_score DESC;
```

![top reaction types by cat.JPG](top_reaction_types_by_cat.jpg)

### What content type is the most popular?

```sql
SELECT content_type, COUNT(*)
FROM "Accenture".content
	GROUP BY content_type
LIMIT 5;
```

![top content type.JPG](top_content_type.jpg)

### During which month were the most posts created?

```sql
SELECT FORMAT_TIMESTAMP('%B', r.Datetime) AS month,EXTRACT(YEAR FROM r.Datetime) AS year, count(distinct co.content_id) as counts 
FROM `october-portfolio-project.Accenture.content` co
	LEFT JOIN `october-portfolio-project.Accenture.reactions` as r
		ON co.content_id = r.content_id
group by month, year
ORDER BY counts desc;
```

![monthly post count.JPG](monthly_post_count.jpg)