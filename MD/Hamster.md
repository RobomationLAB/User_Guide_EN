# Blocks
## Set Wheel Speed
Sets the hamster’s wheel speed.  
If the wheel speed is positive, it rotates forward, and if the wheel speed is negative, it rotates backward.  
For example, if the wheel speed is 100, it rotates forward at speed 100,  
and if the wheel speed is -100, it rotates backward at speed 100.  
Once you set the wheel speed, the hamster will keep moving at that speed until you set the wheel speed again.

<img src="https://github.com/user-attachments/assets/9a7689f8-e0c9-44de-9734-ee75e1bdd429" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type | left, right, both |
| velocity | Input Value | Wheel speed | Integer -100 ~ 100, 0: stop | 

### JavaScript Code
```javascript
// Set hamster left wheel speed to 50
$('Hamster*0:wheel.speed.left').d = __getSpeed('Hamster*0', 50); // (robot, speed)

// Set hamster right wheel speed to 30
$('Hamster*0:wheel.speed.right').d = __getSpeed('Hamster*0', 30); // (robot, speed)

// Set hamster both wheel speeds to -10
$('Hamster*0:wheel.speed.left').d = __getSpeed('Hamster*0', -10); // (robot, speed)
$('Hamster*0:wheel.speed.right').d = __getSpeed('Hamster*0', -10); // (robot, speed)
```

### Python Code
```python
# Set hamster left wheel speed to 50
__('Hamster*0:wheel.speed.left').d = __getSpeed('Hamster*0', 50) # (robot, speed)

# Set hamster right wheel speed to 30
__('Hamster*0:wheel.speed.right').d = __getSpeed('Hamster*0', 30) # (robot, speed)

# Set hamster both wheel speeds to -10
__('Hamster*0:wheel.speed.left').d = __getSpeed('Hamster*0', -10) # (robot, speed)
__('Hamster*0:wheel.speed.right').d = __getSpeed('Hamster*0', -10) # (robot, speed)
```

## Move by Time
Sets the time the hamster will move.  
If wheel speed is not set, it will not move.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/949659c6-838e-4e8a-b9db-282e5813d479" width="100%" height="100%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| time | Input Value | Time value | Real number ≥ 0 |
| unit | Dropdown Option | Time unit | seconds, milliseconds | 

If you set the option to milliseconds, the input will be the value of time divided by 1000.

### JavaScript Code
```javascript
// Move 5 seconds | Wait O
await __stopAfterDelay('Hamster*0', 5, true); // (robot, time, wait_w)

// Move 1 millisecond | Wait X
__stopAfterDelay('Hamster*0', 0.001, false); // (robot, time, wait_w)
```

### Python Code
```python
# Move 5 seconds | Wait O
await __stopAfterDelay('Hamster*0', 5, True) # (robot, time, wait_w)

# Move 1 millisecond | Wait X
__stopAfterDelay('Hamster*0', 0.001, False) # (robot, time, wait_w)
```

## Change Wheel Speed
Changes the hamster’s wheel speed.  
The new wheel speed becomes the current wheel speed plus the input value.  
The new wheel speed is clamped to the range -100 ~ 100.

<img src="https://github.com/user-attachments/assets/d5c9f69a-719a-4a9d-bde6-981bde2ce1ab" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type | left, right, both |
| velocity | Input Value | Value to add to current speed | Integer -200 ~ 200, 0: stop | 

### JavaScript Code
```javascript
// Change hamster left wheel speed by +50
$('Hamster*0:wheel.speed.left').d = $('Hamster*0:wheel.speed.left').d + __getSpeed('Hamster*0', 50);

// Change hamster right wheel speed by +10
$('Hamster*0:wheel.speed.right').d = $('Hamster*0:wheel.speed.right').d + __getSpeed('Hamster*0', 10);

// Change hamster both wheel speeds by -20
$('Hamster*0:wheel.speed.left').d = $('Hamster*0:wheel.speed.left').d + __getSpeed('Hamster*0', (-20));
$('Hamster*0:wheel.speed.right').d = $('Hamster*0:wheel.speed.right').d + __getSpeed('Hamster*0', (-20));
```

