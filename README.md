# TotallySpies-Cloudsaver_SCDFXIBM                                    

We are group of students from Yale-NUS college, wishing to embark on this Hackathon to broaden our perspectives and play a part in securing Singapore's safety, through the use of advanced technology. We are passionate about and motivated by problem-solving, with a keen interest in the integrtion of technology to provide solutions for everyday problems. 

__We are Totally Spies, and we are here to Occupy!__ -------------- _Antrusha, Kai, Sam, Simone, Vasu_


## Part A - Short Description

__What’s the problem?__
 
With climate change resulting in the urban heat island effect of increased temperatures and higher air pollution, it has contributed to the increased risk of heat-related injuries. This is particularly risky for First Responders who already face physically challenging operations in fire-related emergencies as it increases the strain on their bodies’ heat tolerance. Furthermore, as weather extremities become increasingly common, vegetation fires and electrical fires breakout more frequently, resulting in a higher need for intervention by First Responders.

__How can technology help?__

Real-time monitoring sensors will allow for early detection and enable First Responders to get live updates of the local situation which increases situational awareness of the operation. A centralised data platform will allow for different stakeholders to contribute and obtain detailed information without the hassle of miscommunication, maximising the efficiency of operations to increase the safety and performance of First Responders. 

__The Idea__

To ensure that data is efficiently and accurately collected and translated to maximize the operations of First Responders, we will adopt a central database system called “Cloudsaver”, backed by IBM Cloud storage and IoT technologies. This will enable First Responders to respond more efficiently and safely in the face of an increased risk and frequency of fire-related emergencies. 

## Part B - Pitch Video

(insert link later)


## Part C - Architecture of Proposed Solution

![Architect](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/architecture.png)

## Part D - Hyperlink of Detailed Solution

[Project Cloudsaver](https://docs.google.com/document/d/11WGcwiu8O6XnnvPLRTGHo0gmFj3ji5541ztsV6U9FFA/edit)

## Part E - Project Timeline

![Timeline](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/timeline.png)

## Part F - Getting Started

Section 1 - Cloudie Input
 
 
 Section 2 - Community Input (995 Calls)
 
 
 Section 3 - Compilation and Platform

## Compiling Data in the Central Database Platform

##### Step 1: Ensure all your Datasets are in the same folder
Download the _CDP_and_Sample_Data_ folder from the Repository and check for: 
- Jupyter Notebook File - _Central Database Platform Management.ipynb_
- Two .csv files - _com_myresponderinput.csv_ and _hsm_input1.csv_
- Five .txt files - _sen_1.txt_ to _sen_4.txt_ and _com_record.txt_

##### Step 2: Downloading the require software
1) Download [Anaconda](https://www.anaconda.com/products/individual) (Scroll to the bottom and download according to your respective OS)

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

# You're done with the preperation! Time to test the code as stated on Jupyter Notebook


## Part G - Running the Test

For our Cloudie Sensor Data, due to time and resource constraints we are unable to provide any means to test it, since the sensor data being outputted right now is not exactly relavant to our proposed solution.

As for community input, using the makeshift 995 call receiver, faciliated by microphone detection with Node RED (following the steps laid out in Section 2 of Part F), the user is able to pretend that they are in a state of emergency and speak into their microphones, with the system outputting what they have said along with a probability of their being in a state of fear. 

In testing the entire Centralised Database Platform, following the steps laid out in Section 3 of Part F, the user is able to visualise how data will finally be stratified and presented on the spreadsheet, before it is disseminated to the relavant parties. By tweaking the values in the .csv files provided, the user can emulate changing circumstances and how this might affect overall data representation and presentation.


## Part H - Live Demo

links hopefully

## Part I - Solution Building Tools

- IBM Cloud Functions - Watson Assistant, Watson IoT Platform, 
- Google Spreadsheets
- Jupyter Notebook
- Node-RED
- GitHub


Notwithstanding time and resource constraints, we would like to further develop on our usage of, or by including the following tools
- IBM Cloudant
- IBM Machine Learning Instances




