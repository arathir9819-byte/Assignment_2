# Assignment_2
Data Cleaning and Transformation    

Handling Missing Values(Power Query): Identified the missing values in the Price column and replaced them with median price using Power Query.                         
 Identified missing Category values , Created a Custom Column named Corrected Category and enter the formula     [ = if[Category]=null then if [Product Name]="Backpack" then "Accessories" else if [Product Name]="Sneakers" then "Fashion" else if [Product Name]="Coffee Maker" then "Kitchen" else if [Product Name]="Fitness Tracker" then "Electronics" else "unknown"] ,  Remove the Original Category column and Renamed Corrected Category to Category.          
Close and Load.  

Correcting Inconsistent Data :  To Correct Product Name Formatting: used the PROPER(),TRIM(),CLEAN() Functions (=PROPER(TRIM(CLEAN([@[Product Name]])))).                
To Correct Spelling mistake in Category: used Find and Replace to correct spelling mistakes (Electroni -> Electronics) and used TRIM() and CLEAN() to correct the inconsistent text formats.

Removing Duplicates : Duplicate rows were identified and removed.

Splitting and Merging Data : To split Product ID into Manufacturing Date and Country code used LEFT() and RIGHT()    (=LEFT([@[Product ID]],6) and =RIGHT([@[Product ID]],2))                                                                                                                                                                                                                                                                                                                                             To merge Brand name and Product name in Product Brand column used "&" (=[@[Brand Name]]&" "&[@[Product Name Corrected]]).

Number Formatting :  Format Price as Currency and Manufacturing Date in DD-MM-YYYY format, created a column and considered the year as 2026 (=DATE(2026,MONTH(DATEVALUE([@[Manufacturing Date]])),DAY(DATEVALUE([@[Manufacturing Date]])))).

Conditional Formatting : Highlighted the Price values by selecting Data Bars,     Highlighted Electronics in Category by New Rule, use a formula  to determine which cells to format (=$L2="Electronics").
