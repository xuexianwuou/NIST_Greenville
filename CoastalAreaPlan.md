
# Meeting with Kendra on 11am 09/27/2016 (Tuesday)



## 1) How to place the Shelby County in the Pamlico River area?
-------
>Attached is the options Alessandro (from UIUC) provided. I knew you worked that area for many years, so based on your experience, which option is the most favorable in term of taking the full advantage of the capacity of your couple model (ADCIRC + SWAN + Hydrological model + HEC-RAS model)? We would love to know your thoughts/suggestions on this. And then we can make the final choice and get the interesting points from UIUC to let your model export the simulations. I also attached the sample hurricane tracks in this area.
    
**Sample Tracks**: 
![Tracks](https://github.com/xuexianwuou/NIST_Greenville/blob/master/Figures/Tracks.pdf)

**Possible locations for Shelby County**
-----

**Note from UIUC**: 
```    
-   The contour of Shelby County includes, in the western part, the Mississippi River. Therefore, in option 10 the superimposition with the Pamlico river is negligible     
-  Options 6 and 8 are those where the contour of Shelby County is closest to the shoreline
-  In option 8 the part of Shelby County superimposed to the Neuse River (on the south) is almost completely a park (Meeman-Shelby Forest State Park)
```

| **Shelby vs Pamlico River Area** ![Shelby vs Pamlico River Area](https://github.com/xuexianwuou/NIST_Greenville/blob/master/Figures/Possible_locations_for Shelby_County/Slide1.png "Shelby vs Pamlico River Area") |
|------------------------------|
| **All Shelby County contour on dryland** ![All Shelby County contour on dryland](https://github.com/xuexianwuou/NIST_Greenville/blob/master/Figures/Possible_locations_for Shelby_County/Slide2.png "All Shelby County contour on dryland")|
| **A side of Shelby County along the river (small superimposition with the river)** ![A side of Shelby County along the river (small superimposition with the river)](https://github.com/xuexianwuou/NIST_Greenville/blob/master/Figures/Possible_locations_for Shelby_County/Slide3.png "A side of Shelby County along the river (small superimposition with the river)") |
| **Memphis area close the river (large superimposition with the river)** ![Memphis area close the river](https://github.com/xuexianwuou/NIST_Greenville/blob/master/Figures/Possible_locations_for Shelby_County/Slide4.png "Memphis area close the river")  |
 
----
**OU Options**

**Shelby real and Shrinked Polygon** Please note that the blue polygon is the real Shelby County and read polygon is the shrinked polygon ![Shelby real and Shrinked Polygon](https://github.com/xuexianwuou/NIST_Greenville/blob/master/Figures/ForShelbyCountyTo.pdf "Shelby County Real and Shrinked Polygon")
 
 
 
 


**Answer**:
>Kendra and Dr. Kolar will take a look at the information for the placement of Shelby County and give you our thoughts on it by either Thursday or Friday this week. 

## 2) How possible/difficult to change the landcover in your model after we place the Shelby County to this area?
-------

>We have discussed during the yesterday meeting,  could you find a time to see the possibility of this changes? If it will take a long time to do it, we should decide whether we should do it or not. 

**Answer**: 
>It would take us a little while to implement changes to the input of the model for the Manning's n values. Currently, we should probably leave the model as is and indicate that we would look at the changes in the results with the different Manning's n values as **future studies**.

## 3) How long the R-CLIPPER model will take from preparing the input to output the simulation for about 256 events from Hurricane data?  And how difficult to output precipitation with 30 arc-second ( around 1km) grid size.
-------
> - Maybe you need a mask file with 30 arc-second grid size, If you need, please let me know the extent, I will prepare it for you.
> - Could you also send me some sample output files from R-CLIPPER? Then I can program to convert the outputs to the format I will use in the hydrological model. 

**Answer**: 
>The R-CLIPPER model does not take long to run and we could probably complete the various runs necessary **in one to one and half weeks**. The big decision we have to determine is how many frequencies to look at. 

>Kendra thinks we should not change the grid from the 4 km one. The reason is that we would have to do some changing of the steps to run the model from what the graduate student has set up already. It is ready to run as is and we can use the domain that has already been developed for this area without much delay with the storm path files. 

## 4) How long the ADCIRC model will take from preparing the inputs to the simulation for 256 events? 
-------
>I will plan how long I should take to send you the simulated results for the hand-off points. And then I will ask UIUC group to prepare their interested points for you to export the simulation. Could you also send me some sample files to let me develop a program to deal with them in advance?

**Answer**: 
>ADCIRC will take a while to run. If we are running on Schooner, we have completed the Isabel run **(5 day 11 hours for time of hurricane), which took about 4 hours to run**. If we want to include the effects of the upstream rainfall in the riverine areas after the hurricane has passed, then we can run for another 4 to 5 hours to process this information. We do not have a dedicated queue on Schooner, so we will have to see how fast we can process things. 

>Additionally, I have files for Hurricane Isabel that can be used by the other group that is working to process our information. 

## 5) Could you send me the variables which will use in R-CLIPPER and ADCIRC model before next Monday or at least next week?
-------

.. After the meeting, I double checked and I found Jia is the only person who knows the Hurricane data, since he will leave next Monday, it is difficult to find him after he returned to China. If we have some questions about the data, it will take a long time to solve it without Jia’s help. 

Answer: 
>The wind information needed for ADCIRC is as follows (ascii format): 

-----------
[Meteorological Forcing Data (fort.22)](http://adcirc.org/home/documentation/users-manual-v51/input-file-descriptions/single-file-meteorological-forcing-input-fort-22/)


Notes for NWS=20 Generalized Asymmetric Holland Model (GAHM)

>The Generalized Asymmetric Holland Model (GAHM) provides a set of theoretical and practical improvements over previous parametric meteorological vortex models in ADCIRC. The theory and implementation of the GAHM was initially described at the 2013 ADCIRC Users Group Meeting.

- **Forecast time in hours (column 6); enter the time in hours in each record starting at 0**

- **Latitude of the eye (column 7)**

- **Longitude of the eye (column 8)**

- Maximum sustained wind speed in knots (column 9)

- Minimum sea level pressure in MB (column 10)

- Wind intensity in knots of the radii defined in the record (34, 50, 64 or 100 knots) (column 12)

- Radius of specified wind intensity for quadrants 1, 2, 3, 4 in NM (columns 14, 15, 16, 17); ? 0

- Background pressure in MB (column 18); a standard value of 1013 can be used

- Rmax as reported in the ATCF BEST TRACK file in column 20

- Storm Name in Column 28 ATCF file format

- Time Record number in column 29. There can be multiple lines for a given time record depending on the number of isotachs reported in the ATCF File

- number of isotachs reported in the ATCF file for the corresponding Time record.

- Columns 31-34 indicate the selection of radii for that particular isotach. 0 indicates do not use this radius, and 1 indicates use this radius and corresponding wind speed.

- Columns 35-38 are the designated Rmax values computed for each of the quadrants selected for each particular isotach.

- Column 39 is the Holland B parameter computed using the formulas outlines in the Holland paper, and implemented using the aswip program.

- Column 40-43 is the quadrant-varying Holland B parameter

- Column 44-47 are the quadrant-varying Vmax calculated at the top of the planetary boundary (a wind reduction factor is applied to reduce the wind speed at the boundary to the 10-m surface)

----
|1)2|)|3)Date_Time|4)|5)|
|---|---|---|

|1)Longitude|Latitude|
|-------:|--------:|
|-31.4000000000 |13.8000000000|
----

|1) State Name??|2) ??|3)Date & Time|4) ?? |5) ?? |6) Forecast Time in Hours, start with 0|7) Lat |8) Lon| 9) Maximum Sustained wind speed in knots| 10) Minimum Sea Level Pressure in MB| 11) ??   |12) Wind intensity in knots of the radii defined in the record| 13)??| 14) Radius of specified wind intensity for quadrants 1 in NM| 15) Radius of specified wind intensity for quadrants 2 in NM|  16) Radius of specified wind intensity for quadrants 3 in NM|  17) Radius of specified wind intensity for quadrants 4 in NM | 18) *Background pressure in MB; a standard value of 1013 can be used* | 19) ??    | 20) Rmax as reported in the ATCF BEST TRACK file  |  21) ??    | 22) ??    | 23) ??    | 24) ??    | 25) ??    | 26) ??|  27) ??| 28) *Storm Name in Column 28 ATCF file format* | 29) Time Record number. There can be multiple lines for a given time record depending on the number of isotachs reported in the ATCF File | 30) number of isotachs reported in the ATCF file for the corresponding Time record.| 31) the selection of radii for that particular isotach. 0 indicates do not use this radius, and 1 indicates use this radius and corresponding wind speed. | 32) the selection of radii for that particular isotach. 0 indicates do not use this radius, and 1 indicates use this radius and corresponding wind speed.| 33) the selection of radii for that particular isotach. 0 indicates do not use this radius, and 1 indicates use this radius and corresponding wind speed. | 34) the selection of radii for that particular isotach. 0 indicates do not use this radius, and 1 indicates use this radius and corresponding wind speed. |  35) the designated Rmax values computed for each of the quadrants selected for each particular isotach |  36) the designated Rmax values computed for each of the quadrants selected for each particular isotach |  37) the designated Rmax values computed for each of the quadrants selected for each particular isotach |  38) the designated Rmax values computed for each of the quadrants selected for each particular isotach |  39) he Holland B parameter computed using the formulas outlines in the Holland paper, and implemented using the aswip program| 40) the quadrant-varying Holland B parameter| 41) the quadrant-varying Holland B parameter|  42) the quadrant-varying Holland B parameter| 43) the quadrant-varying Holland B parameter|  44) the quadrant-varying Vmax calculated at the top of the planetary boundary (a wind reduction factor is applied to reduce the wind speed at the boundary to the 10-m surface)| 45) the quadrant-varying Vmax calculated at the top of the planetary boundary (a wind reduction factor is applied to reduce the wind speed at the boundary to the 10-m surface)| 46) the quadrant-varying Vmax calculated at the top of the planetary boundary (a wind reduction factor is applied to reduce the wind speed at the boundary to the 10-m surface) | 47) the quadrant-varying Vmax calculated at the top of the planetary boundary (a wind reduction factor is applied to reduce the wind speed at the boundary to the 10-m surface)|
|---|----|----|---|---|---|---|---|---|---|---|---|---|---|
|AL| 12| 2005082318|   | BEST|   0| 231N|  751W|  30| 1008|   |   0| NEQ|    0|    0|    0|    0| 1013|     |  30|     |    |    |    |    |299|   6|    TWELVE  |   1|    1| 1| 1| 1| 1|     30.0|   30.0|   30.0|   30.0|    1.2996|   1.5957|   1.5957|   1.5957|   1.5957|  28.0258|  28.0258|  28.0258|  28.0258|
|AL| 12| 2005082400|   | BEST|   6| 234N|  757W|  30| 1007|   |   0| NEQ|    0|    0|    0|    0| 1013|     |  40|     |    |    |    |    |299|   6|    TWELVE  |   2|    1| 1| 1| 1| 1|     40.0|   40.0|   40.0|   40.0|    1.0830|   1.4219|   1.4219|   1.4219|   1.4219|  28.0258|  28.0258|  28.0258|  28.0258|
|AL| 12| 2005082406|   | BEST|  12| 238N|  762W|  30| 1007|   |   0| NEQ|    0|    0|    0|    0| 1013|     |  40|     |    |    |    |    |311|   6|    TWELVE  |   3|    1| 1| 1| 1| 1|     40.0|   40.0|   40.0|   40.0|    1.0911|   1.4366|   1.4366|   1.4366|   1.4366|  28.1298|  28.1298|  28.1298|  28.1298|
|AL| 12| 2005082412|   | BEST|  18| 245N|  765W|  35| 1006|   |  34| NEQ|   60|   60|    0|    0| 1013|     |  55|     |    |    |    |    |339|   8|   KATRINA  |   4|    1| 1| 1| 1| 1|     60.0|   60.0|   23.7|   23.7|    1.2826|   1.7877|   1.9244|   1.4895|   1.4895|  32.6839|  34.1580|  32.9429|  32.9429|
|AL| 12| 2005082418|   | BEST|  24| 254N|  769W|  40| 1003|   |  34| NEQ|   60|   60|    0|    0| 1013|     |  55|     |    |    |    |    |338|  10|   KATRINA  |   5|    1| 1| 1| 1| 1|     38.9|   37.9|   14.6|   14.6|    1.1610|   1.4436|   1.4365|   1.2650|   1.2650|  37.4605|  37.4605|  37.4605|  37.4605|
|AL| 12| 2005082500|   | BEST|  30| 260N|  777W|  45| 1000|   |  34| NEQ|   60|   60|    0|    0| 1013|     |  55|     |    |    |    |    |310|   9|   KATRINA  |   6|    1| 1| 1| 1| 1|     28.0|   32.6|   11.5|   19.1|    1.1857|   1.3682|   1.3989|   1.2597|   1.3099|  43.1641|  43.1641|  43.1641|  43.1641|
|AL| 12| 2005082506|   | BEST|  36| 261N|  784W|  50|  997|   |  34| NEQ|   60|   60|    0|    0| 1013|     |  30|     |    |    |    |    |279|   6|   KATRINA  |   7|    2| 1| 1| 1| 1|     24.2|   29.3|   16.0|   12.2|    1.3030|   1.4513|   1.4832|   1.4005|   1.3772|  50.1993|  50.1993|  50.1993|  50.1993|
|AL| 12| 2005082506|   | BEST|  36| 261N|  784W|  50|  997|   |  50| NEQ|   15|    0|    0|    0| 1013|     |  30|     |    |    |    |    |279|   6|   KATRINA  |   7|    2| 1| 0| 0| 0|     15.0|    0.0|    0.0|    0.0|    1.3030|   1.4208|   1.3453|   1.3453|   1.3453|  50.6905|  50.1993|  50.1993|  50.1993|
|AL| 12| 2005082512|   | BEST|  42| 262N|  790W|  55|  994|   |  34| NEQ|   60|   60|   30|   50| 1013|     |  15|     |    |    |    |    |281|   5|   KATRINA  |   8|    2| 1| 1| 1| 1|     21.5|   24.7|   12.7|   19.1|    1.3772|   1.5015|   1.5203|   1.4499|   1.4871|  56.2395|  56.2395|  56.2395|  56.2395|
|AL| 12| 2005082512|   | BEST|  42| 262N|  790W|  55|  994|   |  50| NEQ|   20|   20|    0|    0| 1013|     |  15|     |    |    |    |    |281|   5|   KATRINA  |   8|    2| 1| 1| 0| 0|     12.8|   20.0|    0.0|    0.0|    1.3772|   1.4508|   1.5521|   1.4127|   1.4219|  56.2395|  57.3971|  56.2395|  56.2395|