### Python Code
```python
# Change hamster left wheel speed by +50
__('Hamster*0:wheel.speed.left').d = __('Hamster*0:wheel.speed.left').d + __getSpeed('Hamster*0', 50)

# Change hamster right wheel speed by +10
__('Hamster*0:wheel.speed.right').d = __('Hamster*0:wheel.speed.right').d + __getSpeed('Hamster*0', 10)

# Change hamster both wheel speeds by -20
__('Hamster*0:wheel.speed.left').d = __('Hamster*0:wheel.speed.left').d + __getSpeed('Hamster*0', (-20))
__('Hamster*0:wheel.speed.right').d = __('Hamster*0:wheel.speed.right').d + __getSpeed('Hamster*0', (-20))
```

## Stop
Stops the hamster’s movement.  
Both wheel speeds are reset to 0.

<img src="https://github.com/user-attachments/assets/1e011f4a-a491-4a78-9f83-df51ec25b834" width="40%" height="40%" >

### JavaScript Code
```javascript
__stopMove('Hamster*0');
```

### Python Code
```python
__stopMove('Hamster*0')
```

## Move One Tile Forward on the Board
Moves the hamster forward by one tile on the board.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/646d33bd-797d-4847-a019-58e05b315595" width="80%" height="80%" >

### JavaScript Code
```javascript
// Move one tile forward | Wait O
await __grid_move_forward('Hamster*0', true); // (robot, wait_w)

// Move one tile forward | Wait X
__grid_move_forward('Hamster*0', false);  // (robot, wait_w)
```

### Python Code
```python
# Move one tile forward | Wait O
await __grid_move_forward('Hamster*0', True) # (robot, wait_w)

# Move one tile forward | Wait X
__grid_move_forward('Hamster*0', False) # (robot, wait_w)
```

## Turn Once on the Board
Rotates the hamster 90 degrees on the board in the given direction.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/4e9e7cf2-2276-45a6-b546-4378256ecc31" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Turn direction | left, right |

### JavaScript Code
```javascript
// Turn left once on the board | Wait O
await __grid_turn_left('Hamster*0', true); // (robot, wait_w)

// Turn left once on the board | Wait X
__grid_turn_left('Hamster*0', false); // (robot, wait_w)

// Turn right once on the board | Wait O
await __grid_turn_right('Hamster*0', true); // (robot, wait_w)

// Turn right once on the board | Wait X
__grid_turn_right('Hamster*0', false); // (robot, wait_w)
```

### Python Code
```python
# Turn left once on the board | Wait O
await __grid_turn_left('Hamster*0', True) # (robot, wait_w)

# Turn left once on the board | Wait X
__grid_turn_left('Hamster*0', False) # (robot, wait_w)

# Turn right once on the board | Wait O
await __grid_turn_right('Hamster*0', True) # (robot, wait_w)

# Turn right once on the board | Wait X
__grid_turn_right('Hamster*0', False) # (robot, wait_w)
```

## Follow a Line Using Sensors
The hamster follows a specific line using the floor sensors.

<img src="https://github.com/user-attachments/assets/2e8db30d-45a5-4750-9cb9-67a6787faeca" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Floor sensor position | left, right, center |
| color | Dropdown Option | Line color | black, white |

### JavaScript Code
```javascript
$('Hamster*0:wheel.trace.mode').d = 1; // Follow black line with left floor sensor
$('Hamster*0:wheel.trace.mode').d = 2; // Follow black line with right floor sensor
$('Hamster*0:wheel.trace.mode').d = 3; // Follow black line with center floor sensor
$('Hamster*0:wheel.trace.mode').d = 8; // Follow white line with left floor sensor
$('Hamster*0:wheel.trace.mode').d = 9; // Follow white line with right floor sensor
$('Hamster*0:wheel.trace.mode').d = 10; // Follow white line with center floor sensor
```

