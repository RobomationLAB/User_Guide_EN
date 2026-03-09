This document explains RobomationLAB, a robot coding education platform that is part of Robomation’s “Execution Engine and Integrated Authoring Environment for Robot Motion Streaming Services”.  

It provides a detailed explanation in the following order:  
- Main features of RobomationLAB
- Robot programming methods of RobomationLAB
- Principles of robot software modeling 
- Basic grammar system of RobomationLAB

<br>

# Table of Contents
1. [RobomationLAB - Robot Coding Education Platform](#robomationlab---robot-coding-education-platform)  
    1-1) [Robot Coding Program](#robot-coding-program)  
    1-2) [Main Features of the Coding Program](#main-features-of-the-coding-program)  
    1-3) [Real-Time Robot Control Method](#real-time-robot-control-method)  

2. [RobomationLAB - Robot Programming Method](#robomationlab---robot-programming-method)  
    2-1) [Sequential Execution and Parallel Execution](#sequential-execution-and-parallel-execution)  
    2-2) [setup Function](#setup-function)  
    2-3) [loop Function](#loop-function)  

3. [Robot Software Modeling](#robot-software-modeling)  
    3-1) [Modeling Process](#modeling-process)  
    3-2) [Roboid Class Definition](#roboid-class-definition)  
    3-3) [Unique Identifier, urn](#unique-identifier-urn)  

4. [RobomationLAB - Basic Grammar System for Robot Coding](#robomationlab---basic-grammar-system-for-robot-coding)  
    4-1) [Robot Device Objects](#robot-device-objects)  
    4-2) [d Function](#d-function)  
    4-3) [c Function](#c-function)  
    4-4) [e Function](#e-function)  
    4-5) [w Function](#w-function)   

<br><br>

# RobomationLAB - Robot Coding Education Platform
RobomationLAB is a platform optimized for **AI robotics software education**,  
providing a Chrome web browser–based integrated authoring environment for robot coding education targeting elementary and middle school students.  

RobomationLAB offers various robot coding education programs such as **block coding** and **script coding**.  
In addition to learning coding theory, learners can actually move and control robots using Robomation’s products,  
providing opportunities to learn both coding and robotics at the same time.

<br>

## Robot Coding Program

### Block Composer
**Block Composer is a tool that allows users to easily and quickly control Robomation robots through block coding and learn the basics of robot control.**  

- An authoring environment optimized for physical computing  

- Easy coding for beginners using block Drag & Drop  
- Learning environment that provides basic concepts and prevents syntax errors  
- Automatic conversion to JavaScript and Python script code  
- A collection of predefined blocks with robot-specific functions and various hands-on examples  
- Real-time result verification through code execution  
- Improvement of problem-solving skills and creativity through block combinations  
- Optimized feedback provided through AI-based script code analysis  

<br>

### Script Composer
**Script Composer is a tool that allows users to easily and quickly control Robomation robots through script coding and learn the basics of Python, JavaScript syntax, and robot coding.**  

- Simultaneous support for Python and JavaScript editors  

- Automatic code completion and code insertion features by language  
- Various hands-on example codes provided for each robot  
- Real-time result verification through code execution  
- Optimized feedback provided through AI-based script code analysis  

<br>  

## Main Features of the Coding Program
The main features of the robot coding programs provided by RobomationLAB are as follows.  
1. Chrome web browser–based, with no dependency on the operating system (OS)  
2. Direct control of robot hardware via USB dongle using Web Serial communication  
3. Support for simultaneous control of multiple robots – no limitation on robot type or quantity  
4. When saving files, outputs are converted and stored as JSON text files  

<br>

## Real-Time Robot Control Method
In the robot coding programs provided by RobomationLAB, robots are controlled in real time through the following process.  
1. Through block coding or script coding,  
   write code that sets values for Effector and Command objects to control the robot,  
   or utilizes the robot’s Sensor values and Event occurrences.  
2. Execute the code.  
3. Receive packets containing Sensor and Event data from the robot via Web Serial communication  
   and reflect them in the robot Device objects.  
4. Interpret the code in real time,  
   overwrite data in Effector and Command objects, or read values from Sensor and Event objects.  
5. Generate packets reflecting the data of the robot Device objects,  
   then send them to the robot via Web Serial communication to verify actual robot operation.  
6. While the code is running, steps 3 to 5 are repeated approximately every 10–20 ms.

<br><br>

# RobomationLAB - Robot Programming Method

## Sequential Execution and Parallel Execution
There are two ways to program robots: sequential execution and parallel execution.  
Sequential execution is a method in which the next action is performed after one action is completed, and it is suitable for coding simple behaviors.  
For example, if you want the robot to move forward, then stop and turn on an LED, sequential execution is required so that the code corresponding to each action is arranged in order and executed chronologically.  

Parallel execution is a method in which multiple actions are performed simultaneously, and it is necessary for programming more complex and advanced behaviors.  
For example, to implement a walking motion for a bipedal robot, the robot’s feet and legs must move at the same time, so parallel execution coding must be possible.  

The robot coding programs provided by RobomationLAB  
support both sequential execution and parallel execution at the same time,  
based on a setup / loop code structure similar to Arduino’s H/W development environment.

<img src="https://github.com/user-attachments/assets/cc820f34-6687-4478-99ee-f5289f9bbf3a" alt="Block Composer" /><br> 

When you first access Block Composer, two empty function blocks appear in the workspace as shown above.  
The “Start” block represents the `setup` function, and the “Repeat Forever” block represents the `loop` function.  

Blocks are converted into Python / JavaScript code in real time,  
and the code has the following basic structure depending on the programming language.  

```python
# Python basic code structure
import asyncio

# put setup code here, to run once:
async def setup():
    return

# put control code here, to run repeatedly:
def loop():
    return
```

```javascript
// JavaScript basic code structure
// put setup code here, to run once:
async function setup() {
}
// put control code here, to run repeatedly:
function loop() {
}
```

<br>

## setup Function
The setup function is executed only once at the moment when “Run Code” is triggered.  
In the setup function, code is mainly written to initialize variables or to initialize the robot’s mode, functions, and settings.  
For example, when controlling a robot that moves using wheels, the initial wheel speed can be set in the setup function.  

In addition, the `async` keyword attached before the setup function allows the code inside the function to be executed sequentially.  
The async/await approach is a method added to modern JavaScript and Python,  
which designates a specific function as an asynchronous function and waits until its operation is completed without affecting the execution of other code.  

In practice, the setup function is executed only once at the beginning of code execution.  
However, if there is code with the `await` keyword inside the function, the function wakes up after a specified time or action and then executes the next code,  
so it can be considered to remain active.  
By using this feature, not only simple sequential execution but also powerful robot programming is possible through integration with the loop function, which plays the role of parallel execution.  

The following is an example of writing code in which a HamsterS robot moves forward for 1 second and then moves backward for 1 second.  
If this behavior were implemented inside the loop function using a parallel execution method, time calculations and control code would be mixed, making the code very complex.  
Instead, by using the time-delay function `__wait` with the `await` keyword inside the setup function,  
it is possible to write code that operates in chronological order as if it were synchronous.  
(The `__wait` function will be explained again later in [Basic Utility Functions](https://github.com/RobomationLAB/User_Guide_EN/wiki/Custom-Function#basic-utility-functions).)

Example Code (JavaScript)  
```javascript
// put setup code here, to run once:
async function setup() {
    // Move forward by setting both wheel speeds to 50
    $('HamsterS*0:wheel.speed.left').d = 50;
    $('HamsterS*0:wheel.speed.right').d = 50;
    await __wait(1000);  // Wait for 1 second (1000 milliseconds)
    // Move backward by setting both wheel speeds to -50
    $('HamsterS*0:wheel.speed.left').d = -50;
    $('HamsterS*0:wheel.speed.right').d = -50;
    await __wait(1000);  // Wait for 1 second (1000 milliseconds)
}

// put control code here, to run repeatedly:
function loop() {
}
```
( The `$` syntax will be explained again later in [RobomationLAB - Basic Grammar System for Robot Coding](#robomationlab---basic-grammar-system-for-robot-coding). )

<br>

## loop Function
The `loop` function supports parallel execution and is repeatedly executed approximately every 10–20 ms while the code is running.  
In the `loop` function, you typically write code that repeatedly updates variable values or detects and handles specific robot events.  

Below is an example that changes the wheel speed and LED brightness of the HamsterS robot over time.  

```javascript
var frame;

// put setup code here, to run once:
async function setup() {
    frame = 0;
}
// put control code here, to run repeatedly:
function loop() {
    frame += 1;  // Increase the value of the frame variable by 1 each time the loop function is called

    // Use the updated frame value to set both wheel speeds and the RGB values of both LEDs
    $('HamsterS*0:wheel.speed.left').d = frame % 100;
    $('HamsterS*0:wheel.speed.right').d = frame % 100;
    $('HamsterS*0:led.left').d = [frame % 256, 0, 0];
    $('HamsterS*0:led.right').d = [0, 0, frame % 256];
}
```
( The `$` syntax will be explained again later in [RobomationLAB - Basic Grammar System for Robot Coding](#robomationlab---basic-grammar-system-for-robot-coding). )

The following is an example of writing code that turns the LED red when a Tap action—lightly tapping the body of the HamsterS robot—occurs.  

```python
import asyncio

# put setup code here, to run once:
async def setup():
    return

# put control code here, to run repeatedly:
def loop():
    # Detect the moment when a Tap action occurs
    if __('HamsterS*0:gravity.tap').e == True:  # True when an event is detected
        __('HamsterS*0:led.left').d = [255, 0, 0]  # Set the LED red value to 255
    else:
        __('HamsterS*0:led.left').d = [0, 0, 0]
    return
```
( The `__` and `.e` syntax will be explained again later in [RobomationLAB - Basic Grammar System for Robot Coding](#robomationlab---basic-grammar-system-for-robot-coding). )

<br><br>

# Robot Software Modeling
This section defines the minimum system configuration for streaming-based robot hardware control and a JSON-based markup grammar.

## Modeling Process
The robot software modeling process is broadly as follows.
1. Abstract and organize the functions, sensors, and characteristics of the robot hardware.
2. Using predefined blocks with specified classes, names, and data types, define Device objects that correspond one-to-one with the robot hardware.
3. Combine each defined Device object block to create a single model.  
   The model obtained by abstracting robot hardware into software in this way is called a `Roboid`.
4. Each block inside the Roboid is converted into a JSON data object according to predefined rules.
5. Subclass objects are connected in a structure that inherits the characteristics of superclass objects, and are ultimately converted into a single JSON dataset with a tree structure.  
   If block B is contained within block A, block A becomes the upper (parent) class object of block B,  
   block B becomes the lower (child) class object of block A, and inherits the characteristics of block A.

<br>

## Roboid Class Definition
The classes of Device objects that make up a Roboid are as follows.  

#### Roboid
<img src="https://github.com/user-attachments/assets/fb0630e8-eead-493b-a19f-a7d0f5fb16f1" alt="Block Composer" /><br>

The Roboid class is the top-level parent class and represents which Roboid (robot) it is.  
The Roboid class consists of one or more units or Devices as its components.  
It has the properties name, implement (model name), and pid (unique product ID).  
The delimiter used is :.

#### Module
<img src="https://github.com/user-attachments/assets/089a95e1-86de-4e78-9777-685d9125455b"alt="Block Composer" /><br>

The Module class is used to define modules that extend the functionality of the Roboid class.  
External communication depends on the Roboid class, but functionally it is independent and internally has its own interface.  
It has the same internal structure as the Roboid class and consists of one or more units or Devices as components.  
For example, among the peripherals of the Raccoon robot arm, the Conveyor has its own internal interface, but external communication operates by depending on the Raccoon.  
It has the properties name and mid (module unique ID).  
The delimiter used is +.

#### Slot
<img src="https://github.com/user-attachments/assets/b6f7c2c9-6f46-4780-ade2-f096cf86582e" alt="Block Composer" /><br> 

The Slot class represents an interface to which a Module can be attached.  
When selecting and using one module among multiple available Modules, the Slot can be used to distinguish them.  
It has the properties name and module (connected module ID).  
The delimiter used is >.

#### Unit
<img src="https://github.com/user-attachments/assets/1da493b4-b9ac-4cc8-861b-6dd0fe077b28" alt="Block Composer" /><br> 

The Unit class is used simply to distinguish names without having any special functionality, and it serves as a container that groups Devices with similar characteristics.  
It has the property name.  
The delimiter used is ..


### Notifier
A Notifier represents a type of device class that transmits information in a one-way manner at regular intervals, regardless of whether data reception is successful.  

A device is classified as a Notifier if it meets any of the following conditions.  
1) A device that changes rapidly and continuously over time  
2) A device for which intermediate numerical values are meaningful  
3) A device for which reception success is not important  
4) A device for which information about execution progress or completion status is not required  

Device objects that fall under the Notifier category include the Effector and Sensor classes.

#### Effector
<img src="https://github.com/user-attachments/assets/3578e92f-13cb-4878-afc1-4e5ad52aa689" alt="Block Composer" /><br>

The Effector class represents controllable devices among the physical components that make up a robot.  
Examples include a motor’s speed value, an LED’s brightness value, and a buzzer’s frequency value.  
It has the properties name, type (data type), size (data size), min (minimum value), max (maximum value), and unit.  
There is no delimiter.

#### Sensor
<img src="https://github.com/user-attachments/assets/e461d463-021d-4178-8c28-b4b57bc2c287" alt="Block Composer" /><br> 

The Sensor class represents devices among the physical components of a robot that generate data.  
Examples include temperature sensors, acceleration sensors, and encoder values.  
It has the properties name, type (data type), size (data size), min (minimum value), max (maximum value), and unit.  
There is no delimiter.


### Responder
Responder represents a device class for which it is necessary to determine whether data reception was successful.

A device is classified as a Responder if it satisfies at least one of the following conditions:
1) Devices where successful reception or completion status is important  
2) Devices where intermediate values or execution process information are not required  

Device objects that fall under the Responder category include the Command and Event classes.

#### Command
<img src="https://github.com/user-attachments/assets/4b04c534-1396-4e46-9b3b-898428394945" alt="Block Composer" /><br> 

The Command class represents a controllable device similar to an Effector, and is used to define control commands that must be delivered to the robot.  
By writing data to a Command object, control commands can be sent to the robot. Each time a command is sent, the internal `command_id` value is incremented, allowing the number of issued commands to be tracked.  

It has the following properties:  
name (name), type (data type), size (data size), min (minimum value), max (maximum value).  

There is no separator.

#### Event
<img src="https://github.com/user-attachments/assets/cee4c3e6-c825-4443-a7e0-4a140ac535a9" alt="Block Composer" /><br> 

The Event class represents a device that generates data, similar to a Sensor, and is used to define specific events that must be detected.  
Each time a response for a specific event is received from the robot, the internal `event_id` value is incremented, and at that moment the `e` value is set to `true`, allowing the occurrence of the event to be identified.

It has the following properties:  
name (name), type (data type), size (data size), min (minimum value), max (maximum value).

There is no separator.


### Action, Servo
The Action and Servo classes represent devices that require time to complete the execution of a command.

#### Action
<img src="https://github.com/user-attachments/assets/c617ed22-841a-48e0-b4b0-95b5f076b574" alt="Block Composer" /><br> 

The Action class is used when issuing a command for the robot to perform a specific action and when it is necessary to check whether that action has been completed.  
It has the following properties:  
name (name), type (data type), size (data size), min (minimum value), max (maximum value).

When an Action object is created, an Event object is automatically created internally.  
The properties of the generated Event object are as follows:  
Name: `!{name}` / Data type: `uint8` / Data size: `0` / Minimum value: `0` / Maximum value: `0`.

There is no separator.

#### Servo
<img src="https://github.com/user-attachments/assets/41f10b8e-0c4f-4f11-8e5f-db786f9dbd6d" alt="Block Composer" /><br> 

The Servo class is used to issue commands for the robot to perform a specific action, to monitor the execution process, and to check whether the action has been completed.  
Examples include setting robot joint angles and commands related to moving a certain distance or rotating by a certain angle.  
It has the following properties:  
name (name), type (data type), size (data size), min (minimum value), max (maximum value), unit (unit).

When a Servo object is created, Event and Sensor objects are automatically created internally.  
The properties of the generated Event object are as follows:  
Name: `!{name}` / Data type: `uint8` / Data size: `0` / Minimum value: `0` / Maximum value: `0`.

The generated Sensor object outputs intermediate values and is used to monitor the execution process.  
Its name is set to `~{name}`, and it has the same data type and size properties as the Servo object.

There is no separator.


#### Constant
<img src="https://github.com/user-attachments/assets/33311454-9b56-4164-b37b-6531d0498fb1" alt="Block Composer"  /><br> 

The Constant class is used to predefine constant values that each Device object can have by default.  
It has the following properties:  
name (name), value (value).

A caret symbol ^ is prefixed to the object’s name.  
There is no separator.


<br>

### Unique Identifier, URN
Each Roboid and Device object has a unique identifier called a URN.  
The URN of each object is determined based on the following rules:

> { URN of a Roboid class object }   
> = { implement } + '*' + { index number } + { roboid object separator }

> { URN of a Device object }  
> = { URN of the parent Device object } + { name of the Device object } + { Device object separator }

When only one robot is used, the index number is 0.  
When using multiple robots, the index number increases according to the number of robots of the same type  
(e.g. 0, 1, 2, …).

<br><br>

# RobomationLAB - Basic Grammar System for Robot Coding
When writing code in the robot coding programs provided by RobomationLAB, the following basic syntax rules must be followed.

### Robot Device Objects
Robot Device objects can be accessed in the following ways depending on the programming language.

```python
# Python
__('{Device object URN}')
```

```javascript
// JavaScript
$('{Device object URN}')
```
Using this object, you can write code to read or write values.

<br>

### d Function
The d function is used to handle the data (value) of a Device object, allowing you to read from or write to the object.  
It is mainly used to set values of Effector class objects, or to input commands into Command and Action class objects.

Depending on the programming language, the code is written as follows.

1. Reading a value
```python
# Python
__('{Device object urn}').d
```

```javascript
// JavaScript
$('{Device object urn}').d
```

2. Writing a value
```python
# Python
__('{Device object urn}').d = {value}
```

```javascript
// JavaScript
$('{Device object urn}').d = {value}
```

### c Function
The c function is used to handle the command invocation count of a Device object.  
It is read-only and returns the number of times a value has been written to the Device object.  
It is mainly used to check how many times a specific action has been executed through a Command class object.

Depending on the programming language, the code is written as follows:

```python
# Python
__('{Device object urn}').c
```

```javascript
// JavaScript
$('{Device object urn}').c
```

### e Function
The e function is used to handle event processing of a Device object.  
It is read-only and is available only for Event class objects.  
When a state change or an environmental change occurs in an Event object, this function detects the event and returns true at the moment the event occurs.

The e value of all Device objects is set before the loop function starts,  
and it is automatically reset to false after each execution of the loop function.

Depending on the programming language, the code is written as follows:

```python
# Python
__('{Device object urn}').e
```

```javascript
// JavaScript
$('{Device object urn}').e
```

### w Function
The w function is used to wait for a Device object’s operation-completion event.  
It is available only for Event class objects derived from Action or Servo classes,  
and it waits until the event indicating that a specific operation has been completed occurs.

After the event is detected, the program continues executing the next code.

Depending on the programming language, the code is written as follows:

```python
# Python
await __('{Device object urn}').w()
```

```javascript
// JavaScript
await $('{Device object urn}').w();
```

**Important Notes**  
The w function waits until a specific operation is completed, so it must be used together with the await keyword.  

In this case, any code that uses the await keyword must be written inside an async function.  
Therefore, when using the w function in the RobomationLAB coding program,  
it must be used inside the setup function, which is an async function,  
and must not be used inside the loop function.

<br>