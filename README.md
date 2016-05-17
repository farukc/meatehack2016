# meatehack2016
MEA TE Hackathon 2016

In this hackathon an [IoT set](http://www.robotistan.com/raspberry-pi-2-microsoft-iot-seti) containing a Raspberry PI 2, sensors and standard Electronic components is supplied to teams. <br>
In our project we worked on a scenario which our device and a camera is located right next to the teller who is talking to a customer in a bank's branch. UWP app running on RPI2 takes  the picture of the customer from time-to-time and logs from all the tellers in all the branches of the bank. Please note that we already know the customer as because teller already opened up their bank's standard banking app when they first met with the customer. We log all the emotional data from all the customers when a teller offered a new product to the customer. It could be a new product or a interest rate for a new credit loan ustomer asked from the teller. 
Imagine the scenario that the bank using this "solution" is released a new banking product (a new credit card, a new mortgage package etc.) and tellers started offering this new product to the customers in their meetings in the bank branch. Bank management (could be marketing dept) would see the outcome of the offer by looking at the customer's emotions which is centralized.

In our team we attached a webcam to RPI2 and wrote an app taking pictures of the person in front of the camera continously and sending the picture to Emotions API in MS Cognitive Services (former name ProjectOxford.ai) and took the emotion data in JSON format.

Technically, we wrote a Windows UWP app running on Raspberry PI2 making the Emotion API call. This app generates a JSON file and we took this data into Azure Event Hubs and passed this stream into Azure Stream Analytics job which is storing the data into a Azure blob Storage as well as feeding the output into a PowerBI sink. We designed a live dashboard in Power BI showing the incoming data as well.

In addition to this we prepared an experiment in Azure Machine Learning to predict when will the right time to offer the product(s) of the bank to the customers.

Technologies used ;
 1) Window 10 UWP app running on Windows 10 IoT Core on a Raspberry PI2
 2) Cognitive Services (Emotions API specifically)
 3) Azure Events Hub, Azure Stream Analytics
 4) Power BI 
 5) Azure Machine Learning
