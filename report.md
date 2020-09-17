Anthony Biondo
August Bernhard	

My teammate and I have not used Python prior to this assignment. 
Therefore, some python conventions that may be immediately obvious to those who have learn
ed the language formally may not be followed. 
However, this also means we got more out of this project than our peers who may already be
 practiced in Python. First, we analysed the code provided to us. 
A few things stood out to us, for instance Add.argument and Asyncio, so we began our endea
vor by researching the keywords we were not familiar with. 
Python proved to be a very approachable language, and once we began to feel  comfortable w
ith the general syntax the coding itself became much easier. 
This familiarity allowed us to implement code of our own, such as the pandas function whic
h proved critical to analysing the data. 

	The zeroth task set out for us was very manageable, as we both have had experience wit
	h github before. 
	Unfortunately, one of our import functions was not working correctly and therefore it 
	took awhile to truly get the first code working. 
	This was solved by writing the import function into the code directly rather than use 
	it in a path. 
	The first task could be accomplished with only a few lines of code in client.py, which
	would append the file we created by adding any information as it came in. 
	In the second task, we relied on pandas to organize the data into probability density 
	functions. 
	With these probability density functions graphed, we can gauge easily the main charact
	eristics of the data. With the data organized, we can also use functions on it to find
	its median, variance, mean, etc. 
	For task 3, we set a standard deviation from the mean of the data as a bound, and comp
	ared each point's absolute difference to this bound to see which were outliers. 
	If it was an outlier, python would print its timestamp, and add it to an array which w
	ould later be dropped. 
	Once the faulty data points were dropped, it was trivial to run similar functions on t
	hem as in task 2 to find the new characteristics of the outlier-less data. 

	

Task 0

Greeting String: ECE Senior Capstone IoT simulator.




Task 1

In order to accomplish task 1 we added additional code to the client.py and called the fun
ction by using the command python ws_client.py -l SensorData20.txt in order to write the d
ata to the file SensorData20.txt

Task 2


Lab1 chart
Median Temperature 		21.003
Variance Temperature 	2.197
Occupancy Median 		5.000
occupancy Variance 		4.857
Time Interval Mean 		3.289
Time Interval Variance 	12.791

![Graphs](https://github.com/augustb21/2020-sensor-miniproject/blob/main/Screen%20Shot%202020-09-17%20at%206.58.54%20PM.png?raw=true)















Task 3


| Lab1 Chart       | Lab1   | Class1 | Office |  
|------------------|--------|--------|--------|
| % of Anomalies   | 3.802  | 3.861  | .704   | 
| Mean Temp        | 20.998 | 27.018 | 23.029 |   
| Variance of Temp | 0.138  | .737   | 3.795  |
				
% of Anomalies  Lab1: 3.802			Class 1: 3.861		Office: .704
Mean Temp		Lab1: 20.998 		Class 1: 27.018		Office: 23.029
Variance of Temp Lab1: 0.138		Class 1: 0.737		Office: 3.795

Does a persistent change in temperature always indicate a failed sensor?
           No. Our algorithm detects anomalies by comparing the data points to the other 
           data points through standard deviation to the mean. If a persistent change occurs 
           This will affect the variance and our algorithm will not flag it as outliers.
           Whether a persistent change indicates a failing sensor that is not flagged as 
           an outlier is a possible false negative. 
       
What are the possible bounds for each room?
In all three rooms, we use 1.5 standard deviations to get rid of outlier data. 
In the office, that is 2.22% of data points. 13 degrees from the median. In the lab, this 
gets rid of 6.25% of data points. 0.5 degrees from the median. 
In the class, this gets rid of 2% of data points. 6 degrees from the median. 

Task 4
	
How is this simulation reflective of the real world?
This simulation approaches real world scenarios. By simulating real world sensors, asking 
for the data being produced by those sensors is a common occurrence in many products. 
It is also realistic to have some faulty data within the data set, as sensors do not obtain
 their information perfectly. 
Additionally, in a world of social distancing, it's not inconceivable to be writing code f
or sensors far away from one’s physical self. 

2. 	How is this simulation deficient? What factors does it fail to account for?
 
This simulation is ultimately using make believe sensors. That means they will not turn of
f, they will not run into real word errors, and they will not have product specific quirks. 
Any outliers will be simple randomly generated numbers, not a string of numbers created fr
om a specific error. 
The made up sensors will be much neater than their real world counterparts. With that being
 said, real world sensors will most likely have software recommendations for how to analyse
  those sensors data. 
Creating our own software from scratch is unusual in today’s age. 

3. How is the difficulty of initially using this Python websockets library as compared to 
a compiled language e.g. C++ websockets
This was made easier as a non compiled language, as every time we wanted to test our code 
we did not need to run it or 20 minutes to get 20 minutes of data. 
Instead of needing to run it each time, we would just save the code and use the same data 
for each iteration of our code. 
Therefore, we could see in real time what was happening to our code, by using functions li
ke print to display the variable we were currently working on. 
C## may have needed us to run for the data file each time, adding 20 minutes for each iter
ation of code. 

4. Would it be better to have the server poll the sensors, or the sensors reach out to the
 server when they have data?

If the server polled the sensors, it would need to be constantly asking for data. Even whe
n the sensors are off. 
So, it would be more efficient to only send over data when the sensor is on and collecting
 data. 
Therefore, it makes the most sense for the sensor to send data to the server. 
