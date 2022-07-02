# Door-Alarm-System
In this project, we are going to make a door alarm system using the HC-SR04 ultrasonic sensor. The ultrasonic sensor used in this project is used as a distance sensor, it will tell us the distance at which the object is placed. Using this distance value, we will turn the buzzer on or off.<br>
![image](https://user-images.githubusercontent.com/54525786/177015889-d06c3351-41b5-4dbb-9de3-7df25fdcd134.png)
#Circuit Diagram
![image](https://user-images.githubusercontent.com/54525786/177015954-220cd7dc-a995-4073-af25-dab90056607a.png)
#How Does the Arduino Door Alarm Work?
The ultrasonic sensor emits an ultrasonic wave from the trigger which comes back after hitting the object and it is received by the echo. The echo will then tell us the distance traveled in microseconds. To send an ultrasonic wave from the trigger, we will have to set the trigger high for 10us. This will send an 8 cycle sonic burst at 40 kHz which will hit the object and is then received by the echo.<br>

We have got the time in microseconds but we need to calculate the distance. So, we will use the equation below. <br>

S = v * t <br>

We have the value of t and we know that the speed of a sound wave is 340m/s. We have to convert the speed of sound into cm/us to calculate the distance. The speed of sound in cm/us is 0.034cm/us. The equation now will become ...<br>

S = (0.034 * t)<br>

We will divide this equation by 2 because we only require the distance it takes to hit the object and not the distance it takes to hit the object and come back. So, the final equation will be <br>

S = (0.035 * t)/2 <br>

We will get the distance value using the equation above and after that, we will set a value which will help us make the buzzer high or low.<br>
