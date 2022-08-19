Will Stonebridge
Design Engineering Intern
August 18th, 2022

Accuracy Test Automator


--Purpose--

This software was designed to improve the speed and reliability of the “Accuracy Tests” the Liquid Flow team uses to evaluate its Liquid Flow Sensors. Relative to the monitor tests the team has been using, this software speeds up data analysis, reduces setup/oversight time and improves test insight during testing. 


--Getting Started--

NOTE: This software is designed to work with the 50ml syringe on a Syringe One pump, but it can work with other syringe pumps. If you are using a different type of syringe pump, you will need to create a control file for it (I discuss this towards the end of the video demo linked below).

1)	Start by connecting your physical setup, this should include an Ohaus scale, a syringe pump and one of our liquid flow sensors on a demo board.
2)	From the Github below, download the test automation software and put them into a folder. This folder should contain an images folder and multiple .py files. 
3)	Create a directory called “Result_Logs”. You should put this directory next to (not inside) the folder you created in the last step.
4)	Open the folder you created in step three as a project in your IDE of choice. I recommend PyCharm.
5)	Attempt to run the software via the main command in the main.py file. (In pycharm, this can be done by clicking the green arrow on line 18). 
a.	You may encounter some errors because some software libraries are not imported on your computer. This can be easily rectified by going to each failed import statement and then right clicking them for context actions, one of which will let you download the given library.
6)	Once you’re able to see the Automator Interface, you will be all setup and ready to run a test!


--Running Tests--

1)	Start by checking your setup’s tubing and sensor for bubbles. Remove any you find before testing.
2)	After your tubing is bubble free, refill your syringe to its full capacity. Once the syringe is full, tare your scale so it reads zero.
3)	On the Automation Interface, connect your scale, pump and demo board using the right panel.
4)	Queue up your tests using the left panel.
5)	Name your log directory (this is the name of the folder in “Result_Logs” that will contain all data after testing)
6)	Hit start and get a coffee as the Automator handles all testing, calculation and setup for you 😊
7)	At the end of testing, check the aforementioned log folder for the csv “cumulative_data0”. This contains all statistics from your series of tests.


--Some Helpful Definitions and Notes--

-	Scale Flow: The volume dispensed by the pump over the time the pump dispensed it.
-	Measured Flow: The flow recorded up by the sensor.
-	Pump Flow: The flow rate the pump is running at.
-	Scale Error: The error of the average measured flow relative to the scale flow.
-	Pump Error: The error of the average measured flow relative to the pump flow.

-	This software automatically refills the syringe on the syringe pump when it is about to run out of water! However, it assumes that the syringe has a capacity of 50 ml of water. If you are using a syringe with a different volume, you should alter the capacity parameter in the pump class (this is connection_one.py if you are using a syringe one)
-	If a bubble gets stuck in your test setup during testing, you can pause the Automator. Once you resume, the individual test you paused on will restart but all other previous tests will remain unaffected.
-	Pausing when the monitor says it is recording is ill-advised. If you do pause, this will prevent the software from recording and calculating data of the present test and the software will rerun this test once you resume.
-	If you want to connect your sensor, pump and scale at startup, I’ve included some commented lines at the end of the create method in GUI.py that will be helpful.


GitHub: https://github.com/WillStonebridge/Test_Automator.git 

Video Demo: https://drive.google.com/file/d/1mc3fS56ZT9nqAQK-zM8oIatq6a5Vxdwe/view?usp=sharing 

Will Stonebridge