-----

**Drs. Wang and Xue will figure out which variables will be provided from the hurricane data**

_Below is the list of variables in Hurricane data with 2-hour_:

|Variable Name| var | Description|
|---|
|Year| yearstore| (1 x m array): This file is only present in event sets spanning multiple years. It contains the year of the first datum of each event|
|Month| monthstore|(m x n array): The calendar month of 2‐hour points along each track.|
|Day|daystore| (m x n array): The day of the month of 2‐hour points along each track.|
|Hour| hourstore| (m x n array): The Greenwich Mean Time of 2‐hour points along each track.|
|Latitude | latstore | (m x n array): The latitude of 2‐hour points along each track.|
|longitude  | longstore|  (m x n array): The longitude of 2‐hour points along each track.|
|Central pressure | pstore | (m x n array): The central surface pressure (hPa) of 2‐hour points along each track.|
|Relative humidity | rhstore |(m x n array): Relative humidity (%) of the environment at 600 hPa at each 2‐hour point along each track.|
| The radius of maximum circular wind|rmstore| (m x n array): The radius (km) of maximum circular wind of 2‐hour points along each track.|
| The radius of maximum circular wind of any secondary wind maxima present|rmsestore| (m x n array): The radius (km) of maximum circular wind of any secondary wind maxima present (0 if absent), of 2‐hour points along each track. Set to zero of there are no secondary eyewalls.|
|RMW | | The radius of maximum wind|
|Windshear| shearstore | (m x n array): The magnitude of the 850‐250 hPa environmental wind shear (m/s) at each 2‐ hour point along each track.|
|Temperature of environment at 600hPa|T600store |(m x n array): Temperature (K) of the environment at 600 hPa at each 2‐hour point along each track.|
|Environmental wind velocity at 850 hPa|u850store |(m x n array): The zonal component of the 850 hPa environmental wind speed at each 2‐hour point along each track (not provided in all event sets).|
|Potential intensity (in wind speed)|vpstore| (m x n array): The potential intensity (knots) at each 2‐hour point along each track.|
|Maximum circular wind speed| vstore |(m x n array): The maximum circular wind speed at each 2‐hour point along each track. Note that a fraction of the translation speed is generally added to this to define the actual maximum wind speed, interpreted as a one‐minute average at 10 m altitude.|
|Secondary eyewall maximum wind speed (if any)|vsestore| (m x n array): The maximum circular wind speed of maximum circular wind of any secondary eyewalls that may be present, at each 2‐hour point along each track. Set to zero of there are no secondary eyewalls. Note that a fraction of the translation speed is generally added to this to define the actual maximum wind speed, interpreted as a one‐minute average at 10 m altitude.|



