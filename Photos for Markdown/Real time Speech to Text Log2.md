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

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/943fb0d6-3498-448b-b602-76807585d620/nodered.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094406Z&X-Amz-Expires=86400&X-Amz-Signature=2efc8b9aea87d490c7b9bd970906b2990d515e5883dfa1cbb01e779bc72b11bc&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22nodered.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/943fb0d6-3498-448b-b602-76807585d620/nodered.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094406Z&X-Amz-Expires=86400&X-Amz-Signature=2efc8b9aea87d490c7b9bd970906b2990d515e5883dfa1cbb01e779bc72b11bc&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22nodered.png%22)

After importing the code, the Node-RED diagram should appear on the application.

# Step 3: Creating IBM Service Instances

Having uploaded the flow onto Node-RED does not entail a completely functional flow just yet. There also needs to be a link created between the IBM provided nodes and their service providers, which can be done with API keys from **IBM Cloud.** In particular, there are two necessary services that are being used from the vast list of IBM services, these are the **IBM Speech to Text** service, and the **IBM tone analyzer** service.  

You can find both services by clicking on the catalog button of the IBM Cloud home page, and typing the respective service names into the catalog search bar.

### IBM Watson Speech to Text Service:

Create a Speech to Text service instance by following this link [here](https://cloud.ibm.com/catalog/services/speech-to-text). Select a region to base your service, as well as a lite plan, then click the create button found on the bottom right of the screen.

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/08d7adf3-2ca5-4bf7-9a0c-3bc43e174e31/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094517Z&X-Amz-Expires=86400&X-Amz-Signature=331ed6f5d138743fce42fa7b609eb40b922e29d6d33e31b9e167cc9da2eab2b9&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/08d7adf3-2ca5-4bf7-9a0c-3bc43e174e31/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094517Z&X-Amz-Expires=86400&X-Amz-Signature=331ed6f5d138743fce42fa7b609eb40b922e29d6d33e31b9e167cc9da2eab2b9&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

Once the Watson Speech to Text service has been created, find and click the service credentials button, found on the left handle-bar. Then, click the "view credentials" twisty, and copy the API key found in the code file.

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/2619a391-cd80-4a18-a907-8c2d40b00225/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094543Z&X-Amz-Expires=86400&X-Amz-Signature=85989b099cba973eff84bc640877c78e670036552a6a495a0208a2583604a65a&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/2619a391-cd80-4a18-a907-8c2d40b00225/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094543Z&X-Amz-Expires=86400&X-Amz-Signature=85989b099cba973eff84bc640877c78e670036552a6a495a0208a2583604a65a&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

### IBM Watson Tone Analyzer Service:

Similarly, create a Tone Analyzer service instance by following this link [here](https://cloud.ibm.com/catalog/services/tone-analyzer). Select a region to base your service and a lite plan, then click the create button found on the bottom right of the screen. 

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/fc3a7520-9998-4118-a9ba-cf8ccf92e9a4/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094620Z&X-Amz-Expires=86400&X-Amz-Signature=8ef872f29474d0467a43aaa3dae7581179ad1ee1cb354c117e7081b196311598&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/fc3a7520-9998-4118-a9ba-cf8ccf92e9a4/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094620Z&X-Amz-Expires=86400&X-Amz-Signature=8ef872f29474d0467a43aaa3dae7581179ad1ee1cb354c117e7081b196311598&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

Once the Watson Tone Analyzer service has been created, find and click the service credentials button, found on the left handle-bar. Then, click the "view credentials" twisty, and copy the API key found in the code file.

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/e595abb6-d642-4fa6-b626-f8a53484bb42/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094638Z&X-Amz-Expires=86400&X-Amz-Signature=a67c7061ef21a9975b85c763e9ed46164e3b048d0113e5594d19863ca9a6ebea&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/e595abb6-d642-4fa6-b626-f8a53484bb42/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094638Z&X-Amz-Expires=86400&X-Amz-Signature=a67c7061ef21a9975b85c763e9ed46164e3b048d0113e5594d19863ca9a6ebea&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

# Step 4: Enabling Watson Nodes

With the API keys, enable the Watson **Speech to Text** node by double clicking on it, then inserting the Speech to Text API key recently acquired, and then clicking "Done". Ensure that the Speech to Text node language is set to English, and that if it is not, change it by clicking on the down arrow in the language tab and finding "US English".

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/3ee38ee6-24bb-47cb-ab65-853843769078/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094700Z&X-Amz-Expires=86400&X-Amz-Signature=9d4accf54c937457f22064525028606ebdd9f78a89241c9d026971d09fd04c3d&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/3ee38ee6-24bb-47cb-ab65-853843769078/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094700Z&X-Amz-Expires=86400&X-Amz-Signature=9d4accf54c937457f22064525028606ebdd9f78a89241c9d026971d09fd04c3d&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

Similarly, enable the Watson **Tone Analyzer** node by double clicking on it, then inserting the Speech to Text API key recently acquired, and then clicking "Done".

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/8c6e3ea1-678b-4754-abd5-c51300dfec21/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094715Z&X-Amz-Expires=86400&X-Amz-Signature=e4dbd31e7516248e5ab67edf2e44bef3ed31428b23c3b575b6282f615efa73d1&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/8c6e3ea1-678b-4754-abd5-c51300dfec21/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094715Z&X-Amz-Expires=86400&X-Amz-Signature=e4dbd31e7516248e5ab67edf2e44bef3ed31428b23c3b575b6282f615efa73d1&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

# Step 5: Re-Directing the Output Files

In order to successfully receive the necessary output files, make sure you redirect the file locations of the two files being created by the Node-RED flow. In order to do so, double-click on the two **file nodes**, highlighted in maroon, and then adjust the directory destination by changing the word "user" to your device username. This ensures that the necessary files do indeed get outputted to your desktop.

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/905892f4-4213-4055-bd83-24f80de5845d/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094729Z&X-Amz-Expires=86400&X-Amz-Signature=93a6e6b44fea9a5b6bfeb394f70c29bf6133187117ca0232e8132575c1a112f6&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/905892f4-4213-4055-bd83-24f80de5845d/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094729Z&X-Amz-Expires=86400&X-Amz-Signature=93a6e6b44fea9a5b6bfeb394f70c29bf6133187117ca0232e8132575c1a112f6&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

# Step 6: Deployment

At this point, be sure to click the **"Deploy"** button found on the top right of the screen. Then, enable the dashboard by clicking on the "Menu" handle-bar, clicking "view", and then "dashboard".

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/53c976cb-2b46-4f43-a451-e5d0b43934e4/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094750Z&X-Amz-Expires=86400&X-Amz-Signature=f234a1fa91b3e781911e749ac3c88a01b7213906742c0e316f94c99d200a1583&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/53c976cb-2b46-4f43-a451-e5d0b43934e4/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094750Z&X-Amz-Expires=86400&X-Amz-Signature=f234a1fa91b3e781911e749ac3c88a01b7213906742c0e316f94c99d200a1583&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

This should conclude the installation of the Real Time Speech-to-Text logger program.

# Using the Program

At this point, the program should be fully installed and ready to use. We test the program's functionality by clicking the button extension on the right of the Microphone node, which should automatically be configured to your device microphone. 

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/5b340db4-3928-4eb1-b7a4-91a49b26657a/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094806Z&X-Amz-Expires=86400&X-Amz-Signature=3743a7e53966b141a260880e815b60195bc564088e26246ee388017c5c432f17&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/5b340db4-3928-4eb1-b7a4-91a49b26657a/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094806Z&X-Amz-Expires=86400&X-Amz-Signature=3743a7e53966b141a260880e815b60195bc564088e26246ee388017c5c432f17&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

Proceed to emulate a dispatcher civilian call by saying anything into the microphone. Once the recording is complete, press the microphone button again to conclude the Call. Be sure to press the "debug"  button in the dashboard, to see the program's progress. 

Once the program has finished running, there should be two files on your device's desktop, aptly titled "record.txt" and "emotion_record.txt". If this is the first time the program is being run on a given device, the files will automatically be added to your desktop. If this is not the first time the program is being run, the data will merely be updated to the existent files. The first file "record.txt" records a log of the conversation between the dispatcher and the caller in a CSV format, whereby each conversation is one column. The second file "emotion_record.txt" records the log of the conversation between the dispatcher and the caller in a dictionary format. It also records a score out of 1 that describes the poignancy of the most prevalent emotion detected in the call, followed by what tone analyzer believes is the most present emotion. The higher the score out of one, the more distressed a caller likely is (as the main emotion conveyed will almost always be fear).

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/32065f6f-9fc4-4aae-8cd7-41121c24aec5/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094822Z&X-Amz-Expires=86400&X-Amz-Signature=eaf2cdea96b03ea495573f3189b6e1d72ab2909d82a85c52759c0e1bac500434&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/32065f6f-9fc4-4aae-8cd7-41121c24aec5/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094822Z&X-Amz-Expires=86400&X-Amz-Signature=eaf2cdea96b03ea495573f3189b6e1d72ab2909d82a85c52759c0e1bac500434&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

![https://s3.us-west-2.amazonaws.com/secure.notion-static.com/90691039-ff3d-402c-baa8-6777a72ad739/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094836Z&X-Amz-Expires=86400&X-Amz-Signature=c1a39cfc58fdeca074a07af99afc44bdd4523122ef17b0d766abd589eb8a3f0a&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/90691039-ff3d-402c-baa8-6777a72ad739/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200614%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200614T094836Z&X-Amz-Expires=86400&X-Amz-Signature=c1a39cfc58fdeca074a07af99afc44bdd4523122ef17b0d766abd589eb8a3f0a&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

# Application to SCDF

When applying this program in the SCDF, there will be a couple of modifications to consider. Primarily, there will be a system connecting the dispatcher phone to this application, whereby the second the call is picked up, the program is activated and is recording data, and the second the call is ended, the program ends and begins synthesizing the data. Furthermore, the data files produced by the program would directly link to an SCDF cloud database, which would allow automated tabulation of the data through the synthesis and tabulation program we have created. This could be done through a system similar to the IBM IoT system, that allows you to connect devices to the cloud. Both of these fixes are demonstrably and easily completable, given the proper infrastructure (cloud system and dispatcher phone connection).
