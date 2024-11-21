# MIST4610-Project2


## Team Name
4610Fa24Group9


## Team Members:
1. Dylan Van Saun [@dylanvansaun](https://github.com/dylanvansaun)
2. Zoey Cao [@zoeync](https://github.com/zoeync)
3. Jennifer Tran [@j-tran1](https://github.com/j-tran1)
4. Margaret Cox [@mac14681](https://github.com/mac14681)
5. Jayden Smith [@jaydenSmith4321](https://github.com/jaydenSmith4321)


## Dataset Description and Features:
The dataset, created by the Town of Cary's Geographic Information Systems (GIS) Group, compiles real estate data from the western portion of Wake County, the eastern portion of Chatham County, and the southern portion of Durham County. The original data from these counties have been modified to function as one layer and for this analysis, only the data pertaining to Wake County was used. While the dataset includes many (50+) columns, this analysis focuses on seven columns that were identified as the most relevant and useful for understanding property characteristics and market trends. It is available at https://catalog.data.gov/dataset/real-estate-data.

The county column is a string that shows which county the data is from. It’s used to categorize the data by location, and since the analysis focuses on Wake County, there was no need to filter the data as the columns we used for analysis had null values for Chatham and Durham.

The total building square footage column is a continuous measure stored as a decimal number. It represents the size of the building on the property and is compared to the total sale value to analyze the relationship between property size and price. The total sale value column, a whole number, captures the total sale price of the property, including both land and fixed assets (buildings). This value is used with square footage and acreage to calculate key metrics, such as sale price per acre.

The total sale date column, a discrete dimension recorded as a date, specifies when each property (land and fixed assets) was sold. This data is analyzed by month to identify historical trends in sale prices over time. The typedecode column is a string that categorizes the type of property such as a church, fast food restaurant, single-family, and more. This column is useful for filtering data to focus on specific property types.

The APA ownership description column describes the ownership classification of the property, such as individual or corporate ownership. This column is useful for filtering data to see individually owned properties and forecast future sale price trends for them. Lastly, the total calculation acreage column, a continuous measure stored as a decimal number, indicates the total acreage of the property. This column is important for calculating metrics like sale price per acre.

Certain columns were excluded from the analysis because that data was not as relevant compared to the more informative columns mentioned previously. Specifically, the indicator columns that duplicated information in corresponding description columns were removed to eliminate redundancy. For example, the APA ownership column, which contained numerical identifiers, was excluded because the APA ownership description column provided descriptive text of the same information.

## Questions and Their Importance:


#### Question 1: How much of the variation in sale value is based off the square footage for different types of real estate?

##### Question 1 Importance:
The first analysis question focuses on how much of the variation in sales value is based on square footage for different types of real estate. To address this, several property types were analyzed, such as Church, Fast Food, Multi-Tenant, and Single-Family. These categories were chosen because their sales value may be impacted by square footage and they exhibited the most normal data points. This question is important as it helps in understanding how much of the total sales value can be explained by square footage, using scatterplot and regression analysis. For instance, in the case of Single-Family homes, does a larger house and land area consistently lead to higher sales values? Similarly, for companies, is the size of the property a major factor in determining pricing, or do other factors, such as location, play a larger role? Answering these questions has significant economic and practical implications, offering insights into property valuation dynamics across different cases. This analysis is particularly useful for property sellers, corporations or organizations looking to purchase property, and aspiring homeowners. By understanding the relationship between property size and value, these stakeholders can make more informed decisions about pricing, investments, and purchases. The data is sourced from a non-federal North Carolina real estate database from Wake County, North Carolina. It includes variables such as Totalbldgsqft, which represents the building square footage, and Total Sale Value. These dimensions are directly tied to the analysis and were used to create a scatterplot with Totalbldgsqft on the x-axis and Total Sale Value on the y-axis, to help visualize the relationship between size and sale value.

##### Question 1 Manipulations:
To ensure the analysis reflects current market conditions, data from January 2018 to the present was used. Additionally, to enhance relevance, the data was filtered using the Typedecode field to focus on specific property types where square footage is likely to have a significant impact on value. This filtering step allowed for honing in on relevant real estate categories. The approach, combining scatterplots and regression analysis, provides a well-rounded foundation for identifying trends and patterns in property valuation, offering relevant insights for stakeholders in the real estate market.

![image](https://github.com/user-attachments/assets/502c9b52-a7b5-4245-b2f4-c1489ce38d8d)

#### Question 2: For single family individually owned residential households, how has the price per acre changed over time and how do we expect it to change over the next five years?

##### Question 2 Importance:
The second analysis question examines for single-family individual ownership residential households, how has the price per acre changed over time and how is it expected to change over the next five years? This question is important because it evaluates the historical trends for the housing market in the near future given the events that have happened in the last couple of decades. These events, such as the 2008 recession and the 2020 COVID-19 pandemic, have had an impact on almost every corner of the United States economy, especially the housing market. 

For the purposes of this project, it was important to forecast possible changes, increases, or decreases, in housing sale prices based on the sale price over acreage within the next 5 years based on historical trends. While Wake County, North Carolina could not represent all states and major counties in the United States, it could be a good starting point to understand and analyze pricing trends since Wake County includes the capital of North Carolina, Raleigh, a major city. This analysis would help investors, stakeholders and companies hoping to sell residential property within the North Carolina housing market because they can see where they should focus their efforts while keeping track of the current market trends and prices. In addition, this analysis would be useful to aspiring homeowners within the county as they see if they should look forward to lower or higher prices in the near future or should get out of the market now.

##### Question 2 Manipulations:
To achieve the analysis required for question 2, data was manipulated in various fields. For instance, the Typedecode attribute was filtered to include only SINGLFAM descriptions, Apaownershipdesc to include only Individual, and Totalsaledate to include from 2002 to today. These filters were used because the focus was on more recent data for single-family individually-owned residential households. In addition, a calculated field was made using Totalsalevalue divided by Calcacreage to find the price per acreage. For the analysis, this calculated field was placed in the row section (y-axis) as a measure to get the average price per acreage and the Totalsaledate attribute was placed into columns (x-axis) as a dimension in months to track the average price per acre throughout 2002 to today in months. Using months made the visualization for the historical trend line more detailed and useful for our analysis purposes. On top of that, color was also applied as a mark to the forecast line and made it an attribute to have it connect to the historical line. This way, it is easier to differentiate between historical and forecast trends.

![image](https://github.com/user-attachments/assets/5fa76cef-f9d8-4363-8f57-6829471cd609)


## Analysis and Results:

#### Question 1 Analysis:

First, it is important to note that all the regression lines were statistically significant at a 95% confidence level (p-value < 0.05), meaning there is significant evidence that square footage is related to the total sale value.

When looking at the combined slope (which contains typedecode of church, fastfood, mult-ten, and singlfam), there is an r-squared value of ~51%. This implies that 51% of the variation in total sale value can be explained by square footage. This makes sense because other factors affect the value of real estate. This can be seen when a separate regression analysis is done on each typedecode, in which the r-squared values for each line change. The only line that the r-squared value does not change for is single family, which is believed to be due to the large amount of data points that are single family compared to the other types of real estate.

When looking at fastfood, the r-squared value is ~39%, which implies that less of the variation in total sale price is explained by square footage than for single-family properties. This is interpreted as indicating that other factors are more important to buyers than size. An example of this could be location; people are much more willing to go to a fast-food restaurant if it is in a shopping center compared to being hidden in a dark alley. Additionally, when looking at churches, the r-squared value is ~69%, which implies that more variation in total sale prices is explained by square footage for churches than for single-family properties. In this case, people care less about the location of a church and more about how many people can fit inside a church, which explains why square footage matters more in regards to price for churches.

Another large piece of data is the slopes of the different regression lines. Each type of real estate has a different slope, which implies that people are willing to pay more per square foot based on the real estate type. For example, the slope for fast food was $451.637/sqft, while single-family homes had a slope of $185.63/sqft. This implies that people may be willing to pay more for fast-food franchises of the same size than for single-family houses. This makes sense since real estate valuation is based on the cash the property can generate. For a single-family home, the cash is rent, while for a fast food franchise, the cash is from operating the business, which is significantly more than income from renting out a home.

Overall, this question is beneficial to real estate investors throughout Wake County as it provides insights into the different drivers in real estate valuation and what previous buyers have used to value the properties.

#### Question 2 Analysis:

By looking at the price per acre, it allows for comparing real estate valuation across different size houses by putting them on a unified scale. Something to note is how large this number is. However, having an acre of land is very expensive, and typically results in a relatively large valuation.


First, it is important to analyze the historical data presented. In 2008, there was the first noticeable decline in price per acre, which can be directly attributed to the 2008 financial crisis. Similarly, in 2020, there was a massive hike in price per acre, which can be attributed to the COVID-19 pandemic’s economy. Interest rates were near zero, which promoted real estate investments due to the ability to source capital at a cheap cost. This historical volatility has a large impact on future expectations. By using the forecasting ability in Tableau, the price per acre for the next 5 years was predicted. The 95% confidence interval is very wide, showing how volatile the real estate market in Wake County can be. Since there has been so much volatility in the past, the standard deviation is very large and is affecting the confidence in the projections. However, there is still 95% confidence that the average price per acre will increase over the next 5 years, which can be seen by the forecast.


This question is beneficial to investors because it shows the risks associated with investing in real estate in Wake County. While a common trend of an increase in price per acre over time is expected, the confidence interval and standard deviation express how risky and volatile real estate investments could be.


## Presentation:
[Group9_Project2_Presentation.pdf](https://github.com/user-attachments/files/17852351/Group9_Project2_Presentation.pdf)

## Tableau Packaged Workbook
Attached to the submission of this README.
