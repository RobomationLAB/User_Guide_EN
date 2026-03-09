# Blocks
## Set Wheel Speed
Sets the Beagle’s wheel speed.  
If the wheel speed is positive, the wheel rotates forward, and if the wheel speed is negative, the wheel rotates backward.  
For example, if the wheel speed is 100, it rotates forward at a speed of 100,  
and if the wheel speed is -100, it rotates backward at a speed of 100.  
Once the wheel speed is set, the Beagle will keep moving at that speed until you set the wheel speed again.


<img src="https://github.com/user-attachments/assets/0ac1e673-36da-41fc-96aa-1c1b0daad440" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type | left, right, both |
| speed | Input | Wheel speed | Integer -100 ~ 100, 0: Stop | 

### JavaScript Code
```javascript
// Set left wheel speed to 100
if($('Beagle*0:wheel.move').d != 0) {
    $('Beagle*0:wheel.move').d = 0;
}
$('Beagle*0:wheel.speed.left').d = __getSpeed('Beagle*0', 100);

// Set right wheel speed to -100
if($('Beagle*0:wheel.move').d != 0) {
    $('Beagle*0:wheel.move').d = 0;
}
$('Beagle*0:wheel.speed.right').d = __getSpeed('Beagle*0', -100);

// Set both wheel speeds to 100
if($('Beagle*0:wheel.move').d != 0) {
    $('Beagle*0:wheel.move').d = 0;
}
$('Beagle*0:wheel.speed.left').d = __getSpeed('Beagle*0', 100);
$('Beagle*0:wheel.speed.right').d = __getSpeed('Beagle*0', 100);
```

### Python Code
```python
# Set left wheel speed to 100
if __('Beagle*0:wheel.move').d != 0:
    __('Beagle*0:wheel.move').d = 0
__('Beagle*0:wheel.speed.left').d = __getSpeed('Beagle*0', 100)

# Set right wheel speed to -100
if __('Beagle*0:wheel.move').d != 0:
    __('Beagle*0:wheel.move').d = 0
__('Beagle*0:wheel.speed.right').d = __getSpeed('Beagle*0', -100)

# Set both wheel speeds to 100
if __('Beagle*0:wheel.move').d != 0:
    __('Beagle*0:wheel.move').d = 0
__('Beagle*0:wheel.speed.left').d = __getSpeed('Beagle*0', 100)
__('Beagle*0:wheel.speed.right').d = __getSpeed('Beagle*0', 100)
```

## Move by Distance
Sets the distance for the Beagle to move.  
If the wheel speed is not set, it will not move.  
If the distance value is 0, it will keep moving without stopping at the currently set wheel speed.  
If wait is checked, it waits until the movement is completed.  
However, if wait is checked, it can only be used inside an async function.


<img src="https://github.com/user-attachments/assets/78813698-25e9-4b27-b3ec-5c7e7dab9b3b" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| distance | Input | Distance value | Real number ≥ 0 |
| unit | Dropdown Option | Distance unit | cm, mm, inch | 

### JavaScript Code
```javascript
// Move 50cm | Wait O
$('Beagle*0:wheel.move').d = __getDistance('Beagle*0', 50, 'cm');
await $('Beagle*0:wheel.!move').w();

// Move 50mm | Wait X
$('Beagle*0:wheel.move').d = __getDistance('Beagle*0', 50, 'mm');

// Move 50inch | Wait X
$('Beagle*0:wheel.move').d = __getDistance('Beagle*0', 50, 'inch');
```

### Python Code
```python
# Move 50cm | Wait O
__('Beagle*0:wheel.move').d = __getDistance('Beagle*0', 50, 'cm')
await __('Beagle*0:wheel.!move').w()

# Move 50mm | Wait X
__('Beagle*0:wheel.move').d = __getDistance('Beagle*0', 50, 'mm')

# Move 50inch | Wait X
__('Beagle*0:wheel.move').d = __getDistance('Beagle*0', 50, 'inch')
```

## Move by Time
Sets the time for the Beagle to move.  
If the wheel speed is not set, it will not move.  
If wait is checked, it waits until the movement is completed.  
However, if wait is checked, it can only be used inside an async function.

