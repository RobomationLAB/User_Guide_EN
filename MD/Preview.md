**Preview** is an area that helps with robot coding by allowing you to check the **robot connection status** and by providing tools such as the code console and camera console.  
Below, the functions available in each tab are described.

## Robot Connection Status Tab

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/connections/sensor.png" alt="Block Composer" width="70%" /><br> 

In the Robot Connection Status tab, you can check information about the robots that are currently connected.  
By clicking **Hide Real-Time Sensor Values**, you can monitor the robot’s sensor data in real time, displayed as graphs or numerical values.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/connections/screen.png" alt="Block Composer" width="70%" /><br>

1. You can select which sensor to view, and the types of sensors supported vary by robot.  
   Depending on the selected sensor, the graph and data display format automatically adjust to match that sensor’s values.
2. You can choose the time interval (in seconds) at which sensor values are checked or recorded.  
   Based on the selected interval, the maximum duration for which data can be recorded and displayed on the graph will vary.
3. When you place the mouse cursor over the sensor graph, you can view the sensor value at that specific point in time in real time.
4. Start / Stop Recording: Records sensor data.
5. Export: Saves the recorded sensor data as a `.csv` file and the graph view as a `.png` file.  
   This feature is only available after data has been recorded.
6. Capture: Saves the current graph view as a `.png` file in real time.  
   You can record changes in sensor values and save both the recorded data files and the graph images as files.

<br>

## Code Tab

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/code/screen.png" alt="Block Composer" width="70%" /><br>

In the Code tab, you can see how adding or removing blocks is reflected in **Python** and **JavaScript** code in real time.  
By observing how blocks are converted into code, you can more easily learn and understand coding syntax.

※ The Code tab is available **only in the Block Coding Editor**.  
In the Python / JavaScript editors, users write code directly, so a separate Code tab is not provided.

<br>

## Camera Tab

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/camera/select.png" alt="Block Composer" width="70%" /><br>

In the Camera tab, you can view the live video feed from a camera connected to your PC in real time.

This feature is enabled **only when a camera-based extension module is added to the program**, and a corresponding camera module will appear in the Camera tab.  
Each camera module provides the following functions:

- Select one of the cameras available on the current PC and display its video feed.
- Use the **On / Off** button to show or stop the camera view.

<br>

## Console Tab

In the Console tab, you can monitor log messages (Log) and scope graphs (Scope) in real time while the program is running.  
This tab is useful for debugging, sensor value monitoring, and graph-based analysis.

### Log
By using the **Log Output** block, you can print text or numeric values to the console log area together with a specified tag.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/console/log_block.png" alt="Block Composer" width="30%" /><br>

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/console/log.png" alt="Block Composer" width="70%" /><br>

### Scope

By using the **Scope Output** block, you can visualize numeric values as **real-time graphs** for each tag.  
You can configure the minimum value, maximum value, and graph color to visually monitor changes in the desired data.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/console/scope_block.png" alt="Block Composer" width="40%" /><br>

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/console/scope.png" alt="Block Composer" width="70%" /><br>
