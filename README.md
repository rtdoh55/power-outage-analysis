# power-outage-analysis
## Our data set is a set of the major power outages that occurred in the US from January 2000 to July 2016. 
## Our question is *Where and when do major power outages tend to occur?*
> The data set provides much information about the area, the time, and the causes of the power outages. People should care because it can provide insight into the area where someone may want to live or where they may want to buy property it also provides insight that can help people to know when major outages are likely to occur and so they can prepare for an outage and be better informed. There are 1534 rows and 56 columns: OBS, YEAR, MONTH	U.S._STATE, POSTAL.CODE	NERC.REGION	CLIMATE.REGION, ANOMALY.LEVEL	CLIMATE.CATEGORY, OUTAGE.START.DATE, OUTAGE.START.TIME, OUTAGE.RESTORATION.DATE, OUTAGE.RESTORATION.TIME, CAUSE.CATEGORY, CAUSE.CATEGORY.DETAIL, HURRICANE.NAMES, OUTAGE.DURATION, DEMAND.LOSS.MW, CUSTOMERS.AFFECTED	RES.PRICE	COM.PRICE	IND.PRICETOTAL.PRICE	RES.SALES	COM.SALES	IND.SALES	TOTAL.SALES	RES.PERCEN	COM.PERCEN	IND.PERCEN	RES.CUSTOMERS	COM.CUSTOMERS	IND.CUSTOMERS	TOTAL.CUSTOMERS	RES.CUST.PCT	COM.CUST.PCT	IND.CUST.PCT	PC.REALGSP.STATE, PC.REALGSP.US, PC.REALGSP.REL, PC.REALGSP.CHANGE, UTIL.REALGSP, TOTAL.REALGSP, UTIL.CONTRI, PI.UTIL.OFUSA, POPULATION	POPPCT_URBAN, POPPCT_UC, POPDEN_URBAN, POPDEN_UC, POPDEN_RURAL, AREAPCT_URBAN, AREAPCT_UC	PCT_LANDPCT_WATER_TOT, PCT_WATER_INLAND 
>
### The columns we found relevant were:
1.CUSTOMERS.AFFECTED: The total customers affected
2.POPULATION: The total population of the area
3.CLIMATE.REGION: The climate region of the area 
4.U.S._STATE: The state in the US where the outage occurred
5.MONTH: The month When the outage occurred
6.CLIMATE.CATEGORY: How hot or cold the climate was during the outage
7.OUTAGE.DURATION: Time duration of the outage
8.CUSTOMERS.AFFECTED: Numbers of customers of the electric company affected by the outage
9.TOTAL.CUSTOMERS: Total number of customers of the electric company
10.POPULATION: Population of the area
11.PCT_WATER_INLAND: What percentage of water is inland in the area
12.OBS: index

# Exploratory Data Analysis

# Plot of Year
<iframe src="assets/Year_plot.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%" ></iframe>
# Plot of Climate
<iframe src="assets/Climate_plot.html" width=800 height=600 frameBorder=0  style = "position: relative; right: 30%"></iframe>
