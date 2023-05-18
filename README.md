# power-outage-analysis
## Our data set is a set of the major power outages that occurred in the US from January 2000 to July 2016. 
## Our question is *Where and when do major power outages tend to occur?*
> The data set provides much information about the area, the time, and the causes of the power outages. People should care because it can provide insight into the area where someone may want to live or where they may want to buy property it also provides insight that can help people to know when major outages are likely to occur and so they can prepare for an outage and be better informed. There are 1534 rows and 56 columns: 
> 
> OBS, YEAR, MONTH	U.S._STATE, POSTAL.CODE	NERC.REGION	CLIMATE.REGION, ANOMALY.LEVEL,	CLIMATE.CATEGORY, OUTAGE.START.DATE, OUTAGE.START.TIME, OUTAGE.RESTORATION.DATE, OUTAGE.RESTORATION.TIME, CAUSE.CATEGORY, CAUSE.CATEGORY.DETAIL, HURRICANE.NAMES, OUTAGE.DURATION, DEMAND.LOSS.MW, CUSTOMERS.AFFECTED,	RES.PRICE	COM.PRICE,	IND.PRICETOTAL.PRICE,	RES.SALES	COM.SALES,	IND.SALES,	TOTAL.SALES,	RES.PERCEN,	COM.PERCEN,	IND.PERCEN,	RES.CUSTOMERS,	COM.CUSTOMERS,	IND.CUSTOMERS,	TOTAL.CUSTOMERS,	RES.CUST.PCT,	COM.CUST.PCT IND.CUST.PCT,	PC.REALGSP.STATE, PC.REALGSP.US, PC.REALGSP.REL, PC.REALGSP.CHANGE, UTIL.REALGSP, TOTAL.REALGSP, UTIL.CONTRI, PI.UTIL.OFUSA, POPULATION	POPPCT_URBAN, POPPCT_UC, POPDEN_URBAN, POPDEN_UC, POPDEN_RURAL, AREAPCT_URBAN, AREAPCT_UC, PCT_LAND, PCT_WATER_TOT, PCT_WATER_INLAND 
>
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
First, we had to format the data frame in order to include only the columns that had information from the excel file. We did this using dataframe manipulation, setting OBS as our index and then creating OUTAGE.START and OUTAGE.RESTORATION which were stored as timestamps. We then selected the most relevant columns to our question and stored those columns in a new data frame. After this new dataframe was created, we assigned the appropriate data types for each column so that we could perform data manipulation on those columns.
### Cleaned DF Head
|   YEAR |   MONTH | U.S._STATE   | POSTAL.CODE   | NERC.REGION   | CLIMATE.REGION     | CLIMATE.CATEGORY   |   ANOMALY.LEVEL | CAUSE.CATEGORY     |   OUTAGE.DURATION |   CUSTOMERS.AFFECTED |   TOTAL.PRICE |   TOTAL.CUSTOMERS |   POPULATION |   PCT_LAND |   PCT_WATER_TOT |   PCT_WATER_INLAND | OUTAGE.START        | OUTAGE.RESTORATION   |
|-------:|--------:|:-------------|:--------------|:--------------|:-------------------|:-------------------|----------------:|:-------------------|------------------:|---------------------:|--------------:|------------------:|-------------:|-----------:|----------------:|-------------------:|:--------------------|:---------------------|
|   2011 |       7 | Minnesota    | MN            | MRO           | East North Central | normal             |            -0.3 | severe weather     |              3060 |                70000 |          9.28 |           2595696 |      5348119 |    91.5927 |         8.40733 |            5.47874 | 2011-07-01 17:00:00 | 2011-07-03 20:00:00  |
|   2014 |       5 | Minnesota    | MN            | MRO           | East North Central | normal             |            -0.1 | intentional attack |                 1 |                  nan |          9.28 |           2640737 |      5457125 |    91.5927 |         8.40733 |            5.47874 | 2014-05-11 18:38:00 | 2014-05-11 18:39:00  |
|   2010 |      10 | Minnesota    | MN            | MRO           | East North Central | cold               |            -1.5 | severe weather     |              3000 |                70000 |          8.15 |           2586905 |      5310903 |    91.5927 |         8.40733 |            5.47874 | 2010-10-26 20:00:00 | 2010-10-28 22:00:00  |
|   2012 |       6 | Minnesota    | MN            | MRO           | East North Central | normal             |            -0.1 | severe weather     |              2550 |                68200 |          9.19 |           2606813 |      5380443 |    91.5927 |         8.40733 |            5.47874 | 2012-06-19 04:30:00 | 2012-06-20 23:00:00  |
|   2015 |       7 | Minnesota    | MN            | MRO           | East North Central | warm               |             1.2 | severe weather     |              1740 |               250000 |         10.43 |           2673531 |      5489594 |    91.5927 |         8.40733 |            5.47874 | 2015-07-18 02:00:00 | 2015-07-19 07:00:00  |
##
# Plot of Year
<iframe src="assets/Year_plot.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%" ></iframe>
# Plot of Climate
<iframe src="assets/Climate_plot.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%"></iframe>
