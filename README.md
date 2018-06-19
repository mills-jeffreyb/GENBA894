# GENBA894
Capstone Class Poject for Jeff Mills,
Summer 2018,
Kansas State University
***
<br><br>
# Importing Python Packages
   import openpyxl <br>
   import xlrd <br>
   import os <br>
import glob <br>
import requests <br>
from lxml import html <br>
import csv <br>
import pandas as pd <br>

from os import path <br>

import matplotlib.pyplot as plt <br>
%matplotlib inline <br>


*regular expression*  <br>
import re  <br>
*csv*  <br>
import csv  <br>
*Excel-like format*  <br>
import pandas as pd <br>
#data visualization <br>
import matplotlib.pyplot as plt <br>
% matplotlib inline <br>

import numpy as np  <br>

import statsmodels.api as sm  <br>

import statsmodels.formula.api as smf
<BR> <br> <br>
# Opening the Correct Directory
os.chdir('C:\\Users\\millsj.ADMIN\\Desktop\\GENBA 894\\2018_DataChallenges_Teradata\\Donations\\')
 <br> <br>  <br>
# Importing Data
*filenames* <br>
excel_names = ["2013 Bike Donations.xlsx", "2014 Bike Donations.xlsx", "2015 Bike Donations.xlsx","2016 Bike Donations.xlsx","2017 Bike Donations.xlsx"] <br>

*read them in* <br>
excels = [pd.ExcelFile(name) for name in excel_names] <br>

*turn them into dataframes* <br>
frames = [x.parse(x.sheet_names[0], header=1,index_col=None) for x in excels] <br>

*delete the first row for all frames except the first <br>
i.e. remove the header row -- assumes it's the first* <br>
frames[1:] = [df[1:] for df in frames[1:]] <br>

*concatenate them.* <br>
combined = pd.concat(frames) <br>

*Check headers* <br>
combined.head(3)   <br> <br><br> <br>



# Project: 2018 Data Challenges Sponsored by Teradata University Network
<b>Background Information</b><br> 
The National Multiple Sclerosis Society (NMSS) seeks to help people with multiple sclerosis and their families. Help is provided by raising funds to support research, advocate, educate and supply support services. The NMSS’ flagship fundraising event is Bike MS, which is the largest charity bike event in the United states. Previously, Bike MS has solicited 70,000 participants and raised over $68 million through more than 75 rides.<br>


A typical Bike MS event shares the following characteristics:
•	One or two-day event,
•	Located within reasonable driving distance from metropolitan areas,
•	Offer participants first aid, mechanics, rest areas, and shuttles, 
•	Community “village” with vendors, dining, beer gardens, camping (in some locations), team tents, and entertainment. 
•	Riders chose among routes ranging from 10 to 100 miles per day.


Teams are responsible for 87% of fundraising and Bike MS participant demographics of mostly male, middle age, higher income earners align well with corporate events. Previous research has shown that corporate teams of 10 or more cyclists are seven times more valuable than any other kind of team. For this reason, companies with a large professional employee base, especially those with a corporate culture of health and wellness, are vital recruiting targets. 


## Business Problem
Currently, Bike MS has struggled to maintain fundraising and participation growth due to overcrowding in the charity cycling marketplace. This increased level of competition has caused Bike MS participation and revenue to steadily decline since peaking in 2012. Despite retention rates over 50%, solicitation of new cyclists cannot keep pace with the number of cyclists no longer participating in Bike MS events. The NMSS believes it must increase new cyclist participation to find future success. Since 10+ members teams raise three times more money than smaller teams and over 41% of the 1,561 teams with 10+ members in 2017 were corporate teams, NMSS believes it must also recruit new 10 or more member corporate teams to maximize fundraising efforts. 


NMSS goals for 2018 Bike MS:

  * Increase from 74,000 riders to 80,572 riders,
  * Increase from 6,150 teams to 6,489 teams,
  * Recruit 40,000 new riders,
  * Increase number of corporate teams with 10 or more riders, 
  * Successfully utilize digital marketing efforts to impact fundraising goals.

# Questions to be Answered



## FIRST PRIORITY: CORPORATE ACQUISITION
  * What are the greatest growth opportunities for new corporate teams?
  * Can we apply those opportunities to specific rides/markets, especially our biggest events?
  * What industries have had the strongest involvement in Bike MS in the last five years?
  * What occupations were responsible for most of our fundraising?
  * Can we tie together these industries and occupations to identify gaps/opportunities?
  * What is the common denominator for our top performing corporate teams? (Is it industry, culture, executive involvement, connection to MS, other?)
  * Can we quantify the effect competing events are having in our top markets? 
  
  
Top competitors:
   1. Best Buddies
     * HYANNIS PORT June 2, 2018 Boston to Hyannis Port, MA
     * HEARST CASTLE September 8, 2018 San Simeon, CA
     * MIAMI November 16, 2018 Miami, FL
   2. Peddle the Cause
     * Louis
     * San Diego
   3. Pelatonia – OH
   4. PanMass Challenge - Boston
   5. ADA – Tour de Cure
   6. Jude Children’s Research Hospital
   7. JDRF Ride to Cure Diabetes
   8. Cycle for Life - Cystic Fibrosis Foundation
   9. Ride to Recovery
   10. Virtual Cycling
   11. Athletic Club Stationary Cycling Relays
   12. American Cancer Society
   13. Leukemia and Lymphoma Society – Team in Training
   <br><br>
   
## SECOND PRIORITY: DIGITAL/SOCIAL ACQUISITION
  * What are the greatest opportunities for digital marketing investments? Where have we seen the greatest ROI?
  * Once someone is registered, what tactics and behaviors drive fundraising, and at what times leading up to the event?
  * What behavioral data do you see about usage of our fundraising tools and how it may or may not relate to performance of top fundraisers?
  * Despite increasing our digital advertising spend, acquisition continues to trend downward overall. Why? Is it an issue of needing more traffic, better targeting, or a conversion rate issue that needs to be addressed through the registration process? What can we do to reverse the trend?
   <br><br>
## FINALLY:
  * As you studied this data, is there something else that came up as an insight into our operations that the questions above do not capture? 
   
