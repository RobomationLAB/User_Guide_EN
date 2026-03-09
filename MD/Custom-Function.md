This document explains custom functions that support smooth robot coding in RobomationLAB.

# Basic Utility Functions

Basic utility functions are functions that can be commonly used in the robot coding programs provided by RobomationLAB.  
Except for the `Wait` function, utility functions use the same code regardless of Python or JavaScript syntax.

Below, the role of each function and how to write the code are explained.

## Wait
This is a time-delay function used when executing code in a sequential manner.  
After waiting for the amount of time specified as a parameter, the next code is executed.  
The `await` keyword must be placed in front of it, and it can only be used inside functions marked with `async`.  
It cannot be used inside a `loop` function.

### Parameters
| Parameter | Range | Description | 
| --- | --- | --- | 
| time     | (Integer ≥ 0) | Time (Python: seconds, JavaScript: milliseconds) |
<br>

The wait function is an exception and uses different code depending on Python or JavaScript syntax.

### Python Code
```python
await asyncio.sleep(1)  # (seconds)
```

### JavaScript Code
```javascript
await __wait(1000);  // (milliseconds)
```


<br>

## Key Down
This function detects keyboard input and returns whether the keyCode provided as a parameter matches the last pressed key.  

### Parameters
| Parameter | Range | Description | 
| --- | --- | --- | 
| keyCode | (Integer ≥ 0) | keyCode value corresponding to a keyboard key |

### Code
```python
__keydown(0)  # (keyCode)
```

<br>

## Key Up
This function detects keyboard input and returns whether the keyCode provided as a parameter matches the last released key.  

### Parameters
| Parameter | Range | Description | 
| --- | --- | --- | 
| keyCode | (Integer ≥ 0) | keyCode value corresponding to a keyboard key |

### Code
```python
__keyup(0)  # (keyCode)
```

<br>

## Key Pressed
This function detects keyboard input and returns whether the set of currently pressed keys matches the given keyCode array provided as a parameter.  

### Parameters
| Parameter | Range | Description | 
| --- | --- | --- | 
| keyCode list | (Array) | List of keyCode values corresponding to keyboard keys |

### Code
```python
__keypressed([0, 0, 0, 0, 0])  # (keyCode list)
```

<br>

## Log
Console - This is a function that outputs the value of a specific variable to the log.

### Parameters
| Parameter | Range | Description | 
| --- | --- | --- | 
| signal | - | Value to be output to the log |
| tag | (String) | Tag (name) to be displayed in the log |
| unit | (String) | Unit to be displayed in the log |

### Code
```python
__log(0, '', '')  # (signal, title, unit)
```

<br>

## Scope
Console - This is a function that outputs the changes in specific variable values as a graph in the Scope window.

### Parameters
| Parameter | Range | Description | 
| --- | --- | --- | 
| title | (String) | Scope title |
| min | (Integer) | Minimum value |
| max | (Integer) | Maximum value |
| color | (String) | Line graph color |
| signal | - | Value to be displayed in the scope |

### Code
```python
__scope('', 0, 1, '#000000', 0);  # (title, min, max, color, signal)
```

<br>

## Random Color
This function returns a [red, green, blue] array with random RGB values.  

### Code
```python
__randomColor()
```

<br>

## Play Sound
This function plays a sound registered in the program through the PC or device.  

### Parameters
| Parameter | Range | Description | 
| --- | --- | --- | 
| name | - | Name of the sound to play |
| volume | (Integer, 0 ~ 100) | Sound volume |
| repeat | (Boolean) | Whether to repeat the sound |

### Code
```python
__playSound('', 100, True)  # (name, volume, repeat)
```

<br>

## Speak
This function converts text into speech and plays it through the PC or device.    

### Parameters
| Parameter | Range | Description | 
| --- | --- | --- | 
| text | (String) | Text to be played using TTS |

### Code
```python
__speak('')  # text
```

<br>

## Exit
This function terminates code execution. 

### Code
```python
__exit()
```

<br><br>

# Robot-Specific Special Functions

