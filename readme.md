# Wee Baby, Big Data

## Statistical analysis versus child-based insomnia: a parental survival aid

Rougly hacked together Python scripts to visualise sleep patterns and analyse the relationship between daytime sleep patterns and those of the subsequent night

`graphActivities.py` produces a graphical representation a of data-set of time spent carrying out daily activities, using the matplotlib library. 

`analyseData.py` processes the activity data into `dataItem` objects containing daily sleep time and duration information. Then produces graphical represtentions of said data items and carries out a regression analysis to determine daily sleep patterns corresponding with increased or decreased sleep over the following night.

If you find this useful or have any suggestions for additions or improvements, let me know at butleraidan at gmail dot com.

## Use Instructions

Written in Python 2.7.

Activities over time visualisation:

    python graphActivities.py

Analysis processing and visualisation:

	python analyseData.py

## Input
 
The dataset used should be one or more `.csv` files with the following format:

    SleepStartDate,SleepStartTime,SleepStopTime
    17/03/17,23:45,07:25
    19/03/17,01:05,09:10
    19/03/17,23:50,08:25

Visualisation shows hours of the day on the y-axis and calendar days on the x-axis.

Activities over time visualisation:

![Output example](https://github.com/ambidextrous/weeBabyBigData/blob/master/activityData.jpg "Ouput Example")

## Analysis

Hours slept night and day graph:

![Hours slept night and day](https://github.com/ambidextrous/weeBabyBigData/blob/master/hoursSleptNightAndDayBarchart.jpg "Hours slept night and day")

Mean day sleep time graph:

![Mean day sleep time](https://github.com/ambidextrous/weeBabyBigData/blob/master/meanDaySleeptimeLineGraph.jpg "Mean day sleep time")

Longest continuous sleep night and day graph:

![Longest continuous sleep night and day](https://github.com/ambidextrous/weeBabyBigData/blob/master/longestContinuousSleepNightAndDayBarchart.jpg "Longest continuous sleep night and day")

# Multi-variable linear regression analysis

## Scatter plots

![Hours slept per night vs. hours slept per day scatter plot](https://github.com/ambidextrous/weeBabyBigData/blob/master/HourssleptpernightHourssleptperdayScatterplot.jpg "Hours slept per night vs. hours slept per day scatterplot")


![Hours slept per night vs. longest period of continuous sleep during day scatter plot](https://github.com/ambidextrous/weeBabyBigData/blob/master/HourssleptpernightLongestcontinuoussleepperiodduringdayScatterplot.jpg "Hours slept per night vs. longest period of continuous sleep during day scatterplot")


![Hours slept per night vs. hours slept per day scatter plot](https://github.com/ambidextrous/weeBabyBigData/blob/master/HourssleptpernightHourssleptperdayScatterplot.jpg "Hours slept per night vs. hours slept per day scatterplot")

![Hours slept per night vs. age in days scatter plot](https://github.com/ambidextrous/weeBabyBigData/blob/master/HourssleptpernightAgeindaysScatterplot.jpg "Hours slept per night vs. age in days scatterplot")

                            OLS Regression Results                            
    ==============================================================================
    Dep. Variable:        hoursSleptNight   R-squared:                       0.313
    Model:                            OLS   Adj. R-squared:                  0.208
    Method:                 Least Squares   F-statistic:                     2.964
    Date:                Thu, 13 Apr 2017   Prob (F-statistic):             0.0384
    Time:                        16:19:46   Log-Likelihood:                -32.299
    No. Observations:                  31   AIC:                             74.60
    Df Residuals:                      26   BIC:                             81.77
    Df Model:                           4                                         
    Covariance Type:            nonrobust                                         
    ========================================================================================
                               coef    std err          t      P>|t|      [95.0% Conf. Int.]
    ----------------------------------------------------------------------------------------
    Intercept               10.3061      2.282      4.516      0.000         5.615    14.997
    hoursSleptDay            0.1866      0.148      1.261      0.219        -0.118     0.491
    longestSleepHoursDay    -0.8716      0.346     -2.521      0.018        -1.582    -0.161
    meanSleepTimeDay        -0.2837      0.126     -2.248      0.033        -0.543    -0.024
    ageInDays               -0.0023      0.017     -0.141      0.889        -0.036     0.032
    ==============================================================================
    Omnibus:                        5.932   Durbin-Watson:                   0.562
    Prob(Omnibus):                  0.051   Jarque-Bera (JB):                1.934
    Skew:                           0.088   Prob(JB):                        0.380
    Kurtosis:                       1.789   Cond. No.                         887.
    ==============================================================================
    
    Warnings:
    [1] Standard Errors assume that the covariance matrix of the errors is correctly specified.

# Disclaimer

This software is used subject to the following conditions:

THIS SOFTWARE (INCLUDING, WITHOUT LIMITATION, ADVICE OR RECOMMENDATIONS) IS INTENDED SOLELY AS A GENERAL EDUCATIONAL AID AND ARE NEITHER MEDICAL NOR HEALTHCARE ADVICE FOR ANY INDIVIDUAL PROBLEM NOR A SUBSTITUTE FOR MEDICAL OR OTHER PROFESSIONAL ADVICE AND SERVICES FROM A QUALIFIED HEALTHCARE PROVIDER FAMILIAR WITH YOUR UNIQUE FACTS. ALWAYS SEEK THE ADVICE OF YOUR PHYSICIAN OR OTHER QUALIFIED HEALTHCARE PROVIDER REGARDING ANY MEDICAL CONDITION AND BEFORE STARTING ANY NEW TREATMENT. NOTHING CONTAINED IN THE SOFTWARE IS INTENDED TO BE USED FOR MEDICAL DIAGNOSIS OR TREATMENT. THE SOFTWARE IS PROVIDED WITH THE UNDERSTANDING THAT NEITHER THE AUTHORS OF THE SOFTWARE NOR ANY OF ITS CONTRIBUTORS OR USERS ARE ENGAGED IN RENDERING LEGAL, MEDICAL, COUNSELING, OR OTHER PROFESSIONAL SERVICES OR ADVICE. YOUR USE OF THE SOFTWARE IS SUBJECT TO THE ADDITIONAL DISCLAIMERS AND CAVEATS THAT MAY APPEAR THROUGHOUT THE SOFTWARE. THE AUTHORS ASSUME NO RESPONSIBILITY FOR ANY CONSEQUENCE RELATING DIRECTLY OR INDIRECTLY TO ANY ACTION OR INACTION YOU TAKE BASED ON THE SOFTWARE. 

IN NO EVENT WILL THE AUTHORS OR THEIR AFFILIATES BE LIABLE FOR ANY DIRECT, SPECIAL, INDIRECT, INCIDENTAL, CONSEQUENTIAL (INCLUDING AMONG OTHER THINGS LOSS OF REVENUE OR PROFITS), PUNITIVE, OR EXEMPLARY, DAMAGES OF ANY KIND OR SUBJECT TO EQUITABLE OR INJUNCTIVE REMEDIES (WHETHER BASED ON BREACH OF CONTRACT, TORT, NEGLIGENCE, STRICT LIABILITY OR OTHERWISE) ARISING OUT OF USE OF THIS SOFTWARE, OR DELAY OR INABILITY TO USE THE SOFTWARE, OR ANY INFORMATION CONTAINED IN THE SOFTWARE. NOTHING IN THIS LIMITATION OF LIABILITY SHALL EXCLUDE LIABILITIES NOT PERMITTED TO BE EXCLUDED BY APPLICABLE LAW.