# power-outage-analysis
## Our data set is a set of the major power outages that occurred in the US from January 2000 to July 2016. 
## Our question is *Does where and when major power outages tend to occur affect the duration of the outage*
> The data set provides much information about the area, the time, and the causes of the power outages. People should care because it can provide insight into the area where someone may want to live or where they may want to buy property it also provides insight that can help people to know when major outages are likely to occur and so they can prepare for an outage and be better informed. There are 1534 rows and 56 columns: 
> 

**OBS, YEAR, MONTH	U.S._STATE, POSTAL.CODE	NERC.REGION	CLIMATE.REGION, ANOMALY.LEVEL,	CLIMATE.CATEGORY, OUTAGE.START.DATE, OUTAGE.START.TIME, OUTAGE.RESTORATION.DATE, OUTAGE.RESTORATION.TIME, CAUSE.CATEGORY, CAUSE.CATEGORY.DETAIL, HURRICANE.NAMES, OUTAGE.DURATION, DEMAND.LOSS.MW, CUSTOMERS.AFFECTED,	RES.PRICE	COM.PRICE,	IND.PRICETOTAL.PRICE,	RES.SALES	COM.SALES,	IND.SALES,	TOTAL.SALES,	RES.PERCEN,	COM.PERCEN,	IND.PERCEN,	RES.CUSTOMERS,	COM.CUSTOMERS,	IND.CUSTOMERS,	TOTAL.CUSTOMERS,	RES.CUST.PCT,	COM.CUST.PCT IND.CUST.PCT,	PC.REALGSP.STATE, PC.REALGSP.US, PC.REALGSP.REL, PC.REALGSP.CHANGE, UTIL.REALGSP, TOTAL.REALGSP, UTIL.CONTRI, PI.UTIL.OFUSA, POPULATION	POPPCT_URBAN, POPPCT_UC, POPDEN_URBAN, POPDEN_UC, POPDEN_RURAL, AREAPCT_URBAN, AREAPCT_UC, PCT_LAND, PCT_WATER_TOT, PCT_WATER_INLAND**

### The columns we found relevant were:
1. CUSTOMERS.AFFECTED: The total customers affected
2. POPULATION: The total population of the area
3. CLIMATE.REGION: The climate region of the area 
4. U.S._STATE: The state in the US where the outage occurred
5. MONTH: The month When the outage occurred
6. CLIMATE.CATEGORY: How hot or cold the climate was during the outage
7. OUTAGE.DURATION: Time duration of the outage
8. CUSTOMERS.AFFECTED: Numbers of customers of the electric company affected by the outage
9. TOTAL.CUSTOMERS: Total number of customers of the electric company
10. POPULATION: Population of the area
11. PCT_WATER_INLAND: What percentage of water is inland in the area
12. OBS: index

# Exploratory Data Analysis
### Data cleaning
First, we had to format the data frame in order to include only the columns that had information from the excel file. We did this using dataframe manipulation, setting OBS as our index and then creating OUTAGE.START and OUTAGE.RESTORATION which were stored as timestamps. We then selected the most relevant columns to our question and stored those columns in a new data frame. After this new dataframe was created, we assigned the appropriate data types for each column so that we could perform data manipulation on those columns. At the end, we added a fillna function to fill any missing values with NaN, that way we would have uniform missing values.
### Cleaned DF Head
  
|   YEAR |   MONTH | U.S._STATE   | POSTAL.CODE   | NERC.REGION   | CLIMATE.REGION     | CLIMATE.CATEGORY   |   ANOMALY.LEVEL | CAUSE.CATEGORY     |   OUTAGE.DURATION |   CUSTOMERS.AFFECTED |   TOTAL.PRICE |   TOTAL.CUSTOMERS |   POPULATION |   PCT_LAND |   PCT_WATER_TOT |   PCT_WATER_INLAND | OUTAGE.START        | OUTAGE.RESTORATION   |
|-------:|--------:|:-------------|:--------------|:--------------|:-------------------|:-------------------|----------------:|:-------------------|------------------:|---------------------:|--------------:|------------------:|-------------:|-----------:|----------------:|-------------------:|:--------------------|:---------------------|
|   2011 |       7 | Minnesota    | MN            | MRO           | East North Central | normal             |            -0.3 | severe weather     |              3060 |                70000 |          9.28 |           2595696 |      5348119 |    91.5927 |         8.40733 |            5.47874 | 2011-07-01 17:00:00 | 2011-07-03 20:00:00  |
|   2014 |       5 | Minnesota    | MN            | MRO           | East North Central | normal             |            -0.1 | intentional attack |                 1 |                  nan |          9.28 |           2640737 |      5457125 |    91.5927 |         8.40733 |            5.47874 | 2014-05-11 18:38:00 | 2014-05-11 18:39:00  |
|   2010 |      10 | Minnesota    | MN            | MRO           | East North Central | cold               |            -1.5 | severe weather     |              3000 |                70000 |          8.15 |           2586905 |      5310903 |    91.5927 |         8.40733 |            5.47874 | 2010-10-26 20:00:00 | 2010-10-28 22:00:00  |
|   2012 |       6 | Minnesota    | MN            | MRO           | East North Central | normal             |            -0.1 | severe weather     |              2550 |                68200 |          9.19 |           2606813 |      5380443 |    91.5927 |         8.40733 |            5.47874 | 2012-06-19 04:30:00 | 2012-06-20 23:00:00  |
|   2015 |       7 | Minnesota    | MN            | MRO           | East North Central | warm               |             1.2 | severe weather     |              1740 |               250000 |         10.43 |           2673531 |      5489594 |    91.5927 |         8.40733 |            5.47874 | 2015-07-18 02:00:00 | 2015-07-19 07:00:00  |
                                                      
