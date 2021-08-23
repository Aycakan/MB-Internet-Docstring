# Get that Alumni
Get that Alumni is a Python script for retrieving the details of Doctoral Alumni as a spreadsheet file, from the current version of http://www.mind-and-brain.de/people/doctoral-alumni/

# Getting Started
##  Requirements
This script requires the following third-party libraries:

Requests: https://docs.python-requests.org/en/master/user/install/
Beautiful Soup: https://www.crummy.com/software/BeautifulSoup/#Download
Pandas: https://pandas.pydata.org/docs/getting_started/install.html
NumPy: https://numpy.org/install/
OpenPyXL: https://openpyxl.readthedocs.io/en/stable/

## Recommendations
This script was written with: 
* Anaconda3 
* Spyder 4.1.5
* Python 3.8

## Executing the Program
1) Download the **.zip** file
2) Extract all to your current working directory
3) Open **get_that_alumni.py**
4) Enjoy!

# Usage

## Possible Errors
The script is specifically designed for this website: http://www.mind-and-brain.de/people/doctoral-alumni/

If you change the url from this:
```python
# Site URL
url= "http://www.mind-and-brain.de/people/doctoral-alumni/"
```
To another url:
```python
# Site URL
url= "http://www.google.com/"
```
You will get a NameError:
```python
NameError: Provided keys "['Cohort' 'Description' 'Doctoral project' 'Supervisors']" are not table headers from the website.

Please provide a valid key for the Info_d dictionary 
and make sure that your url is correct.
```

The script scrapes the Alumni Names and Alumni URLs by default. If you wish **not to** scrape the Name or URL information, **see xxx**.



```python
Info_d = {'Doctoral project':[], 'Description':[], 'Supervisors':[],
                   'Cohort': [], 'URLs':[]}
```



```python
```
## Change Default Behavior



# Contact Information
To submit bug reports and suggestions:
aycaaakan@gmail.com