Robot-specific special functions are dedicated functions provided according to the hardware characteristics of each robot.  
They are used to perform actual actions or calculations such as robot movement, rotation, and kinematic operations.

Below, the role of each function, how to write the code, and the robots that use these functions are explained.

## Get Speed
This function converts the robot wheel speed entered as a value between 0 and 100 into the value required for the robot to actually move.

### Robots that use this function:  
Hamster S, Hamster, Pio, Turtle, Beagle

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| value     | (Float, 0 ~ 100) | Speed value to convert |

### Python Code
# Python  
```python
__getSpeed('', 50)  # (robot, value)
```

### JavaScript Code
```javascript
// JavaScript  
__getSpeed('', 50)  // (robot, value)
```

<br>

## Get Distance
This function converts the input distance (e.g., 30 cm, 500 mm) into the value required for the robot to actually move.

### Robots that use this function:  
Hamster S, Pio, Turtle, Beagle, RaccoonBot peripherals – Conveyor, Slider

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| value     | (Float) | Distance value to convert |
| unit      | ('cm' or 'mm') | Distance unit |

### Python Code
```python
__getDistance('', 50, 'cm')  # (robot, value, unit)
```

### JavaScript Code
```javascript
__getDistance('', 50, 'cm')  // (robot, value, unit)
```

<br>

## Turn Left in Place
This function rotates the robot to the left by **n** degrees while staying in place.  

### Robots that use this function:  
Hamster S, Pio, Turtle, Beagle  

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| degree    | (Integer, 0 ~ 360) | Rotation angle |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the rotation is completed, then execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.

### Python
```python
await __turn_degree_left('', 90, True)  # (robot, degree, wait_w)  
__turn_degree_left('', 90, False)  # (robot, degree, wait_w)  
```

### JavaScript
```javascript
await __turn_degree_left('', 90, true);  // (robot, degree, wait_w)  
__turn_degree_left('', 90, false);  // (robot, degree, wait_w)  
```

<br>

## Turn Right in Place
This function rotates the robot to the right by **n** degrees while staying in place.  

### Robots that use this function:  
Hamster S, Pio, Turtle, Beagle  

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| degree    | (Integer, 0 ~ 360) | Rotation angle |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the rotation is completed, then stop and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.  

### Python Code
```python
await __turn_degree_right('', 90, True)  # (robot, degree, wait_w)  
__turn_degree_right('', 90, False)  # (robot, degree, wait_w)  
```

### JavaScript Code
```javascript
await __turn_degree_right('', 90, true);  // (robot, degree, wait_w)  
__turn_degree_right('', 90, false);  // (robot, degree, wait_w)  
```

<br>


## Turbo
This function enables or disables the robot’s turbo mode.  

### Robots that use this function:  
Pio  

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| turbo     | (Boolean) | Whether to enable turbo mode |

### Python
```python
__turbo('', True)  # (robot, turbo)  
__turbo('', False)  # (robot, turbo)  
```

### JavaScript
```javascript
__turbo('', false);  // (robot, turbo)  
__turbo('', true);  // (robot, turbo)  
```

<br>

## Stop Move
This function stops the robot’s wheel movement.

### Robots that use this function:  
Hamster S (HamsterS), Pio, Turtle, Beagle  

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |

### Python Code
```python
__stopMove('')  # (robot)
```

### JavaScript Code
```javascript
__stopMove('');  // (robot)
```

<br>

## Stop After Delay
This function stops the robot’s wheel movement after waiting for a specified amount of time.

### Robots that use this function:  
Hamster S (HamsterS), Hamster, Pio, Turtle, Beagle

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| delay     | (Float ≥ 0) | Waiting time before stopping |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the specified time has passed, then stop the wheel movement and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately, and the wheel movement stops after the specified time has passed.

### Python
```python
await __stopAfterDelay('', 5, True)  # (robot, delay, wait_w)  
__stopAfterDelay('', 90, False)  # (robot, delay, wait_w)
```