The file format of the variables from Hurricane will be as following (This is just an example):

|3)Date & Time|6) Forecast Time in Hours, start with 0|7) Lat |8) Lon|9) Maximum Sustained wind speed in knots| 10) Minimum Sea Level Pressure in MB| 11) ??   |12) Wind intensity in knots of the radii defined in the record| 13)??| 14) Radius of specified wind intensity for quadrants 1 in NM| 15) Radius of specified wind intensity for quadrants 2 in NM|  16) Radius of specified wind intensity for quadrants 3 in NM|  17) Radius of specified wind intensity for quadrants 4 in NM |
|---|---|
|2005082318| 0| 231N|  751W|  30| 1008|   |   0| NEQ|    0|    0|    0|    0|


## 5) Could you send me the variables which will use in R-CLIPPER model before next Monday or at least next week?
-------

**Answer**:


1) Input to R-CLIPER:
>As I mentioned before, R-CLIPER only needs the storm path information in a file for it to develop the rain for the storm. The additional information is whether the storms is considered a Tropical Storm or one of the five categories of the hurricanes (Cat 1-5). It will develop a rain field from this information. The file structure for the storm path is as follows (in csv format):

>Longitude of eye   Latitude of eye  Filename for each hour (repeat line every hour) 

|Longitude|Latitude|
|-------:|--------:|
|-31.4000000000 |13.8000000000|
|-31.6111207131 |13.8182041342|
|-31.8258523541 |13.8359374670|
|-32.0431526823 |13.8530806224|
|-32.2619764710 |13.8695290582|

