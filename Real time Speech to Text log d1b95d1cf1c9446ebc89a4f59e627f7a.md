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