### Python Code
```python
__('Hamster*0:wheel.trace.mode').d = 1 # Follow black line with left floor sensor
__('Hamster*0:wheel.trace.mode').d = 2 # Follow black line with right floor sensor
__('Hamster*0:wheel.trace.mode').d = 3 # Follow black line with center floor sensor
__('Hamster*0:wheel.trace.mode').d = 8 # Follow white line with left floor sensor
__('Hamster*0:wheel.trace.mode').d = 9 # Follow white line with right floor sensor
__('Hamster*0:wheel.trace.mode').d = 10 # Follow white line with center floor sensor
```

## Turn, Then Follow Line & Stop at the Next Intersection
The hamster turns in the specified direction, then moves along the line until it reaches the next intersection.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/b240504d-3a9c-46cd-922c-31d4fd2dc45f" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Move direction | turn left, turn right, move forward, u-turn |
| color | Dropdown Option | Line color | black, white |

### JavaScript Code
```javascript
// Turn left, follow black line, stop at next intersection | Wait O
$('Hamster*0:wheel.trace.mode').d = 4; 
await $('Hamster*0:wheel.trace.!mode').w();

// Turn right, follow black line, stop at next intersection | Wait X
$('Hamster*0:wheel.trace.mode').d = 5;

// Go forward, follow black line, stop at next intersection | Wait O
$('Hamster*0:wheel.trace.mode').d = 6;
await $('Hamster*0:wheel.trace.!mode').w();

// U-turn, follow black line, stop at next intersection | Wait X
$('Hamster*0:wheel.trace.mode').d = 7;

// Turn left, follow white line, stop at next intersection | Wait O
$('Hamster*0:wheel.trace.mode').d = 11;
await $('Hamster*0:wheel.trace.!mode').w();

// Turn right, follow white line, stop at next intersection | Wait X
$('Hamster*0:wheel.trace.mode').d = 12;

// Go forward, follow white line, stop at next intersection | Wait O
$('Hamster*0:wheel.trace.mode').d = 13;
await $('Hamster*0:wheel.trace.!mode').w();

// U-turn, follow white line, stop at next intersection | Wait X
$('Hamster*0:wheel.trace.mode').d = 14;
```

### Python Code
```python
# Turn left, follow black line, stop at next intersection | Wait O
__('Hamster*0:wheel.trace.mode').d = 4
await __('Hamster*0:wheel.trace.!mode').w()

# Turn right, follow black line, stop at next intersection | Wait X
__('Hamster*0:wheel.trace.mode').d = 5

# Go forward, follow black line, stop at next intersection | Wait O
__('Hamster*0:wheel.trace.mode').d = 6
await __('Hamster*0:wheel.trace.!mode').w()

# U-turn, follow black line, stop at next intersection | Wait X
__('Hamster*0:wheel.trace.mode').d = 7

# Turn left, follow white line, stop at next intersection | Wait O
__('Hamster*0:wheel.trace.mode').d = 11
await __('Hamster*0:wheel.trace.!mode').w()

# Turn right, follow white line, stop at next intersection | Wait X
__('Hamster*0:wheel.trace.mode').d = 12

# Go forward, follow white line, stop at next intersection | Wait O
__('Hamster*0:wheel.trace.mode').d = 13
await __('Hamster*0:wheel.trace.!mode').w()

# U-turn, follow white line, stop at next intersection | Wait X
__('Hamster*0:wheel.trace.mode').d = 14
```

## Set Line Tracing Speed
Sets the hamster’s line tracing speed.  
Speed range is 1 ~ 10.

<img src="https://github.com/user-attachments/assets/4d5093f6-d39d-455a-bfa6-7d612c0708d8" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| velocity | Input Value | line tracing speed | Integer 1 ~ 10 | 

### JavaScript Code
```javascript
$('Hamster*0:wheel.trace.speed').d = 5; // Set line tracing speed to 5
```

### Python Code
```python
__('Hamster*0:wheel.trace.speed').d = 5 # Set line tracing speed to 5
```

## Stop Line Tracing
Stops the hamster’s line tracing feature.


<img src="https://github.com/user-attachments/assets/f94fa157-2445-48b9-a09b-8e115f710de8" width="70%" height="70%" >

### JavaScript Code
```javascript
$('Hamster*0:wheel.trace.mode').d = 0; // Stop line tracing
```

