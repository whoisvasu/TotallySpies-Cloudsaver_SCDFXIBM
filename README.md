 ![Logo](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/clouyas.png)

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
 
 
## Section 2 - Community Input (995 Calls)
 
 # Real time Speech-to-Text log

This section explores how to create a program that automatically logs and records conversations between dispatchers and distressed callers through **Node-RED**. The program also recognizes and tabulates caller distress levels with the **IBM tone analyzer**. This allows us to then automatically filter and organize caller information in a highly efficient manner, saving both dispatchers and firefighters ample time. All in all, the program should be inputted with speech data presented in a WAV format, and should output two text files logging the call and assigning an emotion stress rating respectively. In order to run the program, there are packages and software that require installation.

# Learning Objectives:

In this section, you will acquire the following;

- Locally installing Node-RED and adjacent IBM packages.
- Importing the real time STT logger.
- Familiarity with the IBM tone analyzer.

# Step 1: Prerequisites

Firstly, ensure that you have registered for an **IBM Cloud** account, which will be necessary to access certain IBM provided node services. If you have not yet done so, it can be done [here](https://cloud.ibm.com/registration).

This program is created on and runs through **Node-RED.** As such, users need to locally install the Node-RED application on their devices. Users who do not have Node-RED already installed on their devices can do so [here](http://nodered.org/docs/getting-started/). After installing Node-RED, you can write the following command on your device's command prompt. 

```
C:\User> node-red
```

This will allow you to run Node-RED on a web browser by typing "localhost:1880" in the search bar.

After having installed Node-RED, we install the necessary dependencies. First install the **IBM Watson nodes** by typing the following command into your command prompt.

```
npm install node-red-node-ui-microphone node-red-dashboard node-red-node-watson node-red-contrib-play-audio
```

Then install the following package to have access to the microphone that emulates the recording of dispatcher civilian calls. This should complete the provision of required packages for the program.

```
npm install node-red-contrib-browser-utils
```

# Step 2: Importing the Real Time Speech-to-Text logger program

[import_flow_STT.txt](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/import_flow_STT.txt)

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/nodered.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/nodered.png)

After importing the code, the Node-RED diagram should appear on the application.

# Step 3: Creating IBM Service Instances

Having uploaded the flow onto Node-RED does not entail a completely functional flow just yet. There also needs to be a link created between the IBM provided nodes and their service providers, which can be done with API keys from **IBM Cloud.** In particular, there are two necessary services that are being used from the vast list of IBM services, these are the **IBM Speech to Text** service, and the **IBM tone analyzer** service.  

You can find both services by clicking on the catalog button of the IBM Cloud home page, and typing the respective service names into the catalog search bar.

### IBM Watson Speech to Text Service:

Create a Speech to Text service instance by following this link [here](https://cloud.ibm.com/catalog/services/speech-to-text). Select a region to base your service, as well as a lite plan, then click the create button found on the bottom right of the screen.

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled.png)

Once the Watson Speech to Text service has been created, find and click the service credentials button, found on the left handle-bar. Then, click the "view credentials" twisty, and copy the API key found in the code file.

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%201.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%201.png)

### IBM Watson Tone Analyzer Service:

Similarly, create a Tone Analyzer service instance by following this link [here](https://cloud.ibm.com/catalog/services/tone-analyzer). Select a region to base your service and a lite plan, then click the create button found on the bottom right of the screen. 

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%202.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%202.png)

Once the Watson Tone Analyzer service has been created, find and click the service credentials button, found on the left handle-bar. Then, click the "view credentials" twisty, and copy the API key found in the code file.

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%203.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%203.png)

# Step 4: Enabling Watson Nodes

With the API keys, enable the Watson **Speech to Text** node by double clicking on it, then inserting the Speech to Text API key recently acquired, and then clicking "Done". Ensure that the Speech to Text node language is set to English, and that if it is not, change it by clicking on the down arrow in the language tab and finding "US English".

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%204.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%204.png)

Similarly, enable the Watson **Tone Analyzer** node by double clicking on it, then inserting the Speech to Text API key recently acquired, and then clicking "Done".

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%205.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%205.png)

# Step 5: Re-Directing the Output Files

In order to successfully receive the necessary output files, make sure you redirect the file locations of the two files being created by the Node-RED flow. In order to do so, double-click on the two **file nodes**, highlighted in maroon, and then adjust the directory destination by changing the word "user" to your device username. This ensures that the necessary files do indeed get outputted to your desktop.

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%206.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%206.png)

# Step 6: Deployment

At this point, be sure to click the **"Deploy"** button found on the top right of the screen. Then, enable the dashboard by clicking on the "Menu" handle-bar, clicking "view", and then "dashboard".

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%207.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%207.png)

This should conclude the installation of the Real Time Speech-to-Text logger program.

# Using the Program

At this point, the program should be fully installed and ready to use. We test the program's functionality by clicking the button extension on the right of the Microphone node, which should automatically be configured to your device microphone. 

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%208.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%208.png)

Proceed to emulate a dispatcher civilian call by saying anything into the microphone. Once the recording is complete, press the microphone button again to conclude the Call. Be sure to press the "debug"  button in the dashboard, to see the program's progress. 

Once the program has finished running, there should be two files on your device's desktop, aptly titled "record.txt" and "emotion_record.txt". If this is the first time the program is being run on a given device, the files will automatically be added to your desktop. If this is not the first time the program is being run, the data will merely be updated to the existent files. The first file "record.txt" records a log of the conversation between the dispatcher and the caller in a CSV format, whereby each conversation is one column. The second file "emotion_record.txt" records the log of the conversation between the dispatcher and the caller in a dictionary format. It also records a score out of 1 that describes the poignancy of the most prevalent emotion detected in the call, followed by what tone analyzer believes is the most present emotion. The higher the score out of one, the more distressed a caller likely is (as the main emotion conveyed will almost always be fear).

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%209.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%209.png)

![Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%2010.png](Real%20time%20Speech%20to%20Text%20log%20d1b95d1cf1c9446ebc89a4f59e627f7a/Untitled%2010.png)

# Application to SCDF

When applying this program in the SCDF, there will be a couple of modifications to consider. Primarily, there will be a system connecting the dispatcher phone to this application, whereby the second the call is picked up, the program is activated and is recording data, and the second the call is ended, the program ends and begins synthesizing the data. Furthermore, the data files produced by the program would directly link to an SCDF cloud database, which would allow automated tabulation of the data through the synthesis and tabulation program we have created. This could be done through a system similar to the IBM IoT system, that allows you to connect devices to the cloud. Both of these fixes are demonstrably and easily completable, given the proper infrastructure (cloud system and dispatcher phone connection).
 
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