<img src="https://github.com/user-attachments/assets/28ac11c6-3a3c-4941-868a-67c6ef646d35" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| time | Input | Time value | Real number ≥ 0 |
| unit | Dropdown Option | Time unit | seconds, milliseconds | 

If the option is set to milliseconds, the entered value is the time value divided by 1000.

### JavaScript Code
```javascript
// Move for 5 seconds | Wait O
await __stopAfterDelay('Beagle*0', 5, true);

// Move for 5 milliseconds | Wait X
__stopAfterDelay('Beagle*0', 0.005, false);
```

### Python Code
```python
# Move for 5 seconds | Wait O
await __stopAfterDelay('Beagle*0', 5, True)

# Move for 5 milliseconds | Wait X
__stopAfterDelay('Beagle*0', 0.005, False)
```

## Turn in Place
Sets the direction and angle for the Beagle to rotate in place.  
If wait is checked, it waits until the movement is completed.  
However, if wait is checked, it can only be used inside an async function.


<img src="https://github.com/user-attachments/assets/d46887e3-f452-48a9-9373-d6a41d93e0ee" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Turn direction | left, right |
| degree | Input | Turn angle | Integer ≥ 0 | 

### JavaScript Code
```javascript
// Turn in place 90 degrees to the left | Wait O
await __turn_degree_left('Beagle*0', 90, true);

// Turn in place 270 degrees to the right | Wait X
__turn_degree_right('Beagle*0', 270, false);
```

### Python Code
```python
# Turn in place 90 degrees to the left | Wait O
await __turn_degree_left('Beagle*0', 90, True)

# Turn in place 270 degrees to the right | Wait X
__turn_degree_right('Beagle*0', 270, False)
```

## Change Wheel Speed
Changes the Beagle’s wheel speed.  
The new wheel speed is the current wheel speed plus the entered value.  
The range of the newly set wheel speed is clamped to -100 ~ 100.


<img src="https://github.com/user-attachments/assets/3b95099b-cf0f-4c33-af96-566b6abb699a" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type |left, right, both |
| speed | Input | Value to add to the current wheel speed | Integer -200 ~ 200 | 

### JavaScript Code
```javascript
// Change left wheel speed by 50
if($('Beagle*0:wheel.move').d != 0) {
    $('Beagle*0:wheel.move').d = 0;
}
$('Beagle*0:wheel.speed.left').d = $('Beagle*0:wheel.speed.left').d + __getSpeed('Beagle*0', 50);

// Change right wheel speed by 40
if($('Beagle*0:wheel.move').d != 0) {
    $('Beagle*0:wheel.move').d = 0;
}
$('Beagle*0:wheel.speed.right').d = $('Beagle*0:wheel.speed.right').d + __getSpeed('Beagle*0', 40);

// Change both wheel speeds by 30
if($('Beagle*0:wheel.move').d != 0) {
    $('Beagle*0:wheel.move').d = 0;
}
$('Beagle*0:wheel.speed.left').d = $('Beagle*0:wheel.speed.left').d + __getSpeed('Beagle*0', 30);
$('Beagle*0:wheel.speed.right').d = $('Beagle*0:wheel.speed.right').d + __getSpeed('Beagle*0', 30);
```

### Python Code
```python
# Change left wheel speed by 50
if __('Beagle*0:wheel.move').d != 0:
    __('Beagle*0:wheel.move').d = 0
__('Beagle*0:wheel.speed.left').d = __('Beagle*0:wheel.speed.left').d + __getSpeed('Beagle*0', 50)

# Change right wheel speed by 40
if __('Beagle*0:wheel.move').d != 0:
    __('Beagle*0:wheel.move').d = 0
__('Beagle*0:wheel.speed.right').d = __('Beagle*0:wheel.speed.right').d + __getSpeed('Beagle*0', 40)

# Change both wheel speeds by 30
if __('Beagle*0:wheel.move').d != 0:
    __('Beagle*0:wheel.move').d = 0
__('Beagle*0:wheel.speed.left').d = __('Beagle*0:wheel.speed.left').d + __getSpeed('Beagle*0', 30)
__('Beagle*0:wheel.speed.right').d = __('Beagle*0:wheel.speed.right').d + __getSpeed('Beagle*0', 30)
```

## Stop
Stops the Beagle’s movement.  
Both wheel speeds are reset to 0.


