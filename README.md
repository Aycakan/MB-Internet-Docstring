# Get that Alumni
Get that Alumni is a Python script for retrieving the details of the Doctoral Alumni of Berlin School of Mind and Brain, as a spreadsheet file from the current version of the website: http://www.mind-and-brain.de/people/doctoral-alumni/

# Getting Started
##  Requirements
This script requires the following third-party libraries:

* Requests: https://docs.python-requests.org/en/master/user/install/
* Beautiful Soup: https://www.crummy.com/software/BeautifulSoup/#Download
* Pandas: https://pandas.pydata.org/docs/getting_started/install.html
* NumPy: https://numpy.org/install/
* OpenPyXL: https://openpyxl.readthedocs.io/en/stable/

## Recommendations
The script was written with: 
* Anaconda3 
* Spyder 4.1.5
* Python 3.8

These programs could be used for optimal performance.

## Executing the Program
1) Download the **.zip** file
2) Extract all the documents to your **current working directory**
3) Open **get_that_alumni.py**
4) Enjoy!

# Usage
You can retrieve the desired information by targeting the particular table headers from the website's source code.
To achieve this you can:

**A) Inspect the source code:** 
1) Check the website source code for **table headers**
2) Add the table headers to the **Info_d** dictionary as **keys**. These keys are used to fetch the table data and make up the spreadsheet's table headers. 
      ```python
      # !Dict keys should be named after the table headers in the URL source code!
      Info_d = {'Doctoral project':[], 'Description':[], 'Supervisors':[],
                         'Cohort': [], 'URLs':[]}
      ```
3) Optional: Change the **file_name** to the desired spreadsheet name. Default file_name is "Doctoral_Alumni_Info.xlsx"

  ```python
  # Determine the name of the output file
  file_name = 'Doctoral_Alumni_Info.xlsx'
  ```
4) Run the script
5) The spreadsheet will be created **in your working directory** as the output. 
    This message will pop up in the console if the script worked successfully:
  ```Console
  In [20]: runfile('[PATH]/get_that_alumni.py', wdir='[PATH]')
  DataFrame is written to Excel File successfully. 
  Formating is done.
  File Name: Doctoral_Alumni_Info.xlsx
  ```
**B) Inspect the table_headers list:**
  1) Run **get_that_alumni.py** and observe the default behavior
  2) Print **table_headers** list to the console to see the list of table headers from the website
  ```Console
table_headers
Out[21]: 
['Doctoral project',
 'Description',
 'Funding',
 'Supervisors',
 'M&B topics',
 'Degrees obtained',
 'Institute',
 'Cohort',
 'Status',
 'E-mail',
 'Title',
 'Researchgate',
 'Academia.edu',
 'Phone',
 'Homepage',
 'Current Position']
 ```
  3) Choose the desired table headers, and add them to the **Info_d** dictionary as **keys**
  ```python
  # !Dict keys should be named after the table headers in the URL source code!
  Info_d = {'Doctoral project':[], 'Description':[], 'Supervisors':[],
                     'Cohort': [], 'URLs':[]}
  ```
  4) Optional: Change the **file_name** to the desired spreadsheet name. Default file_name is 'Doctoral_Alumni_Info.xlsx'
  ```python
  # Determine the name of the output file
  file_name = 'Doctoral_Alumni_Info.xlsx'
  ```
  5) Run the script
  6) The spreadsheet will be created in your working directory as the output. 
      This message will pop up in the console if it was a success:
  ```Console
  In [20]: runfile('[PATH]/get_that_alumni.py', wdir='[PATH]')
  DataFrame is written to Excel File successfully. 
  Formating is done.
  File Name: Doctoral_Alumni_Info.xlsx
  ```

# Possible Errors

**1) Different Websites as the URL:**

The script is specifically designed for this website: http://www.mind-and-brain.de/people/doctoral-alumni/. 
For this reason, changing the URL could result in confusing outputs or errors.

Changing the URL could raise a NameError as table headers are unique for different websites:

```console
NameError: Provided keys "[...]" are not table headers from the website.

Please provide a valid key for the Info_d dictionary 
and make sure that your URL is correct.
```
**2) Keys that are not table headers from the URL:**

The script was designed to use the keys from Info_d dictionary to search through the table headers and fetch the table data through this process.
Keys from this dictionary are also used as the table headers for the output spreadsheet.
If you wish to code for scraping another information that is not under the alumni tables or does not have the applicable source code structure, please include the name of this variable to both **Info_d** dictionary and **custom_keys** list:

  ```python
# Scrape information according to the table headers:
# !Dict keys should be named after the table headers in the URL source code!
Info_d = {'Doctoral project':[], 'Description':[], 'Supervisors':[],
                   'Cohort': [], 'Alumni URLs':[]}

# Custom keys that are not headers from the source code (e.g. Alumni URLs) 
# should be added to both Info_d and custom_keys list to avoid NameError
custom_keys = ['Alumni URLs']
  ```
To avoid raising this NameError:

```console
NameError: Provided keys "[...]" are not table headers from the website.

Please provide a valid key for the Info_d dictionary 
and make sure that your URL is correct.
```

## Change Default Behavior
The script scrapes the Alumni Names and Alumni URLs by default as they do not have the same source code structure as the other table elements of the website. If you wish **not to** scrape the Name or URL information, you could follow these steps:

**To Not Scrape Alumni Names**:
Empty the info_dict and make the following for loop a comment:
  ```python
# Scrape the alumni names and surnames
info_dict={}

# for name in soup.findAll('div',attrs={'class':'col col-1'}):
#     for href in name.findAll('a',href = '#'):
#         info_dict['Surname, Name'].append(href.text)
        
  ```

**To Not Scrape Alumni URLs**
Remove 'Alumni URLs' from Info_d dictionary and custom_keys list:
```python
Info_d = {'Doctoral project':[], 'Description':[], 'Supervisors':[],
                   'Cohort': []}

# Custom keys that are not headers from the source code (e.g. Alumni URLs) 
# should be added to both Info_d and custom_keys list to avoid NameError
custom_keys = []
        
  ```
And make this for loop a comment:
```python
    # Scrape for Alumni 
    # for line in alumna_info.findAll('a'):
    #         link = line.get('href')
    #         if link.startswith('http'):
    #             links.append(link)
    # string = string.join(links)
    # if len(string) == 0:
    #     Info_d['Alumni URLs'].append('no info')
    # else:
    #     Info_d['Alumni URLs'].append(string)
    # links = []
    # string = '\r\n, '
    # Scrape for the data that has the same table headers as the given keys      
  ```


## Contact Information
To submit bug reports and suggestions:
aycaaakan@gmail.com


