# surfs_up

![image](https://user-images.githubusercontent.com/90691846/141687701-0f9bed08-c8ac-4d7a-baa3-0d821fb0959a.png)

## Overview
Tasked with analysis of temperature data for the months of June and December in Oahu, Hawaii. This analysis will determine sustainability of opening a surf and ice cream shop to ensure it is a valid investment before establishing the business.

## Results
Evaluation of the data for the months of June and Decmeber relayed the below summary statistics:

![image](https://user-images.githubusercontent.com/90691846/141687951-dab40345-e7cb-4e20-8e86-89877f29d8ef.png)

![image](https://user-images.githubusercontent.com/90691846/141687969-28d04553-7b95-4e7e-a54c-188e2a7904ae.png)

A few observations of the data are described below:
- Average temperatures for both months is similar with only a 3 degree variance, 74.9 in June and 71 in December
- Similarly, both months have an almost identical max temperature with 85 in June and 83 in December
- Largest variance between the two months in the minimum temperature where June is 64 and Decemeber is 56

## Summary
The summary statistics show viability of maintiaing a surf and ice cream shop year round. Temperatures are similar in both June and December with only slight variances as described in the results above. 
Another helpful query would be to review the precipitation data for each month. with the following queries:

```
june_prcp = session.query(Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()
june_prcp_df = pd.DataFrame(june_prcp, columns=['June Precip'])
june_prcp_df.describe()
```

The June precipitation data returns the following summary statistics.

![image](https://user-images.githubusercontent.com/90691846/141688806-4ea347a3-b3f6-4163-bcd9-bbc6ddb913fc.png)

Similarly, we can run the same query but filter on December results instead of June with the below query:

```
dec_prcp = session.query(Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()
dec_prcp_df = pd.DataFrame(dec_prcp, columns=['December Precip'])
dec_prcp_df.describe()
```

The December data returns the following summary statistics:

![image](https://user-images.githubusercontent.com/90691846/141688849-89fab70e-fb70-458e-bd1c-d9d823f1b516.png)

The precipitation data along with the temperature data show that the createion of a surf and ice cream ship is still a sustainable enterprise venture.
December does have a slightly greater average of participation but is still minimal in comparison to June.