### Python Code
```python
__('Hamster*0:wheel.trace.mode').d = 0 # Stop line tracing
```

## Set LED Color
Sets the hamster’s LED color.  
You can set the left, right, or both LEDs.

<img src="https://github.com/user-attachments/assets/5754f48f-b9a5-4d9c-bd48-64cd304ffa43" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | LED side | left, right, both |
| color | Dropdown Option | Color | black(0), blue(1), green(2), cyan(3), red(4), magenta(5), yellow(6), white(7) |

### JavaScript Code
```javascript
// Set left LED color to red (4)
$('Hamster*0:led.left').d = 4;

// Set right LED color to green (2)
$('Hamster*0:led.right').d = 2;

// Set both LED colors to blue (1)
$('Hamster*0:led.left').d = 1;
$('Hamster*0:led.right').d = 1;
```

### Python Code
```python
# Set left LED color to red (4)
__('Hamster*0:led.left').d = 4

# Set right LED color to green (2)
__('Hamster*0:led.right').d = 2

# Set both LED colors to blue (1)
__('Hamster*0:led.left').d = 1
__('Hamster*0:led.right').d = 1
```

## Turn Off LED
Turns off the hamster’s LED color.  
You can turn off the left, right, or both LEDs.

<img src="https://github.com/user-attachments/assets/de5215f7-0db3-4e1f-8a0d-2da5731ec22a" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | LED side | left, right, both |

### JavaScript Code
```javascript
// Turn off left LED
$('Hamster*0:led.left').d = 0;

// Turn off right LED
$('Hamster*0:led.right').d = 0;

// Turn off both LEDs
$('Hamster*0:led.left').d = 0;
$('Hamster*0:led.right').d = 0;
```

### Python Code
```python
# Turn off left LED
__('Hamster*0:led.left').d = 0

# Turn off right LED
__('Hamster*0:led.right').d = 0

# Turn off both LEDs
__('Hamster*0:led.left').d = 0
__('Hamster*0:led.right').d = 0
```

## Set Buzzer Frequency
Sets the hamster’s buzzer sound to the specified frequency.  
Frequency range is 10Hz ~ 4200Hz.

<img src="https://github.com/user-attachments/assets/44eb9c82-d4c7-45dc-846e-6d17aa39883b" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| sound | Input Value | Buzzer frequency | 10 ~ 4200 (Hz) |

### JavaScript Code
```javascript
// Set buzzer frequency to 4200Hz
$('Hamster*0:sound.buzz').d = 4200;
```

### Python Code
```python
# Set buzzer frequency to 4200Hz
__('Hamster*0:sound.buzz').d = 4200
```

## Play a Note
Plays the specified musical note on the hamster.

<img src="https://github.com/user-attachments/assets/3d2d73c7-5ef9-465f-a010-16de9dfc0682" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| note | Dropdown Option | Note | Do, Do#, Re, Re#, Mi, Fa, Fa#, So, So#, La, La#, Si |
| octave | Dropdown Option | Octave | 1 ~ 7 |

### JavaScript Code
```javascript
// Play octave 1 Do
$('Hamster*0:sound.note').d = 4;

// Play octave 1 Re
$('Hamster*0:sound.note').d = 6;

// Play octave 2 Do
$('Hamster*0:sound.note').d = 16;

// Play octave 7 Si
$('Hamster*0:sound.note').d = 87;
```

### Python Code
```python
# Play octave 1 Do
__('Hamster*0:sound.note').d = 4

# Play octave 1 Re
__('Hamster*0:sound.note').d = 6

# Play octave 2 Do
__('Hamster*0:sound.note').d = 16

# Play octave 7 Si
__('Hamster*0:sound.note').d = 87
```

## Stop Sound
Turns off the hamster’s sound.

<img src="https://github.com/user-attachments/assets/88620a87-7150-4fe2-a03a-145024586ff0" width="40%" height="40%" >

### JavaScript Code
```javascript
// Stop hamster sound
__stopSound('Hamster*0');
```

### Python Code
```python
# Stop hamster sound
__stopSound('Hamster*0')
```

