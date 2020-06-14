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

https://youtu.be/k6Jhf-dmYvo


## Part C - Architecture of Proposed Solution

![Architect](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/architecture.png)

## Part D - Hyperlink of Detailed Solution

[Project Cloudsaver](https://docs.google.com/document/d/11WGcwiu8O6XnnvPLRTGHo0gmFj3ji5541ztsV6U9FFA/edit)

## Part E - Project Timeline

![Timeline](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/timeline.png)

## Part F - Getting Started

# Section 1 - Cloudie Input
# CONNECTING SENSORS TO IBM WATSON IOT AND NODE RED TO STORE DATA ONTO A TEXT FILE

The first thing you need to do is activate an IBM Watson IoT service onto your IBM Cloud. Once that is done, you can start connecting different sensors onto the service, to receive their data and be able to analyse or export it onto Node-Red, as we will be doing. 

Due to the time constraint of the competition, and to lack of appropriate hardware, this tutotial will implement your smartphone as an accelerometer and store the data the same way a temperature, humidity and smoke level detector would. Also, make sure to have Node-Red running locally on your computer: this passage will be crucial to the smooth installation of come packages later. You can do that [here](https://nodered.org/docs/getting-started/) (select "running locally". 

## **RESISTERING YOUR SMARTPHONE (USED NOW INSTEAD OF SENSORS) ONTO IBM WATSON IOT PLATFORM**

1) Make sure to note down your Organisation ID, that you will need to input later to register your device both on IBM Watson IoT and Node-Red. You can find it on the top right corner, below your login username. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.16.03.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.16.03.png)

2) Click on the device tab on the left menu. Then, click "add device" on the top right corner, 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.17.34.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.17.34.png)

3) Now, add the Device Type of your smartphone. In this case, you can add **Android** for Android devices, or **IOS** for apple devices. Now, in the Device ID, type a code that must be unique to this device. For example, type 112233445566. Click next. 

4) For the scope of connecting your phone, you can leave this page blank as no metadata on the device is needed for your smartphone., If we were to have **Cloudy Sensors**, we would have to proceed and fill this page. Due to time and hardware constraints, we will move on with our phone only. 

5) In the next page, add a value for the authentication token, that you will need to remember later. Click finish. 

## DOWNLOADING THE ANDROID APP "IOT STARTER" TO CONNECT YOUR PHONE TO IBM WATSON IOT

Note that this passage is strictly to be used to connect our phone to IBM Watson IoT, and not any possible Cloudy Sensor. Hence, this is strictly and just for this developmental stage, to show the working of a sensor on the platform. 

1) Download the apk file. To make it more straightforward,d you will be downloading the apk file from the internet. Use [this link](https://github.com/deveops/iot-starter-for-android/releases), and select 'iotstarter-v2.1.0.apk". 

2) make sure you Android device allows the installation of applications from unknown sources. If this is not the case, you can go to **Settings** > **Apps & notifications,** then tap **Advanced**, scroll to **Special app access,** select **install** **unknown apps.** You must also click **Chrome** ( or whichever browser you use) and enable **trust this source.** 

3) Once you download the apk file, click **install**. 

4) Now, the IoT Starte App is installed onto your device. Let's configure it skipping the tutorial.

In **Organisation**, type the Organisation ID you noted earlier. Onto **Device ID**, type the Device ID you noted earlier from IBM Watson IoT. Do the same for the **Auth token** (authentication token). 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.35.06.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.35.06.png)

5) Now, you can activate the sensor, that will send live data onto your IBM Watson IoT service. Check that this is happening by clicking on the arrow next to your device. Data should be appearing under recent events, if your IoT Starter app is running and open on your phone. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.53.04.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.53.04.png)

## INPUTTING THE DATA ONTO A NODE-RED FLOW THAT CONVERTS IT ONTO A FILE

Now, we will connect IM Watson IoT to Node-Red, which will run locally on our computer, to input the data we receive from the sensor in the Node-Red flow that will output a text file that would be then uploaded onto IBM cloud and analysed by **Cloudsaver** and then, would there be an emergency, pas it onto our centralised database available to the SCDF fire forces. 

1) First, generate a new API key to connect your Node-Red to the IBM Watson IoT platform, and the device connected to it (in this case your smartphone) 

2) Click Apps, in the left side menu on IBM Watson IoT. Then, in the top right corner, cclick **Generate API Key**

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.56.39.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.56.39.png)

3) Once clicked, you will have to add a description for the API key (you can leave thihs blank if you wish). Click **next**.

4) Now, click on **Role** and select **Data Processor Application**. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.59.07.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_16.59.07.png)

5) Click **Generate Key**. Make sure to note down the **Authentication Token** now, as this information will not be made available to you later on and you will need it. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.00.14.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.00.14.png)

6) We can now proceed to install the **nodes ibm iot in and ibm iot out** onto Node-Red, which should be running locally (or on the IBM Cloud platform, however this might result in difficulties installing the afforested notes). 

7) To avoid anyndifficulty, you can install the nodes directly from the Node-Red platform. On the top right corner, click the three lines to open a menu. There, click **manage palette**. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.03.13.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.03.13.png)

8) On the palette, go on **Install** and paste this line: node-red-contrib-scx-ibmiotapp. Click on **Install** to install the node. Now you will be able to connect the IBM Watson IoT platform to your Node-Red platform even with it running locally on you computer. 

## CREATING THE FLOW TO OUTPUT A TEXT FILE FROM THE SENSOR INPUTS

