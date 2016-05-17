##MEA TE Hackathon 2016<br>

In this hackathon an [IoT set](http://www.robotistan.com/raspberry-pi-2-microsoft-iot-seti) containing a Raspberry PI 2, sensors and standard electronic components is supplied each team. <br>
In our project we worked on a scenario which our device and a camera is located right next to the teller who is talking to a customer in a bank's branch. UWP app running on RPI2 takes  the picture of the customer from time-to-time and processeses. This system is running on each and every teller in all the branches of the bank. As we already know the customer  because teller already opened up the bank's standard banking app when they first welcomed the customer. We pass all those pictures taken to Microsoft Cognitive Services and receive the emotional data from it. 

Please remember that we are getting this data from all the customers sitting in front of a teller. Imagine the scenario that the bank using this "solution" is just released a new banking product (a new credit card, a new mortgage package etc.) and asks their tellers to offer this new product to suitable customers in all their meetings in the bank branch. Bank management would easily see if the customers like the new product/ofer by looking at the customer's emotions date which is centralized in a Power BI dashboard.

Technically, we attached a webcam to RPI2 and developed a Windows UWP app taking pictures of the person in front of the camera continously and sending the picture to Emotions API in MS Cognitive Services (former name ProjectOxford.ai) and took the emotion data in JSON format. The generated JSON date is sent to Azure Event Hubs and passed this stream into Azure Stream Analytics job which is storing the data into a Azure blob Storage as well as feeding the output into a PowerBI sink. We designed a live dashboard in Power BI showing the incoming data as well.

In addition to this we prepared an experiment in Azure Machine Learning to predict when will the right time to offer the product(s) of the bank to the customers.

Technologies used : <br>
 1) Window 10 UWP app running on Windows 10 IoT Core on a Raspberry PI2<br>
 2) Cognitive Services (Emotions API specifically)<br>
 3) Azure Events Hub, Azure Stream Analytics<br>
 4) Power BI <br>
 5) Azure Machine Learning<br>