<img src="https://github.com/user-attachments/assets/e0da61fa-361a-492e-810c-a03958bd3ccb" width="35%" height="35%" >

### JavaScript Code
```javascript
__stopMove('Beagle*0');
```

### Python Code
```python
__stopMove('Beagle*0')
```

## Are the Wheels Moving?
Returns whether the Beagle’s wheels are moving as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/df3734a6-8ae9-48be-a4e9-82e6da619939" width="75%" height="75%" >


### JavaScript Code
```javascript
$('Beagle*0:wheel.speed.left').d !== 0 || $('Beagle*0:wheel.speed.right').d !== 0
```

### Python Code
```python
__('Beagle*0:wheel.speed.left').d != 0 or __('Beagle*0:wheel.speed.right').d != 0
```

## Set Buzzer Sound
Sets the Beagle’s buzzer to the specified frequency.  
The frequency range is 10 Hz to 4200 Hz.


<img src="https://github.com/user-attachments/assets/647c03a8-3a85-4eff-bede-5881d8c8ea5f" width="90%" height="90%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| sound | Input | Buzzer frequency | 10 ~ 4200 (Hz) |

### JavaScript Code
```javascript
// Set buzzer frequency to 4200Hz
__stopSound('Beagle*0');
$('Beagle*0:sound.buzz').d = 4200;
```

### Python Code
```python
# Set buzzer frequency to 4200Hz
__stopSound('Beagle*0')
__('Beagle*0:sound.buzz').d = 4200
```

## Play a Note
Plays the specified musical note on the Beagle.


<img src="https://github.com/user-attachments/assets/367537bf-7382-4847-8587-d9d3167331be" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| note | Dropdown Option | Note | Do, Do#, Re, Re#, Mi, Fa, Fa#, So, So#, La, La#, Si |
| octave | Dropdown Option | Octave | 1 ~ 7 |

### JavaScript Code
```javascript
// Play Do in octave 1
__stopSound('Beagle*0');
$('Beagle*0:sound.note').d = 4;

// Play Re in octave 1
__stopSound('Beagle*0');
$('Beagle*0:sound.note').d = 6;

// Play Do in octave 2
__stopSound('Beagle*0');
$('Beagle*0:sound.note').d = 16;

// Play Si in octave 7
__stopSound('Beagle*0');
$('Beagle*0:sound.note').d = 87;
```

### Python Code
```python
# Play Do in octave 1
__stopSound('Beagle*0')
__('Beagle*0:sound.note').d = 4

# Play Re in octave 1
__stopSound('Beagle*0')
__('Beagle*0:sound.note').d = 6

# Play Do in octave 2
__stopSound('Beagle*0')
__('Beagle*0:sound.note').d = 16

# Play Si in octave 7
__stopSound('Beagle*0')
__('Beagle*0:sound.note').d = 87
```

## Play Sound Clip
Plays a specific sound clip on the Beagle.  
If wait is checked, it waits until playback is completed.  
However, if wait is checked, it can only be used inside an async function.

<img src="https://github.com/user-attachments/assets/e81c2820-ddb9-447f-b0cf-b236d8d0cd7d" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| sound_clip | Dropdown Option | Sound clip | beep(1), beep2(2), beep3(3), beep_repeat(4), beep_random(5), beep_random_repeat(6), snore(7), snore_repeat(8), siren(9), siren_repeat(10), engine(11), engine_repeat(12), fart_a(13), fart_b(14), noise(15), noise_repeat(16), whistle(17), chop_chop(18), chop_chop_repeat(19), r2d2(32), dibidibidip(33), simple_melody(35), happy(48), angry(49), sad(50), sleep(51), march(52), birthday(53) |

### JavaScript Code
```javascript
// Play dibidibidip | Wait O
__stopSound('Beagle*0');
$('Beagle*0:sound.clip').d = 33;
await $('Beagle*0:sound.!clip').w();

// Play happy | Wait X
__stopSound('Beagle*0');
$('Beagle*0:sound.clip').d = 48;
```

### Python Code
```python
# Play dibidibidip | Wait O
__stopSound('Beagle*0')
__('Beagle*0:sound.clip').d = 33
await __('Beagle*0:sound.!clip').w()

# Play happy | Wait X
__stopSound('Beagle*0')
__('Beagle*0:sound.clip').d = 48
```