>There are two example file attached and are named 20030906_ Isabel_1-hInterpolated.csv and one that has trimmedtoDomain - the difference between them is one is the full path of the storm while the trimmed to domain is the information on the storm with the grid utilized by R-CLIPER. The trimmed to domain will take less time to run and we can provide define these from the full path of the storm.

|Longitude|Latitude|Path|
|-------:|--------:|----|
|-73.5000000000 |31.5000000000 |xmrg0918200300z|
|-73.6205116362 |31.6532751037 |xmrg0918200301z|
|-73.7467036414 |31.8127613913 |xmrg0918200302z|
|-73.8781693047 |31.9778186094 |xmrg0918200303z|
|-74.0144930026 |32.1478055892 |xmrg0918200304z|

2) Output from R-CLIPER:
>The output from R-CLIPER can be either in the rain rates for every hour or an accumulated rainfall amount over the course of the storm. The hourly files are developed in two ascii formats and one goes to the information necessary for HL-RDHM and the other one is just a general result. I don't know if CREST can use the some input files as HL-RDHM or not? The format for the general file is as follows: 

|HRAP_x|HRAP_y|Longitude|Latitude|Rainfall rate (mm/hr)|radius (km)|
|:----:|:----:|--------:|-------:|--------------------:|----------:|
|260 |237 |-78.609604 |31.649328 |0.0000 |498.3109|
|261 |237 |-78.572784 |31.633764 |0.0000 |494.9457|
|262 |237 |-78.535995 |31.618183 |0.0000 |491.6036|
|263 |237 |-78.499229 |31.602585 |0.0000 |488.2851|
|264 |237 |-78.462486 |31.586967 |0.0000 |484.9906|
|265 |237 |-78.425766 |31.571333 |0.0000 |481.7207|
|266 |237 |-78.389076 |31.555679 |0.0000 |478.4758|
|311 |241 |-76.685516 |30.955893 |0.0000 |350.2245|
|312 |241 |-76.649849 |30.939398 |0.5234 |348.7523|
|313 |241 |-76.614204 |30.922888 |0.5321 |347.3392|
|314 |241 |-76.578583 |30.906361 |0.5404 |345.9859|
|315 |241 |-76.542984 |30.889816 |0.5483 |344.6931|
|316 |241 |-76.507408 |30.873257 |0.5558 |343.4615|
|317 |241 |-76.471855 |30.856682 |0.5630 |342.2917|




>Information is given in the file for the domain that is experiencing rain. The parts of the domain that are outside the radius of the storm is not included in this file. An example of this is given the attached file named rainRate_CAT345... and xmrg ... 

>The accumulated rainfall is shown in file accumulatedRain ... This may not be useful in the hydrology model. 



## 6) Discuss the schedule for this project.
-------

.. After we solved the above the questions, I think we can make a plan for this project. 

**Answer**: 
> Underconstruction

## Note: A friendly reminder: the deadline of the submission of the full paper for review for the ICOSSAR 2017 conference is 15 Dec. 2016.
