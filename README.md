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
# Excel-like format
import pandas as pd <br>
#data visualization <br>
import matplotlib.pyplot as plt <br>
% matplotlib inline <br>

import numpy as np  <br>

import statsmodels.api as sm  <br>

import statsmodels.formula.api as smf
<BR> <br> <br>
# Opening the correct directory
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
combined.head(3)   <br> <br>
  