## Turn Off Sound
Turns off the Beagle’s sound.

<img src="https://github.com/user-attachments/assets/6ecd128c-1afb-4447-9e7b-370f8047d14b" width="40%" height="40%" >

### JavaScript Code
```javascript
// Turn off Beagle sound
__stopSound('Beagle*0');
```

### Python Code
```python
# Turn off Beagle sound
__stopSound('Beagle*0')
```

## Is Sound Playing?
Returns whether the Beagle’s sound is currently playing as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/0cd2a593-bd4b-402f-a29a-665723c047c1" width="80%" height="80%" >

### JavaScript Code
```javascript
// Is Beagle sound playing? - true if playing, false otherwise
$('Beagle*0:sound.playing').d;
```

### Python Code
```python
# Is Beagle sound playing? - True if playing, False otherwise
__('Beagle*0:sound.playing').d
```

## Wheel Speed Value
Gets the set wheel speed value of the Beagle.

<img src="https://github.com/user-attachments/assets/3979a2b7-45d0-4c33-82e7-0ef48cf8c87f" width="65%" height="65%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left, right |

### JavaScript Code
```javascript
// Left wheel speed
__getSpeedInput('Beagle*0', $('Beagle*0:wheel.speed.left').d);

// Right wheel speed
__getSpeedInput('Beagle*0', $('Beagle*0:wheel.speed.right').d);
```

### Python Code
```python
# Left wheel speed
__getSpeedInput('Beagle*0', __('Beagle*0:wheel.speed.left').d)

# Right wheel speed
__getSpeedInput('Beagle*0', __('Beagle*0:wheel.speed.right').d)
```

## Encoder Value
Gets the encoder value of the specified Beagle wheel.

<img src="https://github.com/user-attachments/assets/63e9b011-effe-476f-97c6-ba397697b2c4" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left, right |

### JavaScript Code
```javascript
// Left wheel encoder value
$('Beagle*0:encoder.left').d;

// Right wheel encoder value
$('Beagle*0:encoder.right').d;
```

### Python Code
```python
# Left wheel encoder value
__('Beagle*0:encoder.left').d

# Right wheel encoder value
__('Beagle*0:encoder.right').d
```

## Gyroscope Value
Gets the gyroscope sensor value on a specific axis of the Beagle.


<img src="https://github.com/user-attachments/assets/dac2ced2-f9d8-4eb4-8bd0-a1b48e98fc52" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| axis | Dropdown Option | Axis | x, y, z |

### JavaScript Code
```javascript
// Gyroscope x-axis
$('Beagle*0:gyroscope.x').d;

// Gyroscope y-axis
$('Beagle*0:gyroscope.y').d;

// Gyroscope z-axis
$('Beagle*0:gyroscope.z').d;
```

### Python Code
```python
# Gyroscope x-axis
__('Beagle*0:gyroscope.x').d

# Gyroscope y-axis
__('Beagle*0:gyroscope.y').d

# Gyroscope z-axis
__('Beagle*0:gyroscope.z').d
```

## Accelerometer Value
Gets the accelerometer sensor value on a specific axis of the Beagle.

<img src="https://github.com/user-attachments/assets/880c6bc6-d79f-42d6-bb2a-b600478a589b" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| axis | Dropdown Option | Axis | x, y, z |

### JavaScript Code
```javascript
// Accelerometer x-axis
$('Beagle*0:accelerometer.x').d;

// Accelerometer y-axis
$('Beagle*0:accelerometer.y').d;

// Accelerometer z-axis
$('Beagle*0:accelerometer.z').d;
```

### Python Code
```python
# Accelerometer x-axis
__('Beagle*0:accelerometer.x').d

# Accelerometer y-axis
__('Beagle*0:accelerometer.y').d

# Accelerometer z-axis
__('Beagle*0:accelerometer.z').d
```

## Magnetometer Value
Gets the magnetometer sensor value on a specific axis of the Beagle.


<img src="https://github.com/user-attachments/assets/36da2f86-9cf4-4d3d-b55d-d4421c578cdf" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| axis | Dropdown Option | Axis | x, y, z |