## Wheel Speed Value
Gets the specified hamster wheel speed value.

<img src="https://github.com/user-attachments/assets/bf469182-97ac-4c54-b700-9bfd2c27e85f" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left, right |

### JavaScript Code
```javascript
// Left wheel speed
__getSpeedInput('Hamster*0', $('Hamster*0:wheel.speed.left').d);

// Right wheel speed
__getSpeedInput('Hamster*0', $('Hamster*0:wheel.speed.right').d);
```

### Python Code
```python
# Left wheel speed
__getSpeedInput('Hamster*0', __('Hamster*0:wheel.speed.left').d)

# Right wheel speed
__getSpeedInput('Hamster*0', __('Hamster*0:wheel.speed.right').d)
```

## Proximity Sensor Value
Gets the specified hamster proximity sensor value.

<img src="https://github.com/user-attachments/assets/24151e4f-c250-4373-83d7-43085fc24853" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left, right |

### JavaScript Code
```javascript
// Left proximity sensor value
$('Hamster*0:proximity.left').d;

// Right proximity sensor value
$('Hamster*0:proximity.right').d;
```

### Python Code
```python
# Left proximity sensor value
__('Hamster*0:proximity.left').d

# Right proximity sensor value
__('Hamster*0:proximity.right').d
```

## Floor Sensor Value
Gets the specified hamster floor sensor value.

<img src="https://github.com/user-attachments/assets/0c30decc-48ce-47be-b5a0-e284824888d6" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left, right |

### JavaScript Code
```javascript
// Left floor sensor value
$('Hamster*0:floor.left').d;

// Right floor sensor value
$('Hamster*0:floor.right').d;
```

### Python Code
```python
# Left floor sensor value
__('Hamster*0:floor.left').d

# Right floor sensor value
__('Hamster*0:floor.right').d
```

## Acceleration Value
Gets the acceleration value for a specific axis of the hamster.

<img src="https://github.com/user-attachments/assets/3395f017-a9e7-498c-ba62-08a7edf4a3d4" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| axis | Dropdown Option | Axis | x, y, z |

### JavaScript Code
```javascript
// Acceleration value on x-axis
$('Hamster*0:acceleration.x').d;

// Acceleration value on y-axis
$('Hamster*0:acceleration.y').d;

// Acceleration value on z-axis
$('Hamster*0:acceleration.z').d;
```

### Python Code
```python
# Acceleration value on x-axis
__('Hamster*0:acceleration.x').d

# Acceleration value on y-axis
__('Hamster*0:acceleration.y').d

# Acceleration value on z-axis
__('Hamster*0:acceleration.z').d
```

## Light Sensor Value
Gets the hamster’s light sensor value.

<img src="https://github.com/user-attachments/assets/52b53868-37cf-4aa8-9034-019ccb3ee12d" width="40%" height="40%" >

### JavaScript Code
```javascript
// Light sensor value
$('Hamster*0:light').d; 
```

### Python Code
```python
# Light sensor value
__('Hamster*0:light').d
```

## Temperature Sensor Value
Gets the hamster’s temperature sensor value.

<img src="https://github.com/user-attachments/assets/ecba4d63-7929-4e1d-98ec-cd5a6fc986a8" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| unit | Dropdown Option | Temperature unit | °C, °F |

### JavaScript Code
```javascript
// Temperature in Celsius
__getTemperature($('Hamster*0:temperature').d, '°C');

// Temperature in Fahrenheit
__getTemperature($('Hamster*0:temperature').d, '°F')
```

### Python Code
```python
# Temperature in Celsius
__getTemperature(__('Hamster*0:temperature').d, '°C')

# Temperature in Fahrenheit
__getTemperature(__('Hamster*0:temperature').d, '°F')
```

## Signal Strength Value
Gets the hamster’s signal strength value.

<img src="https://github.com/user-attachments/assets/21dbf029-39b5-4bc8-9cac-3b318b789ca7" width="50%" height="50%" >

### JavaScript Code
```javascript
// Signal strength value
$('Hamster*0:signal_strength').d;
```