### JavaScript
```javascript
await __stopAfterDelay('', 5, true);  // (robot, delay, wait_w)  
__stopAfterDelay('', 90, false);  // (robot, delay, wait_w)
```

<br>

## Grid Turn Left
This function rotates the robot one step to the left while it is on the grid board.

### Robots that use this function:
Hamster S, Hamster, Pio

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the movement is completed, then stop and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.

### Python Code
```python
await __grid_turn_left('', True)  # (robot, wait_w)  
__grid_turn_left('', False)  # (robot, wait_w)
```

### JavaScript Code
```javascript
await __grid_turn_left('', true);  // (robot, wait_w)  
__grid_turn_left('', false);  // (robot, wait_w)
```

<br>

## Grid Turn Right
This function rotates the robot one step to the right while it is on the grid board.

### Robots that use this function:
Hamster S, Hamster, Pio

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the movement is completed, then stop and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.

### Python Code
```python
await __grid_turn_right('', True)  # (robot, wait_w)  
__grid_turn_right('', False)  # (robot, wait_w)
```

### JavaScript Code
```javascript
await __grid_turn_right('', true);  // (robot, wait_w)  
__grid_turn_right('', false);  // (robot, wait_w)
```

<br>

## Grid Move Forward
This function moves the robot forward by one cell while it is on the grid board.

### Robots that use this function:
Hamster S, Hamster, Pio

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the movement is completed, then stop and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.

### Python Code
```python
await __grid_move_forward('', True)  # (robot, wait_w)  
__grid_move_forward('', False)  # (robot, wait_w)
```

### JavaScript Code
```javascript
await __grid_move_forward('', true);  // (robot, wait_w)  
__grid_move_forward('', false);  // (robot, wait_w)
```

<br>

## Grid Move Backward
This function moves the robot backward by one cell while it is on the grid board.

### Robots that use this function:
Pio

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the movement is completed, then stop and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.

### Python Code
```python
await __grid_move_backward('', True)  # (robot, wait_w)  
__grid_move_backward('', False)  # (robot, wait_w)
```

### JavaScript Code
```javascript
await __grid_move_backward('', true);  // (robot, wait_w)  
__grid_move_backward('', false);  // (robot, wait_w)
```

<br>

## Grid Move Left
This function moves the robot one cell to the left while it is on the grid board.

### Robots that use this function:
Pio

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the movement is completed, then stop and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.

### Python Code
```python
await __grid_move_left('', True)  # (robot, wait_w)  
__grid_move_left('', False)  # (robot, wait_w)
```

### JavaScript Code
```javascript
await __grid_move_left('', true);  // (robot, wait_w)  
__grid_move_left('', false);  // (robot, wait_w)
```

<br>

## Grid Move Right
This function moves the robot one cell to the right while it is on the grid board.

### Robots that use this function:
Pio

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the movement is completed, then stop and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.

### Python Code
```python
await __grid_move_right('', True)  # (robot, wait_w)  
__grid_move_right('', False)  # (robot, wait_w)
```

### JavaScript Code
```javascript
await __grid_move_right('', true);  // (robot, wait_w)  
__grid_move_right('', false);  // (robot, wait_w)
```

<br>

## Pivot 
This function rotates the robot in place by **n** degrees in a desired direction based on a specific pivot axis.  

### Robots that use this function:  
Hamster S, Turtle  

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| unit      | (String) | Pivot axis |
| direction | (String) | Rotation direction |
| degree    | (Integer, 0 ~ 360) | Rotation angle |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the rotation is completed, then stop and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.

### Unit Options
The `unit` parameter can have the following values depending on the robot:  
Hamster S (HamsterS): left pen, right pen, left wheel, right wheel  
Turtle: left wheel, right wheel  
    
### Direction Options
The `direction` parameter can have the following values regardless of the robot:  
forward, backward

### Python Code
```python
await __pivot('', '', '', 90, True)  # (robot, unit, direction, degree, wait_w)  
__pivot('', '', '', 90, False)  # (robot, unit, direction, degree, wait_w)
```

