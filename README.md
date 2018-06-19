# GENBA894
Capstone Class Poject for Jeff Mills,
Summer 2018,
Kansas State University
***
<br><br>
# Importing Python Packages
import openpyxl 
import xlrd 
import os
import glob
import requests
from lxml import html
import csv
import pandas as pd

from os import path

import matplotlib.pyplot as plt
%matplotlib inline


#regular expression
import re
#csv
import csv
# Excel-like format
import pandas as pd
#data visualization
import matplotlib.pyplot as plt
% matplotlib inline

import numpy as np

import statsmodels.api as sm

import statsmodels.formula.api as smf
<BR>
# Opening the correct directory
os.chdir('C:\\Users\\millsj.ADMIN\\Desktop\\GENBA 894\\2018_DataChallenges_Teradata\\Donations\\')
  <br>
# Importing Data
# filenames
excel_names = ["2013 Bike Donations.xlsx", "2014 Bike Donations.xlsx", "2015 Bike Donations.xlsx","2016 Bike Donations.xlsx","2017 Bike Donations.xlsx"]

# read them in
excels = [pd.ExcelFile(name) for name in excel_names]

# turn them into dataframes
frames = [x.parse(x.sheet_names[0], header=1,index_col=None) for x in excels]

# delete the first row for all frames except the first
# i.e. remove the header row -- assumes it's the first
frames_new=[df[1:] for df in frames]

# concatenate them..
combined = pd.concat(frames_new)

# Check headers
combined.head(3)  
  

