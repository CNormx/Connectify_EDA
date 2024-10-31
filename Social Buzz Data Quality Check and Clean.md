# Social Buzz Data Quality Check and Clean

**Data Cleaning performed in Google Sheets:**

This dataset contains 7 tables, 3 of the tables `Content` , `Reactions`, and `Reaction Types` are relevant to helping our data analytics team provide answers to the initial inquiry of retrieving the top five post categories. We are also able to dive further into the categories by segmentation and slicing by time to deliver Social Buzz relevant insights.

After uploading the files into Google Sheets I was able to view the data and check for nulls, symbols, misspellings, capitalization. 

![Sheets Filtering.JPG](Sheets_Filtering.jpg)

- Non-critical columns were deleted: URL, User ID from the `Content` & `Reactions` tables, as they are not relevant primary or foreign keys for the metrics we need to create.
- Type, Datetime & Sentiment columns were kept for possible augmentation.
We may want to see what time of day content performs the best.
- Found and replaced all **" "** marks in the `Content` table's *Category* column.
- Null search: Found 980 Nulls in the `Reaction Type` table's 25554 records. Since the nulls only counted for **3%** of the total records/rows, I decided to delete them completely.
- 

**Formatting:** Changed the cases of 58 instances of Studying and 72 instances of Animals to lowercase using the `=ARRAYFORMULA(IF(LEN C2:C), LOWER(C2:C), ""))` function. 

![LowerCap GSheets.JPG](LowerCap_GSheets.jpg)

Changed Type column in Content to Content Type to differentiate between the Type field found in the Reactions and Reaction Types tables.