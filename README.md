# Get that Alumni
Get that Alumni is a Python script for retrieving the details of Doctoral Alumni as a spreadsheet file from the current version of http://www.mind-and-brain.de/people/doctoral-alumni/

# Getting Started
##  Requirements
This script requires the following third-party libraries:

* Requests: https://docs.python-requests.org/en/master/user/install/
* Beautiful Soup: https://www.crummy.com/software/BeautifulSoup/#Download
* Pandas: https://pandas.pydata.org/docs/getting_started/install.html
* NumPy: https://numpy.org/install/
* OpenPyXL: https://openpyxl.readthedocs.io/en/stable/

## Recommendations
This script was written with: 
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
You can retreive the desired information by targeting the particular table headers from the website source code.
To achieve this you can:

**A) Inspect the source code:** 
1) Check the website source code for table headers
2) Add the table headers to the **Info_d** dictionary as **keys**
      ```python
      # Scrape information according to the table headers:
      # !Dict keys should be named after the table headers in the url source code!
      Info_d = {'Doctoral project':[], 'Description':[], 'Supervisors':[],
                         'Cohort': [], 'URLs':[]}
      ```
3) Change the **file_name** to the desired spreadsheet name:
        ```python
        # Determine the name of the output file
        file_name = 'Doctoral_Alumni_Info.xlsx'
        ```
4) Run the script
5) The spreadsheet will be created in your working directory as the output. This message will pop up in the console if it was a success:
  ```Console
  In [20]: runfile('[PATH]/get_that_alumni.py', wdir='[PATH]')
  DataFrame is written to Excel File successfully. 
  Formating is done.
  File Name: Doctoral_Alumni_Info.xlsx
  ```
**B) Inspect the table_headers list:**
  1) Run **get_that_alumni.py** and observe the default behavior
  2) Print **table_headers** list to the console to see the list of table headers from the website
  table_headers
  ```Console
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
  3) Add the desired table headers to the **Info_d** dictionary as **keys**
  ```python
  # Scrape information according to the table headers:
  # !Dict keys should be named after the table headers in the url source code!
  Info_d = {'Doctoral project':[], 'Description':[], 'Supervisors':[],
                     'Cohort': [], 'URLs':[]}
  ```
  4) Optional: Change the **file_name** to the desired spreadsheet name. Default file_name is 'Doctoral_Alumni_Info.xlsx'
  ```python
  # Determine the name of the output file
  file_name = 'Doctoral_Alumni_Info.xlsx'
  ```
  5) Run the script
  6) The spreadsheet will be created in your working directory as the output. This message will pop up in the console if it was a success:
    ```Console
  In [22]: runfile('[PATH]/get_that_alumni.py', wdir='[PATH]')
  DataFrame is written to Excel File successfully. 
  Formating is done.
  File Name: Doctoral_Alumni_Info.xlsx
  ```
  7) The spreadsheet:
  
## Possible Errors
# Different Websites as url:
The script is specifically designed for this website: http://www.mind-and-brain.de/people/doctoral-alumni/. 
For this reason, changing the url could result in confusing outputs or errors.

Table headers are unique for different urls. Changing the url could result in a NameError:
```console
NameError: Provided keys "[...]" are not table headers from the website.

Please provide a valid key for the Info_d dictionary 
and make sure that your url is correct.
```
# Keys that are not table headers from the url:



```python
```
## Change Default Behavior
The script scrapes the Alumni Names and Alumni URLs by default. If you wish **not to** scrape the Name or URL information, **see xxx**.



# Contact Information
To submit bug reports and suggestions:
aycaaakan@gmail.com