1) Onto node red, click **Control + I**  to import the flow needed. Now, paste the code below: 

```json
[{"id":"dc5e627a.00da5","type":"tab","label":"Flow 6","disabled":false,"info":""},{"id":"7d03bab1.476454","type":"ibmiot in","z":"dc5e627a.00da5","authentication":"apiKey","apiKey":"","inputType":"evt","logicalInterface":"","ruleId":"","deviceId":"","applicationId":"","deviceType":"","eventType":"accel","commandType":"","format":"json","name":"IBM IoT App In","service":"registered","allDevices":false,"allApplications":"","allDeviceTypes":true,"allLogicalInterfaces":false,"allEvents":"","allCommands":"","allFormats":"","qos":"0","x":140,"y":260,"wires":[["4d5e4fc8.64016"]]},{"id":"4d5e4fc8.64016","type":"json","z":"dc5e627a.00da5","name":"JSON EDIT","property":"payload","action":"","pretty":false,"x":350,"y":260,"wires":[["265a9366.7b9b6c"]]},{"id":"d9d46dd3.392cc","type":"debug","z":"dc5e627a.00da5","name":"DEBUG","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"true","targetType":"full","x":680,"y":160,"wires":[]},{"id":"265a9366.7b9b6c","type":"file","z":"dc5e627a.00da5","name":"","filename":"","appendNewline":true,"createDir":false,"overwriteFile":"false","encoding":"none","x":510,"y":260,"wires":[["d9d46dd3.392cc","b4b9f696.ba35d8"]]},{"id":"b4b9f696.ba35d8","type":"ibmiot out","z":"dc5e627a.00da5","authentication":"apiKey","apiKey":"","outputType":"cmd","deviceId":"","deviceType":"1.0.6","eventCommandType":"text","format":"json","data":"{\"d\":{\"value\":\"text\"}}","qos":"","name":"IBM IoT App Out","service":"registered","x":690,"y":300,"wires":[]}]
```

The code is also availble in this file, if you wished to directly import it on Node-Red via the **import** command. 

[flows (1).json](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Node-RED%20Flows/Node-REDSensor%20Connection.json)

2) Once you pasted the code, click **import**  to create the working flow. 

It should look like this 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.14.08.png](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/Screenshot_2020-06-14_at_17.14.08.png)

3) Now, let's configurate each node to connect to the IBM Watson IoT platform. 

Click onto the first node (IBM IoT App In) and click the pen symbol to add a new API key. There, add the Key and Token (authentication Key) that you noted from the previous step. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.15.04.png](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/Screenshot_2020-06-14_at_17.15.04.png)

4) Once done, Add the Device ID that you used previously. If the node IBM IoT App Out does not update itself automatically with the data you just imported, do the same exact process for that part.  

5) Now, create a txt file in a directory of your choice. Note down the directory and paste it into the file node. Make sure to inlcude the directorywith the file name and its extension. For example, /Users/user1/IBM SCDF/temp.txt

^) Perfect, now, make sure to deploy the flow. Once deployed, both IBM IoT should show a green box saying "connected". If that is not the case, try to update your API key and deploy again. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.22.08.png](https://github.com/whoisvasu/TotallySpies-Cloudsaver_SCDFXIBM/blob/master/Photos%20for%20Markdown/Screenshot_2020-06-14_at_17.22.08.png)

## WRITING THE .TXT FILE AS THE SENSOR INPUTS DATA ONTO IBM WATSON IOT

1) Perfect, you are very close to the end of this tutorial. Now, open your IoT Started app on your smartphone device. Insert the credentials again if you logged out before, and press **Activate Sensor**. Once done, a set of three coordinates under **Accelerometer Data** should show. 

2) As you phone is open, make sure to check that the data is being received by the IBM Watson IoT platform, as aforestated. If that is the case, proceed to deploy your flow (if you did not before). Once dployed, the flow should be writing data onto the .txt file by you created and of which you specified the directory before. Wait 5 seconds at least and open it to make sure that this is happening. 

The file should look like this.

[]()

3) For the sake of our early stages of development, we decided to use the same exact format to simulate data from Cloudy Sensors. Hence, our file from sensors would look like this. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/WhatsApp_Image_2020-06-14_at_05.04.31_(1).jpeg](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/WhatsApp_Image_2020-06-14_at_05.04.31_(1).jpeg)

Due to time constraints, the file is right now being written only locally on our computer. Going forward, we will make a constant upload of this data back onto the IBM Watson IoT. From there, we would upload it onto the IBM Cloud, in a dedicated database. As this will be done, Cloudsaver will then run through all the data that will be constantly and instantly stored on to the cloud (or in this case the local file that can be included into any database the SCDF is already using, to then have Dloudsaver screen that database instead), and transmitting data indicating possible emergencies or dangerous situation onto our centralised database, accessible for the SCDf fire-fighters to use, as to enhance the ability to detect any possible danger as soon as possible.
 
# Section 2 - Community Input (995 Calls)
 
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

# Section 3 - Compilation and Platform

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

Links in Demo Folder

## Part I - Solution Building Tools

- IBM Cloud Functions - Watson Assistant, Watson IoT Platform, 
- Google Spreadsheets
- Jupyter Notebook
- Node-RED
- GitHub


Notwithstanding time and resource constraints, we would like to further develop on our usage of, or by including the following tools
- IBM Cloudant
- IBM Machine Learning Instances




