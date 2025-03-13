# Maven Marketing Campaign Analysis (WORKING)
This project uses a marketing campaign data of 2,240 customers of Maven Marketing, including customer profiles, product preferences, campaign successes/failures, and channel performance. Our objective is to conduct an analysis for the following: 
- Are there any null values or outliers? How will you handle them?
- What factors are significantly related to the number of web purchases?
- Which marketing campaign was the most successful?
- What does the average customer look like?
- Which products are performing best?
- Which channels are underperforming?

## Excell Skill and Concepts Applied
- Data Cleaing
- Excel Formulas (`Date`, `INDEX`, `MATCH`, `MAX`, etc.)
- Cell Referencing
- Pivot Tables/Charts
- Slicers
- Data visualization
- Dashboard

## Data Cleaning
We imported the dataset through Microsoft Excel. The original dataset contains 2,240 rows and 28 columns. The data was cleaned by:
- Removing duplicates
- Formatting the data of each column appropriately (ie income column was formatted to have currency shown)
- A new columns was created to show the year of birth for each customer using the below formula
 ` =Date (Year, month, day) / =DATE(B2,1,1)`
The formula converts the year in cell B2 to a `Date` format by assuming the month and day as January 1st. The format was changed to ‘yyyy’ through custom format to have only the year part displayed. The rest of the rows were auto-filled by Excel accordingly.

## Analysis

### What factors are significantly related to the number of web purchases?
The first areas of interest that related to the number of web purhases are age and education. I created a new column for age using the formula below 
`= (2014 - B2)`
The formula subtracts the year in the cell B@ from 2014. The rest of the rows were auto filled by excel accordingly. Then I formatted the Age column with the `Number` format. Next, a new column was created for Age Group using the formula below: 
`=IFS(D2<=30,"Adolescent",D2<=40,"Adult",D2<=55,"Middle-Age",D2>55,"Senior")`
The formula groups customers based on their ages in Column D: 30years & below – Adolescents, 40years & below – Adult, 55years & below – Middle-Age, and those above 55years as “Seniors”. The rest of the rows were auto-filled by Excel accordingly. A pivot table and pivot chart was created to check for web purchases by age group and education on creating the column for Age and Age groups. WE discover that the highest number of web purchases come from middle-aged groups with a graduation level of education. We can assumed that this group is also married, but we want to go deeper and look at the data for this. A Pivot table and Chart was also created to check for that, and we find that the married category has the highest web purchases.
It is also important to look at geographical location when considered factors that influence web purchases. A pivot table was created to get the data summary for each country. However, Microsoft Excel is unable to create certain visuals, such as a filled map visual, with data inside a Pivot Table. Hence, to use the appropriate visual, the data was copied outside the Pivot Table. This was done by sorting the data alphabetically, then in a new cell, replicating the country and web purchase columns with the formula as shown below:
`=A50
&
 =VLOOKUP(D50,$A$50:$B$57,2)`
The resulting Pivot and visual shows that Spain had the highest number of web purchases, while Mexico had the least record of web purchases.
### Which marketing campaign was the most successful?
We have now seen the web purchases variation across various categories, but how did the marketing campaigns fare at each stage – was there a high acceptance at the first campaign? or after subsequent campaigns? A Pivot table and Chart was created to evaluate this
From the Pivot Table and Chart/Visual, we see that Campaign 4 was the most successful marketing campaign.
### What does the average customer look like?
From our resulting Pivot, we see that the Average Maven Customer is a Married, Middle-Aged individual with over $50,000 as Income and has at least 1 teenage child.
### Which products are performing best?
A pivot table was created to get the data summary for the product category. However, MS Excel is unable to create certain visuals, such as a Treemap visual, with data inside a Pivot Table. Hence, to use the appropriate visual, the data was copied outside the Pivot Table using cell referencing [shown below] in a new cell and filling down the columns accordingly
`=A91
&
 =B91`
The resulting Pivot and visual, as shown below, shows that the best-performing product is Wines, with over $600,000 spent on them in the last two years, followed by Meat Products, while the least amount was spent on Fruits.
### Which channels are underperforming?
I found that the Catalog sales channel is the least-performing channel, accounting for only 21% of the total purchases. This channel requires attention to enhance Improvement.
## Data Visualization
The interactive dashboard contains a Microsoft Excel worksheet overview of the analysis. It was created to provide insights and dynamic answers to business questions posed during the analysis.
## Key Insights
- Customers at the Graduation education level accounted for the highest number of web purchases across all age groups.
- Customers in Spain and the married group made the highest web purchases.
- Campaign 2 had the least acceptance rate, indicative of low Customer engagement & response.
- The rise and fall pattern in the campaign performance is indicative of reduced effort after a seemingly successful one.
- The Average Maven Customer is a Married, Middle-Aged individual earning over $50,000 as Income and has at least 1 teenage child.
- Wines & Meat products are the best-selling products from the campaign.
- Based on the number of purchases across the channels, the Catalog sales channel is underperforming and requires attention.
- The high rate of Store purchases indicates that Maven has more walk-in Customers than others.