### Python Code
```python
# Signal strength value
__('Hamster*0:signal_strength').d
```

## Battery Level Value
Gets the hamster’s battery charge level value.

<img src="https://github.com/user-attachments/assets/a577722f-3aa7-4bdd-abe3-0a3c5ace7fd6" width="60%" height="60%" >

### JavaScript Code
```javascript
// Battery level value
$('Hamster*0:battery.level').d;
```

### Python Code
```python
# Battery level value
__('Hamster*0:battery.level').d
```

## State Change Condition
Depending on the condition, returns whether the hamster’s state has changed as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/55f95297-85bf-4324-b566-e0ebc28dc51c" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| condition | Dropdown Option | Pose / detect condition | tilt forward, tilt backward, tilt left, tilt right, flipped, not flipped, detected obstacle/hand |

### JavaScript Code
```javascript
// Is hamster tilted forward?
$('Hamster*0:acceleration.x').d > 5000;

// Is hamster tilted backward?
$('Hamster*0:acceleration.x').d < -5000;

// Is hamster tilted left?
$('Hamster*0:acceleration.y').d > 5000;

// Is hamster tilted right?
$('Hamster*0:acceleration.y').d < -5000;

// Is hamster flipped?
$('Hamster*0:acceleration.z').d > 0;

// Is hamster not flipped?
$('Hamster*0:acceleration.z').d < -3000;

// Did hamster detect obstacle/hand?
$('Hamster*0:proximity.left').d > 50 || $('Hamster*0:proximity.right').d > 50;
```

### Python Code
```python
# Is hamster tilted forward?
__('Hamster*0:acceleration.x').d > 5000

# Is hamster tilted backward?
__('Hamster*0:acceleration.x').d < -5000

# Is hamster tilted left?
__('Hamster*0:acceleration.y').d > 5000

# Is hamster tilted right?
__('Hamster*0:acceleration.y').d < -5000

# Is hamster flipped over?
__('Hamster*0:acceleration.z').d > 0

# Is hamster not flipped?
__('Hamster*0:acceleration.z').d < -3000

# Did hamster detect obstacle/hand?
__('Hamster*0:proximity.left').d > 50 or __('Hamster*0:proximity.right').d > 50
```

## Set IO Port Input Mode
Sets the input mode of the hamster I/O ports.  
You can set port A, port B, or both ports A and B.

<img src="https://github.com/user-attachments/assets/77be98a8-81cc-48bc-8f27-e5a6d807cad5" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| port | Dropdown Option | I/O port selection | A, B, A and B |
| mode | Dropdown Option | Port mode | analog input, digital input, servo output, pwm output, digital output |

### JavaScript Code
```javascript
// Set hamster port A to analog input
$('Hamster*0:io.a.mode').d = 0;

// Set hamster port A to digital input
$('Hamster*0:io.a.mode').d = 1;

// Set hamster port B to servo output
$('Hamster*0:io.b.mode').d = 8;

// Set hamster port B to pwm output
$('Hamster*0:io.b.mode').d = 9;

// Set hamster ports A and B to digital output
$('Hamster*0:io.a.mode').d = 10;
$('Hamster*0:io.b.mode').d = 10;
```

### Python Code
```python
# Set hamster port A to analog input
__('Hamster*0:io.a.mode').d = 0

# Set hamster port A to digital input
__('Hamster*0:io.a.mode').d = 1

# Set hamster port B to servo output
__('Hamster*0:io.b.mode').d = 8

# Set hamster port B to pwm output
__('Hamster*0:io.b.mode').d = 9

# Set hamster ports A and B to digital output
__('Hamster*0:io.a.mode').d = 10
__('Hamster*0:io.b.mode').d = 10
```

## Set IO Port Output Value
Sets the output value of the hamster I/O ports.  
You can set port A, port B, or both ports A and B.

<img src="https://github.com/user-attachments/assets/b059e52f-b64b-4cad-858e-fcb2aac6f9f3"width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| port | Dropdown Option | I/O port selection | A, B, A and B |
| output | Input Value | Output value | 0 ~ 180 |