### JavaScript Code
```javascript
await __pivot('', '', '', 90, true);  // (robot, unit, direction, degree, wait_w)  
__pivot('', '', '', 90, false);  // (robot, unit, direction, degree, wait_w)
```

<br>

## Pivot Circle 
This function rotates the robot by **n** degrees in a desired direction while drawing a circle with radius **k cm** based on a specific pivot axis.  

### Robots that use this function:  
Hamster S, Turtle  

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| unit      | (String) | Pivot axis |
| direction | (String) | Rotation direction |
| degree    | (Integer, 0 ~ 360) | Rotation angle |
| wait_w    | (Boolean) | Whether to wait |

If `wait_w` is set to true, use the `await` keyword to wait until the rotation is completed, then stop and execute the next code.  
If `wait_w` is set to false, the next code is executed immediately.

### Unit Options
The `unit` parameter can have the following values depending on the robot:  
Hamster S (HamsterS): left pen, right pen  
Turtle: ''  

### Direction Options
The `direction` parameter can have the following values regardless of the robot:  
left forward, left backward, right forward, right backward

### Python Code
```python
await __pivot_circle('', '', '', __getDistance('', 1, 'cm'), 90, True)  # (robot, unit, direction, radius, degree, wait_w)  
__pivot_circle('', '', '', __getDistance('', 1, 'cm'), 90, False)  # (robot, unit, direction, radius, degree, wait_w)
```

### JavaScript Code
```javascript
await __pivot_circle('', '', '', __getDistance('', 1, 'cm'), 90, true);  // (robot, unit, direction, radius, degree, wait_w)  
__pivot_circle('', '', '', __getDistance('', 1, 'cm'), 90, false);  // (robot, unit, direction, radius, degree, wait_w)
```

<br>

## Stop Sound 
This function stops sound playback on the robot.

### Robots that use this function:  
Hamster S (HamsterS), Hamster, Turtle, Pio, Beagle, RaccoonBot (Raccoon4)  

### Python Code
```python
__stopSound('')  # (robot)
```

### JavaScript Code
```javascript
__stopSound('');  // (robot)
```

<br>

## Forward Kinematics (angles to xyz)
This function calculates and returns the coordinates of the end-effector’s current position based on the robot arm’s joint angles.  
It converts each joint angle into xyz coordinates using the [Forward Kinematics](https://github.com/RobomationLAB/RaccoonBot_API_EN/wiki/4DoF-Kinematics#forward-kinematics) algorithm.

### Robots that use this function:  
RaccoonBot (Raccoon4)

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| angles    | (Array) | Joint angle array [j1, j2, j3, j4] |
| origin    | (String) | Reference point for coordinate calculation ('wrist', 'end_effector') |

### Python Code
```python
__angles_to_xyz('', [0, 0, 0, 0], 'wrist')  # (robot, angles, origin)
```

### JavaScript Code
```javascript
__angles_to_xyz('', [0, 0, 0, 0], 'end_effector')  // (robot, angles, origin)
```

<br>

## Inverse Kinematics (xyz to angles)
This function calculates and returns the four joint angles of the robot arm based on the current coordinates of the end-effector.  
It converts xyz coordinates into four joint angles using the [Inverse Kinematics](https://github.com/RobomationLAB/RaccoonBot_API_EN/wiki/4DoF-Kinematics#inverse-kinematics) algorithm.

### Robots that use this function:  
RaccoonBot (Raccoon4)

### Parameters
| Parameter | Range | Description | 
| --------- | ----------- | ----- | 
| robot     | (String) | Name of the robot to control |
| xyz       | (Array) | Coordinate array of the end-effector [x, y, z] |
| origin    | (String) | Reference point for coordinate calculation ('wrist', 'end_effector') |

### JavaScript Code
```javascript
__xyz_to_angles('', [0, 100, 100], 'wrist'); // (robot, xyz, origin)
```

### Python Code
```python
__xyz_to_angles('', [0, 100, 100], 'end_effector')  # (robot, xyz, origin)
```

<br>
