# IO_curve_descriptive_stats
<i>Descriptive statistics for input/output curves (slope and fiber volley)</i>


#### Spreadsheet setup
- 5 columns: "id", "group", "intensity", "slope", "fv"
- If columns have different names, the user must change those names in the "groupwisemeans()" function for confidence intervals
- All data for all groups should be entered in one spreadsheet, no need to separate out groups into worksheets or additional columns
- See the example below

                                                                                                 
        |   A  |   B   |     C     |     D    |     E   |                                             
       __________________________________________________                                              
       1|  id  | group | intensity |   slope  |    fv   |                                              
       2| A1.1 |  WT   |     0     | -0.00323 | -0.0043 |                                              
       3| A1.1 |  WT   |     50    | -0.03421 | -0.0211 |                                              
       4| A1.1 |  WT   |     100   | -0.52671 | -0.4521 |                                              
       2| A2.2 |  KI   |     0     | -0.00256 | -0.0023 |                                              
       3| A2.2 |  KI   |     50    | -0.07532 | -0.0215 |                                              
       4| A2.2 |  KI   |     100   | -0.64367 | -0.5212 |                                              
                                                                                                       
#### Changes to be made by the user
- <b>fileName</b>: This is the file path and file name with "//" separating folders (i.e. "C://Users//hspeed//Dropbox//Sync Data Analysis Computers//Gulf War Project//Statistics//R Scripts//IO Curve//IO Curve Per Slice.csv")
- <b> if the spreadsheet is in xlsx format</b>, comment-out ("#") the line with the "read.csv()" function
- If the spreadsheet is in the csv format, comment-out ("#") the line with the "read.xlsx()" function (default)

*Optional*
- If the data is set up any way other than the example, then 
  - The column numbers must be updated by the user for:
   ~~~~
   col.id           (Slice Number)
   col.group        (Group Name)
   col.intensity    (Intensity)
   col.slope        (Slope)
   col.fv           (Fiber Volley)
  ~~~~
  
- If the names of the columns are changed from the example spreadsheet, then the column names must be changed in the groupwisemeans() function to get the 5 and 95% confidence intervals

#### Dependencies
- dlpyr
- rcompanion 

#### Output CSV Spreadsheet ("..//analyzed//filename_analyzed.csv")
~~~~
group         (Treatment group or genotype)
n             (sample size per group)
intensity     (stimulus intensity)
slope.mean    (average slope)
slope.sd      (standard deviation of the slope mean)
slope.se      (standard error of the slope mean)
slope.conf5   (5% confidence interval of the slope mean)
slope.conf95  (95% confidence interval of the slope mean)
fv.mean       (mean of the fiber volley amplitude)
fv.sd         (standard deviation of the fv mean)
fv.se         (standard error of the fv mean)
fv.conf5      (5% confidence interval of the fv mean)
fv.conf95     (95% confidence interval of the fv mean)
~~~~

#### Reference Information
Author: Haley E. Speed, PhD

Department of Neurology and Neurotherapeutics

University of Texas Southwestern Medical Center, Dallas, TX

Copyright 2017