### JavaScript Code
```javascript
// Magnetometer x-axis
$('Beagle*0:magnetometer.x').d;

// Magnetometer y-axis
$('Beagle*0:magnetometer.y').d;

// Magnetometer z-axis
$('Beagle*0:magnetometer.z').d;
```

### Python Code
```python
# Magnetometer x-axis
__('Beagle*0:magnetometer.x').d

# Magnetometer y-axis
__('Beagle*0:magnetometer.y').d

# Magnetometer z-axis
__('Beagle*0:magnetometer.z').d
```

## Temperature Sensor Value
Gets the Beagle’s temperature sensor value.


<img src="https://github.com/user-attachments/assets/2e34ba59-4d24-4a99-bbc2-918e389adfb9" width="90%" height="90%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| unit | Dropdown Option | Temperature unit | °C, °F |

### JavaScript Code
```javascript
// Temperature sensor value in Celsius
__getTemperature($('Beagle*0:temperature').d, '°C');

// Temperature sensor value in Fahrenheit
__getTemperature($('Beagle*0:temperature').d, '°F');
```

### Python Code
```python
# Temperature sensor value in Celsius
__getTemperature(__('Beagle*0:temperature').d, '°C')

# Temperature sensor value in Fahrenheit
__getTemperature(__('Beagle*0:temperature').d, '°F')
```

## Signal Strength Value
Gets the Beagle’s signal strength value.


<img src="https://github.com/user-attachments/assets/aee69471-6a99-428e-becd-cd2d4b8f5f30" width="40%" height="40%" >

### JavaScript Code
```javascript
// Signal strength value
$('Beagle*0:signal_strength').d;
```

### Python Code
```python
# Signal strength value
__('Beagle*0:signal_strength').d
```

## Battery Level Value
Gets the Beagle’s battery level value.


<img src="https://github.com/user-attachments/assets/a77bab3c-3b52-4d87-8afd-364975a78592" width="40%" height="40%" >

### JavaScript Code
```javascript
// Battery level value
$('Beagle*0:battery.level').d;
```

### Python Code
```python
# Battery level value
__('Beagle*0:battery.level').d
```

## State Change Condition
Returns whether the Beagle’s state condition is met as **True (1) / False (0)**.


<img src="https://github.com/user-attachments/assets/1c4a59a7-c59f-4dd4-9828-59df40eae2a9" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|condition|Dropdown Option|Posture condition|tilt forward, tilt backward, tilt left, tilt right, Flipped, not flipped|

### JavaScript Code
```javascript
// Is the Beagle tilted forward?
$('Beagle*0:accelerometer.x').d > 0.8;

// Is the Beagle tilted backward?
$('Beagle*0:accelerometer.x').d < -0.8;

// Is the Beagle tilted to the left?
$('Beagle*0:accelerometer.y').d > 0.8;

// Is the Beagle tilted to the right?
$('Beagle*0:accelerometer.y').d < -0.8;

// Is the Beagle flipped over?
$('Beagle*0:accelerometer.z').d > 0;

// Is the Beagle not flipped over?
$('Beagle*0:accelerometer.z').d < 0;
```

### Python Code
```python
# Is the Beagle tilted forward?
__('Beagle*0:accelerometer.x').d > 0.8

# Is the Beagle tilted backward?
__('Beagle*0:accelerometer.x').d < -0.8

# Is the Beagle tilted to the left?
__('Beagle*0:accelerometer.y').d > 0.8

# Is the Beagle tilted to the right?
__('Beagle*0:accelerometer.y').d < -0.8

# Is the Beagle flipped over?
__('Beagle*0:accelerometer.z').d > 0

# Is the Beagle not flipped over?
__('Beagle*0:accelerometer.z').d < 0
```

## Set Servo Motor Speed
Sets the speed of the specified servo motor.


<img src="https://github.com/user-attachments/assets/ab7220fb-67cc-4985-8254-003731ed394c" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|motor|Dropdown Option|Servo motor|A, B, C|
|speed|Input|Speed|Real number 0 ~ 10|

### JavaScript Code
```javascript
// Set servo motor A speed to 1
$('Beagle*0:servo.a.speed').d = 1;

// Set servo motor B speed to 10
$('Beagle*0:servo.b.speed').d = 10;

// Set servo motor C speed to 5.5
$('Beagle*0:servo.c.speed').d = 5.5;
```

