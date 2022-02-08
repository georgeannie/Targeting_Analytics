Python Code - here
Calculates the difference in time, UTM-easting, UTM-northing, and raw height for consecutive events by a single wolf. Note that the first measurement for each wolf will have NaN (Null) as the difference.

Differences are used to calculate new features:
- distance: three-dimensional distance traveled in meters since last measurement, calculated using Euclidean method: for easting, northing, and height
- elasped hours: number of hours between consecutive measurements
- speed m/hr: distance divided by hours

Tableau Visuzaliztion - here 

Data - "cleaned.csv.zip" in Data folder
