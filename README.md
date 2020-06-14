# TotallySpies-Cloudsaver_SCDFXIBM
 We are Totally Spies
 
 
 Part 1 of Code (Simone)
 
 
 Part 2 of Code (Sam)
 
 
 
 Part 3 of Code (Vasu)

## Compiling Data in the Central Database Platform

##### Step 1: Ensure all your Datasets are in the same folder
Download the _CDP_and_Sample_Data_ folder from the Repository and check for: 
- Jupyter Notebook File - Central Database Platform Management.ipynb
- Two .csv files - com_myresponderinput.csv and hsm_input1.csv
- Five .txt files - sen_1.txt to sen_4.txt and com_record.txt

##### Step 2: Downloading the require software
1) Download Anaconda from https://www.anaconda.com/products/individual (Scroll to the bottom and download according to your respective OS)

2) Open Anaconda and Run Jupyter Notebook from the Anaconda Interface
![Image of Anaconda Interface](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/anaconda.png)

3) Locate the folder you have downloaded in Step 1 and open the Central Database Platform Management.ipynb

4) Run the first cell to install all necessary libraries we've used, and the second to import the libraries onto Jupyter Notebook
![Cell 1](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/Cell%201.png)

##### We will be utilising Google APIs to link our Jupyter Notebook onto our Final Central Database Platform on Google Spreadsheets, hence the next few steps will go through the steps to incorporate the necessary elements to integrate the Spreadsheet with Jupyter Notebook

5) Go to the [Google Developer Console](https://console.developers.google.com/) and click on __Create Project__

6) Enter a Project Name (and rename the Project ID if you wish to)
![Creating a Project](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/New%20Project.png)

7) You should be taken back to your Developer Console. Refresh the page if your Project isn't there, and click on the __3 dots__ next to it's name, and click on __Permissions__ (If you're already on the Dashboard, ignore this step)
![Manage Resources](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/Manage%20resources.png)

8) At the search bar on top, search for __Google Sheets API__ , click on it, and press __Enable__
![gsheetsapi](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/gsheets%20api.png)

9) Click on __Create Credentials__
![create cred](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/create%20cred.png)

10) Select __Google Sheets API__, __Other UI__ and __Application Data__, and click on __What Credentials Do I Need?__
![cred again](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/cred%20screen.png)

11) *If prompted*, _don't close the current tab_, click on __Set up a consent screen__ , select __External__ and press __Create__. *If not promted*, skip to step __13__

12) *Fill in any application name, scroll to the bottom and click on __Save__. After which, go back to the __previous tab__*
![consent screen](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/consent%20screen.png)

13) Enter a __Service Account Name__, change role to __Service Account User__, select __JSON__ as the key type, and click on __Continue__

![cred screen](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/add%20cred.png)

14) A file should be downloaded. Save it in your _CDP_and_Sample_Data_ folder.

##### We will now be creating a Google Spreadsheet and linking it to the Google API that we just created

15) Open the .json file that was previously downloaded (You can use any text editor to do so), and copy the __client_email__ 
![client email](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/client%20email.png)

16) Create a new Google Spreadsheet, give it a name, and share the spreadsheet with the email you have copied. 
![share](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/share.png)

17) Prepare the following two items
- Name of the .json file that was downloaded (including the .json)
![name of file](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/name%20of%20file.png)
- ID of Google Spreadsheet (after the /d/)
![spreadsheet](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/spreadsheet.png)

18) Go back to the Jupyter Notebook File and continue running from the 3rd Cell Onwards
- Be sure to watch out for the warnings as indicated to avoid your code from breaking!

## You're done with the preperation! Time to test the code as stated on 
## Jupyter Notebook