### Python Code
```python
# Set servo motor A speed to 1
__('Beagle*0:servo.a.speed').d = 1

# Set servo motor B speed to 10
__('Beagle*0:servo.b.speed').d = 10

# Set servo motor C speed to 5.5
__('Beagle*0:servo.c.speed').d = 5.5
```

## Set Servo Motor Angle
Sets the angle of the specified servo motor.

<img src="https://github.com/user-attachments/assets/8e070a46-a7f5-48d6-89ab-8c73bdce9b5e" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|motor|Dropdown Option|Servo motor|A, B, C|
|angle|Input|Angle|Real number 0 ~ 180|

### JavaScript Code
```javascript
// Set servo motor A angle to 0
$('Beagle*0:servo.a.angle').d = 0;

// Set servo motor B angle to 180
$('Beagle*0:servo.b.angle').d = 180;

// Set servo motor C angle to 90
$('Beagle*0:servo.c.angle').d = 90;
```

### Python Code
```python
# Set servo motor A angle to 0
__('Beagle*0:servo.a.angle').d = 0

# Set servo motor B angle to 180
__('Beagle*0:servo.b.angle').d = 180

# Set servo motor C angle to 90
__('Beagle*0:servo.c.angle').d = 90
```

## Change Servo Motor Angle
Changes the angle of the specified servo motor.  
The new servo motor angle is the current angle plus the entered value.


<img src="https://github.com/user-attachments/assets/d69188f9-af5e-46d5-b7c9-93805e9b9bf8" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|motor|Dropdown Option|Servo motor|A, B, C|
|angle|Input|Value to add to the current motor angle|Real number -180 ~ 180|

### JavaScript Code
```javascript
// Change servo motor A angle by -10
$('Beagle*0:servo.a.angle').d = $('Beagle*0:servo.a.angle').d + -10;

// Change servo motor B angle by 10
$('Beagle*0:servo.b.angle').d = $('Beagle*0:servo.b.angle').d + 10;

// Change servo motor C angle by 20
$('Beagle*0:servo.c.angle').d = $('Beagle*0:servo.c.angle').d + 20;
```

### Python Code
```python
# Change servo motor A angle by -10
__('Beagle*0:servo.a.angle').d = __('Beagle*0:servo.a.angle').d + -10

# Change servo motor B angle by 10
__('Beagle*0:servo.b.angle').d = __('Beagle*0:servo.b.angle').d + 10

# Change servo motor C angle by 20
__('Beagle*0:servo.c.angle').d = __('Beagle*0:servo.c.angle').d + 20
```

## Turn Off Servo Motor
Turns off the power of the specified servo motor.


<img src="https://github.com/user-attachments/assets/d4ca20b9-e68b-484c-96ec-7fbcc8a14d61" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|motor|Dropdown Option|Servo motor|A, B, C|

### JavaScript Code
```javascript
// Turn off servo motor A
$('Beagle*0:servo.a.angle').d = 0;

// Turn off servo motor B
$('Beagle*0:servo.b.angle').d = 0;

// Turn off servo motor C
$('Beagle*0:servo.c.angle').d = 0;
```

### Python Code
```python
# Turn off servo motor A
__('Beagle*0:servo.a.angle').d = 0

# Turn off servo motor B
__('Beagle*0:servo.b.angle').d = 0

# Turn off servo motor C
__('Beagle*0:servo.c.angle').d = 0
```

## Servo Motor Angle Value
Returns the current angle value of the specified servo motor.


<img src="https://github.com/user-attachments/assets/22fd3fdd-5fc2-4baa-b67c-41f60994adce" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|motor|Dropdown Option|Servo motor|A, B, C|

### JavaScript Code
```javascript
// Servo motor A angle
$('Beagle*0:servo.a.angle').d;

// Servo motor B angle
$('Beagle*0:servo.b.angle').d;

// Servo motor C angle
$('Beagle*0:servo.c.angle').d;
```

### Python Code
```python
# Servo motor A angle
__('Beagle*0:servo.a.angle').d

# Servo motor B angle
__('Beagle*0:servo.b.angle').d

# Servo motor C angle
__('Beagle*0:servo.c.angle').d
```

