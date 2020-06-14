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

[flows (1).json](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/flows_(1).json)

2) Once you pasted the code, click **import**  to create the working flow. 

It should look like this 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.14.08.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.14.08.png)

3) Now, let's configurate each node to connect to the IBM Watson IoT platform. 

Click onto the first node (IBM IoT App In) and click the pen symbol to add a new API key. There, add the Key and Token (authentication Key) that you noted from the previous step. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.15.04.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.15.04.png)

4) Once done, Add the Device ID that you used previously. If the node IBM IoT App Out does not update itself automatically with the data you just imported, do the same exact process for that part.  

5) Now, create a txt file in a directory of your choice. Note down the directory and paste it into the file node. Make sure to inlcude the directorywith the file name and its extension. For example, /Users/user1/IBM SCDF/temp.txt

^) Perfect, now, make sure to deploy the flow. Once deployed, both IBM IoT should show a green box saying "connected". If that is not the case, try to update your API key and deploy again. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.22.08.png](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/Screenshot_2020-06-14_at_17.22.08.png)

## WRITING THE .TXT FILE AS THE SENSOR INPUTS DATA ONTO IBM WATSON IOT

1) Perfect, you are very close to the end of this tutorial. Now, open your IoT Started app on your smartphone device. Insert the credentials again if you logged out before, and press **Activate Sensor**. Once done, a set of three coordinates under **Accelerometer Data** should show. 

2) As you phone is open, make sure to check that the data is being received by the IBM Watson IoT platform, as aforestated. If that is the case, proceed to deploy your flow (if you did not before). Once dployed, the flow should be writing data onto the .txt file by you created and of which you specified the directory before. Wait 5 seconds at least and open it to make sure that this is happening. 

The file should look like this.

[]()

3) For the sake of our early stages of development, we decided to use the same exact format to simulate data from Cloudy Sensors. Hence, our file from sensors would look like this. 

![CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/WhatsApp_Image_2020-06-14_at_05.04.31_(1).jpeg](CONNECTING%20SENSORS%20TO%20IBM%20WATSON%20IOT%20AND%20NODE%20RED%20%20ccb3e6bb345349609007b1d3a3914c28/WhatsApp_Image_2020-06-14_at_05.04.31_(1).jpeg)

Due to time constraints, the file is right now being written only locally on our computer. Going forward, we will make a constant upload of this data back onto the IBM Watson IoT. From there, we would upload it onto the IBM Cloud, in a dedicated database. As this will be done, Cloudsaver will then run through all the data that will be constantly and instantly stored on to the cloud (or in this case the local file that can be included into any database the SCDF is already using, to then have Dloudsaver screen that database instead), and transmitting data indicating possible emergencies or dangerous situation onto our centralised database, accessible for the SCDf fire-fighters to use, as to enhance the ability to detect any possible danger as soon as possible.