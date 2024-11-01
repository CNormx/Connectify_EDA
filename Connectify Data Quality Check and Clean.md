# Connectify Data Quality Check and Clean

**Data Cleaning performed in Google Sheets:**

This dataset contains seven tables, of which three—`Content`, `Reactions`, and `Reaction Types`—are relevant to helping our data analytics team answer the initial inquiry about retrieving the top five post categories. We can also dive deeper into the categories by segmenting and slicing the data by time to deliver relevant insights to Social Buzz. 

After uploading the files into Google Sheets, I viewed the data and checked for nulls, symbols, misspellings, and inconsistent capitalization.

![Sheets Filtering.JPG](https://github.com/CNormx/Accenture_analysis/blob/main/Google%20Sheets%20imgs/Sheets%20Filtering.JPG)

- Non-critical columns were deleted: URL and User ID from the `Content` and `Reactions` tables, as they are not relevant primary or foreign keys for the metrics we need to create.
- Type, Datetime, and Sentiment columns were kept for possible augmentation. We may want to analyze what time of day content performs best.
- Found and replaced all quotation marks in the `Content` table's *Category* column.
- Null search: Found 980 nulls in the `Reaction Type` table's 25,554 records. Since the nulls only accounted for **3%** of the total records, I decided to delete them entirely.

**Formatting:** Changed 58 instances of "Studying" and 72 instances of "Animals" to lowercase using the `=ARRAYFORMULA(IF(LEN C2:C), LOWER(C2:C), ""))` function.  

![LowerCap GSheets.JPG](https://github.com/CNormx/Accenture_analysis/blob/main/Google%20Sheets%20imgs/LowerCap%20GSheets.JPG)

Renamed the `Type` column in the `Content` table to `Content Type` to distinguish it from the `Type` fields in the `Reactions` and `Reaction Types` tables.