## Turn LiDAR On / Off
Enables or disables the LiDAR sensor.


<img src="https://github.com/user-attachments/assets/56b553a4-1e0c-4dbd-a056-d222295485d0" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown Option|LiDAR power|On (1), Off (0)|

### JavaScript Code
```javascript
// Turn on LiDAR sensor
$('Beagle*0:lidar+connect').d = 1;

// Turn off LiDAR sensor
$('Beagle*0:lidar+connect').d = 0;
```

### Python Code
```python
# Turn on LiDAR sensor
__('Beagle*0:lidar+connect').d = 1

# Turn off LiDAR sensor
__('Beagle*0:lidar+connect').d = 0
```

## Distance to the Nth Object (LiDAR)
Measures the distance to surrounding objects using the LiDAR sensor (mm).  
Starting with the object in front of the Beagle as number 0, numbers are assigned counterclockwise in order.  
This then returns the distance between the Beagle and the object with the specified number.


<img src="https://github.com/user-attachments/assets/d1b4c641-9646-4786-9053-0e101b80c77c" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|number|Input|Object index|Integer 0 ~ 359|

### JavaScript Code
```javascript
// Distance between LiDAR and object 0 (mm)
$('Beagle*0:lidar+array').d[0];

// Distance between LiDAR and object 1 (mm)
$('Beagle*0:lidar+array').d[1];

// Distance between LiDAR and object 359 (mm)
$('Beagle*0:lidar+array').d[359];
```

### Python Code
```python
# Distance between LiDAR and object 0 (mm)
__('Beagle*0:lidar+array').d[0]

# Distance between LiDAR and object 1 (mm)
__('Beagle*0:lidar+array').d[1]

# Distance between LiDAR and object 359 (mm)
__('Beagle*0:lidar+array').d[359]
```

## LiDAR Sensor Distance Values
Shows the distances measured by the LiDAR sensor in the front, back, sides, and diagonal directions (mm).  
It outputs the average of the distance values within ±45 degrees around the corresponding direction.

<img src="https://github.com/user-attachments/assets/988d9dbf-d91a-4c76-977e-b543558062a2" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|direction|Dropdown Option|Direction|front (0), front-left (1), left (2), back-left (3), back (4), back-right (5), right (6), front-right (7)|

### JavaScript Code
```javascript
// LiDAR front distance value (mm)
$('Beagle*0:lidar+directions').d[0];

// LiDAR front-left distance value (mm)
$('Beagle*0:lidar+directions').d[1];

// LiDAR left distance value (mm)
$('Beagle*0:lidar+directions').d[2];

// LiDAR back-left distance value (mm)
$('Beagle*0:lidar+directions').d[3];

// LiDAR back distance value (mm)
$('Beagle*0:lidar+directions').d[4];

// LiDAR back-right distance value (mm)
$('Beagle*0:lidar+directions').d[5];

// LiDAR right distance value (mm)
$('Beagle*0:lidar+directions').d[6];

// LiDAR front-right distance value (mm)
$('Beagle*0:lidar+directions').d[7];
```

### Python Code
```python
# LiDAR front distance value (mm)
__('Beagle*0:lidar+directions').d[0]

# LiDAR front-left distance value (mm)
__('Beagle*0:lidar+directions').d[1]

# LiDAR left distance value (mm)
__('Beagle*0:lidar+directions').d[2]

# LiDAR back-left distance value (mm)
__('Beagle*0:lidar+directions').d[3]

# LiDAR back distance value (mm)
__('Beagle*0:lidar+directions').d[4]

# LiDAR back-right distance value (mm)
__('Beagle*0:lidar+directions').d[5]

# LiDAR right distance value (mm)
__('Beagle*0:lidar+directions').d[6]

# LiDAR front-right distance value (mm)
__('Beagle*0:lidar+directions').d[7]
```

## Is LiDAR On?
Returns whether the LiDAR is turned on as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/5d5cebc7-286e-432c-91b2-55e095e4c317" width="50%" height="50%" >

### JavaScript Code

```javascript
// Is LiDAR on?
$('Beagle*0:lidar+ready').d;
```

### Python Code
```python
# Is LiDAR on?
__('Beagle*0:lidar+ready').d
```