### Univariate Analysis
# Plot of Month
This was a Histogram plot of the months where outages had occurred, we were able to see the months where the most outages occurred. Giving us a little insight as to which months were commonly associated with power outages. Overall, the trends that we noticed were that the summer months including June, July, and August seemed to contain more outages than other months.
<iframe src="assets/Month_plot.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%" ></iframe>
# Plot of Climate Region
This was a Histogram plot of the climate region where outages had occurred, we were able to see the climate region where the most outages occurred. This allowed us to make assumptions about the regions where a major outage would've been more likely to occur. Overall the trend we noticed was that the Northeast had significantly more outages compared to the rest of the regions. 
<iframe src="assets/Climate_plot.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%"></iframe>

## Bivariate Analysis
# Scatterplot of Total Outages in each Climate Region by Month
This was a scatter plot of the climate region where outages had occurred, we were able to see the climate region where the most outages occurred during each month. This allowed us to make assumptions about the regions where a major outage would've been more likely to occur during a particular month or group of months. The overall trend that we were noticing was that the Northeast Region typically had more outages and some of the summer months (June, July, and August) seemed to have higher averages than other months.
<iframe src="assets/bivariate.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%"></iframe>

# Histogram of Average Outage Duration in each Climate Region
This was a Histogram plot of the average duration of each outage per climate region, during each month. This allowed us to see how long outages would last and if the month or the climate region had any affect on the average duration of the outage. The trend we noticed stemmed from the other univariate analyses where we saw that Northeast and summer months (June, July, and August) would have higher total outages. We thought that because of this, it could potentially affect the average duration of the outage. We did notice this trend in our histogram and decided to explore it.
<iframe src="assets/outage_duration.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%"></iframe>

## Aggregate data frames
## Mean of grouping by Month and Climate Region
This was a grouped dataframe based off of Month and Climate Region and the aggregate function was mean. This helped us to further analyze the average Outage duration for Summer months (June, July, and August) that were in the Northeast. (This is only the tail of the dataframe)

|                            |   OUTAGE.DURATION |   CUSTOMERS.AFFECTED |   TOTAL.CUSTOMERS |   POPULATION |   PCT_WATER_INLAND |   PERCENT.AFFECTED |   MAJOR_OUTAGE |
|:---------------------------|------------------:|---------------------:|------------------:|-------------:|-------------------:|-------------------:|---------------:|
| (12, 'Southeast')          |           1241.22 |              51928.8 |       4.50819e+06 |  9.22126e+06 |           4.84635  |           0.695066 |       0.666667 |
| (12, 'Southwest')          |           1450.57 |             100000   |       2.14067e+06 |  4.97991e+06 |           1.57514  |           1.29752  |       0.285714 |
| (12, 'West')               |           2687.52 |             298283   |       1.40776e+07 |  3.54609e+07 |           1.69005  |           1.12886  |       0.44     |
| (12, 'West North Central') |           5160    |              24750   |  682512           |  1.22901e+06 |           1.53961  |           2.94014  |       1        |
| (12, 'nan')                |           1367    |             294000   |  472025           |  1.33221e+06 |           0.384193 |          22.0685   |       1        |

# Assessment of Missingness
### NMAR Analysis
Outage.Duration could be NMAR, it could be that during the power outage they didn't have the capabilites to record the duartion. Therefore, the missing data occurrred because someone forgot to or was unable to (for lack of equipment or otherwise) take the time during the power outage. The data that we would like to have is whether they had equipment (or capability) to measure time effectively from the start of the outage to the end. Wth this data it could change from NMAR to MAR because if we know that equipment was missing or if they had no proper way to measure it. Then we can see a direct dependence of the power outage duration being missing on the lack of equipment available or the lack of capability.

### Missingness Dependency
## Month and Climate Region
For Month and Climate Region we saw that climate region seemed to depend on Month. Whenever there was a missing value in the Month, there was also a missing value in the Climate region. We created a new column by converting the month column into a boolean column of values indicating whether it was NaN or not. Our choice of test statistic was Total Variation Distance and we found an observed test statistic of 1. We ran a permutation test, shuffling the new boolean column and calculating a TVD for each shuffle. Our observed p-value was 0, and so it was clear that the Month column had a clear effect on the Climate region.
<iframe src="assets/TVDdist.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%"></iframe>

## Climate Region and Population
For Climate Region and Population, we chose them because we saw that there seemed to be no correlation between the population and whether there were missing values or not in the Climate Region column. We created a new column by converting the Climate Region column into a boolean column of values indicating whether it was NaN or not. Our choice of test statistic was Total Variation Distance and we found an observed test statistic of .219. We ran a permutation test, shuffling the new boolean column and calculating a TVD for each shuffle. Our observed p-value was .9994, and so it was clear that the Population column had no effect on whether the Climate region column had missing values or not.
<iframe src="assets/TVDdist2.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%"></iframe>


# Hypothesis Testing
### Null hypothesis: Power outage durations are not dependent on location nor time
### Alternative hypothesis: Power outage durations tend to be higher in Summer, in the Northeast
Our chosen test statistic was the mean outage duration with a significance level of 5%, our resulting p-value was .04 and our conclusion was that we reject the null. These choices are good because our null through this hypothesis testing is that power outages and not dependent on location nor time. By finding a case where this isn't exactly true, we can help answer our question because when power outage duration is significant enough to reject the null, we are able to know that there is possibly a correlation between location and time and the duration of the outage.
<iframe src="assets/Null_dist.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%"></iframe>