### JavaScript Code
```javascript
// Set hamster port A output to 50
$('Hamster*0:io.a.out').d = 50;

// Set hamster port B output to 40
$('Hamster*0:io.b.out').d = 40;

// Set hamster ports A and B output to 30
$('Hamster*0:io.a.out').d = 30;
$('Hamster*0:io.b.out').d = 30;
```

### Python Code
```python
# Set hamster port A output to 50
__('Hamster*0:io.a.out').d = 50

# Set hamster port B output to 40
__('Hamster*0:io.b.out').d = 40

# Set hamster ports A and B output to 30
__('Hamster*0:io.a.out').d = 30
__('Hamster*0:io.b.out').d = 30
```

## Change IO Port Output Value
Changes the output value of the hamster I/O ports.  
The new output value becomes the current port output value plus the input value.  
The new output value is clamped to the range 0 ~ 180.  
You can set port A, port B, or both ports A and B.


<img src="https://github.com/user-attachments/assets/ea2872fd-af65-4aab-8155-f8227a50a88d" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| port | Dropdown Option | I/O port selection | A, B, A and B |
| value | Input Value | Delta value | Integer |

### JavaScript Code
```javascript
// Change hamster port A output by +10
$('Hamster*0:io.a.out').d = $('Hamster*0:io.a.out').d + 10;

// Change hamster port B output by +20
$('Hamster*0:io.b.out').d = $('Hamster*0:io.b.out').d + 20;

// Change hamster ports A and B output by +30
$('Hamster*0:io.a.out').d = $('Hamster*0:io.a.out').d + 30;
$('Hamster*0:io.b.out').d = $('Hamster*0:io.b.out').d + 30;
```

### Python Code
```python
# Change hamster port A output by +10
__('Hamster*0:io.a.out').d = __('Hamster*0:io.a.out').d + 10

# Change hamster port B output by +20
__('Hamster*0:io.b.out').d = __('Hamster*0:io.b.out').d + 20

# Change hamster ports A and B output by +30
__('Hamster*0:io.a.out').d = __('Hamster*0:io.a.out').d + 30
__('Hamster*0:io.b.out').d = __('Hamster*0:io.b.out').d + 30
```

## Open / Close Gripper
Opens or closes the hamster’s gripper.

<img src="https://github.com/user-attachments/assets/049abd76-978f-460b-824a-f4c78935fc6a" width="50%" height="50%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Gripper toggle | open(1), close(2) |

### JavaScript Code
```javascript
// Open hamster gripper
$('Hamster*0:io.gripper').d = 1;

// Close hamster gripper
$('Hamster*0:io.gripper').d = 2;
```

### Python Code
```python
# Open hamster gripper
__('Hamster*0:io.gripper').d = 1

# Close hamster gripper
__('Hamster*0:io.gripper').d = 2
```

## Set Shooter Angle
Controls the hamster by setting the shooter angle.  
Angle range is 0 ~ 255.

<img src="https://github.com/user-attachments/assets/a3162807-6a75-47f3-acee-ec8745befb6c" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| angle | Input Value | Shooter angle | Integer 0 ~ 255 |

### JavaScript Code
```javascript
// Set hamster shooter angle to 255
$('Hamster*0:io.shooter').d = 255;

// Set hamster shooter angle to 0
$('Hamster*0:io.shooter').d = 0;
```

### Python Code
```python
# Set hamster shooter angle to 255
__('Hamster*0:io.shooter').d = 255

# Set hamster shooter angle to 0
__('Hamster*0:io.shooter').d = 0
```

## IO Port Input Value
Gets the hamster I/O port input value.

<img src="https://github.com/user-attachments/assets/ad069e47-a7b4-4e3c-aa23-5cbb0ac6f540" width="50%" height="50%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| port | Dropdown Option | I/O port | A, B |

### JavaScript Code
```javascript
// Hamster port A input value
$('Hamster*0:io.a.in').d;

// Hamster port B input value
$('Hamster*0:io.b.in').d;
```

### Python Code
```python
# Hamster port A input value
__('Hamster*0:io.a.in').d

# Hamster port B input value
__('Hamster*0:io.b.in').d
```