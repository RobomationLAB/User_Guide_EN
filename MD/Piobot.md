# Blocks
## Set Wheel Speed
Sets the PioBot’s wheel speed.  
If the wheel speed is positive, the wheel rotates forward, and if the wheel speed is negative, the wheel rotates backward.  
For example, if the wheel speed is 100, it rotates forward at a speed of 100,  
and if the wheel speed is -100, it rotates backward at a speed of 100.  
Once the wheel speed is set, the Piobot will keep moving at that speed until you set the wheel speed again.

<img src="https://github.com/user-attachments/assets/b591b7d1-6b9f-4ce4-aab3-f747c2af4bc3" width="90%" height="90%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type | left, right, both |
| velocity | Input | Wheel speed | Integer -100 ~ 100, 0: Stop | 

### JavaScript Code
```javascript
// Set left wheel speed to 50
if($('Pio*0:wheel.move').d != 0) {
    $('Pio*0:wheel.move').d = 0;
}
$('Pio*0:wheel.speed.left').d = __getSpeed('Pio*0', 50);

// Set right wheel speed to -50
if($('Pio*0:wheel.move').d != 0) {
    $('Pio*0:wheel.move').d = 0;
}
$('Pio*0:wheel.speed.right').d = __getSpeed('Pio*0', -50);

// Set both wheel speeds to 0
if($('Pio*0:wheel.move').d != 0) {
    $('Pio*0:wheel.move').d = 0;
}
$('Pio*0:wheel.speed.left').d = __getSpeed('Pio*0', 0);
$('Pio*0:wheel.speed.right').d = __getSpeed('Pio*0', 0);
```

### Python Code
```python
# Set left wheel speed to 50
if __('Pio*0:wheel.move').d != 0:
    __('Pio*0:wheel.move').d = 0
__('Pio*0:wheel.speed.left').d = __getSpeed('Pio*0', 50)

# Set right wheel speed to -50
if __('Pio*0:wheel.move').d != 0:
    __('Pio*0:wheel.move').d = 0
__('Pio*0:wheel.speed.right').d = __getSpeed('Pio*0', -50)

# Set both wheel speeds to 0
if __('Pio*0:wheel.move').d != 0:
    __('Pio*0:wheel.move').d = 0
__('Pio*0:wheel.speed.left').d = __getSpeed('Pio*0', 0)
__('Pio*0:wheel.speed.right').d = __getSpeed('Pio*0', 0)
```

## Move by Distance
Sets the distance for the Piobot to move.  
If the wheel speed is not set, it will not move.  
If the distance value is 0, it will keep moving without stopping at the currently set wheel speed.  
If wait is checked, it waits until the movement is completed.  
However, if wait is checked, it can only be used inside an async function.


<img src="https://github.com/user-attachments/assets/806af8c5-1f3e-4c6a-b157-3e0fc6e1d152" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| distance | Input | Distance value | Real number ≥ 0 |
| unit | Dropdown Option | Distance unit | cm, mm, inch | 

### JavaScript Code
```javascript
// Move 50 cm | Wait O
$('Pio*0:wheel.move').d = __getDistance('Pio*0', 50, 'cm'); // (robot, distance, unit)
await $('Pio*0:wheel.!move').w();

// Move 50 mm | Wait X
$('Pio*0:wheel.move').d = __getDistance('Pio*0', 50, 'mm'); // (robot, distance, unit)

// Move 50 inch | Wait X
$('Pio*0:wheel.move').d = __getDistance('Pio*0', 50, 'inch'); // (robot, distance, unit)
```

### Python Code
```python
# Move 50 cm | Wait O
__('Pio*0:wheel.move').d = __getDistance('Pio*0', 50, 'cm') # (robot, distance, unit)
await __('Pio*0:wheel.!move').w()

# Move 50 mm | Wait X
__('Pio*0:wheel.move').d = __getDistance('Pio*0', 50, 'mm') # (robot, distance, unit)

# Move 50 inch | Wait X
__('Pio*0:wheel.move').d = __getDistance('Pio*0', 50, 'inch') # (robot, distance, unit)
```

## Move by Time
Sets the time for the Piobot to move.  
If the wheel speed is not set, it will not move.  
If wait is checked, it waits until the movement is completed.  
However, if wait is checked, it can only be used inside an async function.  


<img src="https://github.com/user-attachments/assets/c831a4ab-a7ed-48a8-8994-91244bae1ee8" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| time | Input | Time value | Real number ≥ 0 |
| unit | Dropdown Option | Time unit | seconds, milliseconds | 

If the option is set to milliseconds, the entered value is the time value divided by 1000.

### JavaScript Code
```javascript
// Move for 5 seconds | Wait O
await __stopAfterDelay('Pio*0', 5, true); // (robot, time, wait_w)

// Move for 5 milliseconds | Wait X
__stopAfterDelay('Pio*0', 0.005, false); // (robot, time, wait_w)
```

### Python Code
```python
# Move for 5 seconds | Wait O
await __stopAfterDelay('Pio*0', 5, True) # (robot, time, wait_w)

# Move for 5 milliseconds | Wait X
__stopAfterDelay('Pio*0', 0.005, False) # (robot, time, wait_w)
```

## Turn in Place
Sets the direction and angle for the Piobot to rotate in place.  
If wait is checked, it waits until the movement is completed.  
However, if wait is checked, it can only be used inside an async function.  


<img src="https://github.com/user-attachments/assets/586c63dc-ad58-4c97-9954-304ee022a6b8" width="90%" height="90%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Turn direction | left, right |
| angle | Input | Turn angle | Integer ≥ 0 |

### JavaScript Code
```javascript
// Turn in place 90 degrees to the left | Wait O
await __turn_degree_left('Pio*0', 90, true); // (robot, degree, wait_w)

// Turn in place 90 degrees to the right | Wait X
__turn_degree_right('Pio*0', 90, false); // (robot, degree, wait_w)
```

### Python Code
```python
# Turn in place 90 degrees to the left | Wait O
await __turn_degree_left('Pio*0', 90, True) # (robot, degree, wait_w)

# Turn in place 90 degrees to the right | Wait X
__turn_degree_right('Pio*0', 90, False) # (robot, degree, wait_w)
```

## Change Wheel Speed
Changes the PioBot’s wheel speed.  
The new wheel speed is the current wheel speed plus the entered value.  
The range of the newly set wheel speed is clamped to -100 ~ 100.


<img src="https://github.com/user-attachments/assets/57c8937b-b10f-4260-907a-065b07b84fb7" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type | left, right, both |
| velocity | Input | Value to add to the current wheel speed | Integer -200 ~ 200, 0: Stop | 

### JavaScript Code
```javascript
// Change left wheel speed by 50
if($('Pio*0:wheel.move').d != 0) {
    $('Pio*0:wheel.move').d = 0;
}
$('Pio*0:wheel.speed.left').d = $('Pio*0:wheel.speed.left').d + __getSpeed('Pio*0', 50); // (robot, value)

// Change right wheel speed by 50
if($('Pio*0:wheel.move').d != 0) {
    $('Pio*0:wheel.move').d = 0;
}
$('Pio*0:wheel.speed.right').d = $('Pio*0:wheel.speed.right').d + __getSpeed('Pio*0', 50); // (robot, value)

// Change both wheel speeds by 50
if($('Pio*0:wheel.move').d != 0) {
    $('Pio*0:wheel.move').d = 0;
}
$('Pio*0:wheel.speed.left').d = $('Pio*0:wheel.speed.left').d + __getSpeed('Pio*0', 50); // (robot, value)
$('Pio*0:wheel.speed.right').d = $('Pio*0:wheel.speed.right').d + __getSpeed('Pio*0', 50); // (robot, value)
```

### Python Code
```python
# Change left wheel speed by 50
if __('Pio*0:wheel.move').d != 0:
    __('Pio*0:wheel.move').d = 0
__('Pio*0:wheel.speed.left').d = __('Pio*0:wheel.speed.left').d + __getSpeed('Pio*0', 50) # (robot, value)

# Change right wheel speed by 50
if __('Pio*0:wheel.move').d != 0:
    __('Pio*0:wheel.move').d = 0
__('Pio*0:wheel.speed.right').d = __('Pio*0:wheel.speed.right').d + __getSpeed('Pio*0', 50) # (robot, value)

# Change both wheel speeds by 50
if __('Pio*0:wheel.move').d != 0:
    __('Pio*0:wheel.move').d = 0
__('Pio*0:wheel.speed.left').d = __('Pio*0:wheel.speed.left').d + __getSpeed('Pio*0', 50) # (robot, value)
__('Pio*0:wheel.speed.right').d = __('Pio*0:wheel.speed.right').d + __getSpeed('Pio*0', 50) # (robot, value)
```

## Turn Turbo Mode On / Off
Turns the PioBot’s turbo mode on or off.


<img src="https://github.com/user-attachments/assets/9a8d7bae-8ad2-4cfe-8678-215475da9453" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown Option|Turbo toggle|On (true), Off (false)|

### JavaScript Code
```javascript
// Turn turbo mode on
__turbo('Pio*0', true);

// Turn turbo mode off
__turbo('Pio*0', false);
```

### Python Code
```python
# Turn turbo mode on
__turbo('Pio*0', True)

# Turn turbo mode off
__turbo('Pio*0', False)
```

## Stop
Stops the PioBot’s movement.  
Both wheel speeds are reset to 0.


<img src="https://github.com/user-attachments/assets/796c849a-7034-4cff-8a34-5bab3a42edba" width="35%" height="35%" >

### JavaScript Code
```javascript
// Stop Piobot
__stopMove('Pio*0');
```

### Python Code
```python
# Stop Piobot
__stopMove('Pio*0')
```

## Are the Wheels Moving?
Returns whether the PioBot’s wheels are moving as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/62564e71-2806-4c7e-a4fc-24e3d663a5e4" width="80%" height="80%" >

### JavaScript Code
```javascript
$('Pio*0:wheel.moving').d;
```

### Python Code
```python
__('Pio*0:wheel.moving').d
```

## Move One Tile Forward on the Board
Moves the Piobot one tile on the board.  
If wait is checked, it waits until the movement is completed.  
However, if wait is checked, it can only be used inside an async function.  


<img src="https://github.com/user-attachments/assets/9235c1d9-2a24-4820-918a-efe0299b3933" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Move direction | forward, backward, left, right |

### JavaScript Code
```javascript
// Move one tile forward on the board | Wait O
await __grid_move_forward('Pio*0', true); // (robot, wait_w)

// Move one tile backward on the board | Wait O
await __grid_move_backward('Pio*0', true); // (robot, wait_w)

// Move one tile left on the board | Wait X
__grid_move_left('Pio*0', false); // (robot, wait_w)

// Move one tile right on the board | Wait X
__grid_move_right('Pio*0', false); // (robot, wait_w)
```

### Python Code
```python
# Move one tile forward on the board | Wait O
await __grid_move_forward('Pio*0', True) # (robot, wait_w)

# Move one tile backward on the board | Wait O
await __grid_move_backward('Pio*0', True) # (robot, wait_w)

# Move one tile left on the board | Wait X
__grid_move_left('Pio*0', False) # (robot, wait_w)

# Move one tile right on the board | Wait X
__grid_move_right('Pio*0', False) # (robot, wait_w)
```

## Turn Once on the Board
Rotates the Piobot on the board by 90 degrees in the specified direction.  
If wait is checked, it waits until the movement is completed.  
However, if wait is checked, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/20255e83-ac1a-47e9-89d6-3861160952f8" width="90%" height="90%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Turn direction | left, right |

### JavaScript Code
```javascript
// Turn once to the left on the board | Wait O
await __grid_turn_left('Pio*0', true); // (robot, wait_w)

// Turn once to the right on the board | Wait X
__grid_turn_right('Pio*0', false); // (robot, wait_w)
```

### Python Code
```python
# Turn once to the left on the board | Wait O
await __grid_turn_left('Pio*0', True) # (robot, wait_w)

# Turn once to the right on the board | Wait X
__grid_turn_right('Pio*0', False) # (robot, wait_w)
```

## Set Neck Rotation Speed
Sets the rotation speed of the PioBot’s neck.  
The neck speed range is 1 ~ 6.


<img src="https://github.com/user-attachments/assets/172f805c-7956-4204-99d9-87a251292089" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|speed|Input|Neck rotation speed|Real number 1 ~ 6|

### JavaScript Code
```javascript
// Set Piobot neck rotation speed to 4
$('Pio*0:neck.speed').d = 4;
```

### Python Code
```python
# Set Piobot neck rotation speed to 4
__('Pio*0:neck.speed').d = 4
```

## Set Neck Angle
Sets the target angle for the PioBot’s neck rotation.  
The neck angle range is -45 ~ 45 degrees.


<img src="https://github.com/user-attachments/assets/da0c50d0-3280-43bb-bf49-27ea1c2f9514" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|angle|Input|Neck angle|Real number -45 ~ 45|

### JavaScript Code
```javascript
// Change Piobot neck angle to 10 degrees | Wait O
$('Pio*0:neck.angle').d = 10;
await $('Pio*0:neck.!angle').w();

// Change Piobot neck angle to -10 degrees | Wait X
$('Pio*0:neck.angle').d = -10;
```

### Python Code
```python
# Change Piobot neck angle to 10 degrees | Wait O
__('Pio*0:neck.angle').d = 10
await __('Pio*0:neck.!angle').w()

# Change Piobot neck angle to -10 degrees | Wait X
__('Pio*0:neck.angle').d = -10
```

## Is the Neck Moving?
Returns whether the PioBot’s neck is moving as **True (1) / False (0)**.


<img src="https://github.com/user-attachments/assets/c244c04c-db30-4642-a0ee-58d0e0a7bd1c" width="80%" height="80%" >

### JavaScript Code
```javascript
$('Pio*0:neck.moving').d;
```

### Python Code
```python
__('Pio*0:neck.moving').d
```

## Set Eye LED Color
Changes the PioBot’s eye LED color.  
You can change the eye LED color for the left, right, or both eyes.


<img src="https://github.com/user-attachments/assets/8dc1327e-c96e-4c5d-ae5c-4b46172fd5b5" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Eye direction | left, right, both |
| color | Dropdown Option | Color | black ([0, 0, 0]), red ([255, 0, 0]), yellow ([255, 255, 0]), green ([0, 255, 0])<br>cyan ([0, 255, 255]), blue ([0, 0, 255]), magenta ([255, 0, 255]), white ([255, 255, 255]) |

### JavaScript Code
```javascript
// Set Piobot left eye to black
$('Pio*0:eye.left.rgb').d = [0, 0, 0];

// Set Piobot right eye to red
$('Pio*0:eye.right.rgb').d = [255, 0, 0];

// Set both Piobot eyes to yellow
$('Pio*0:eye.left.rgb').d = [255, 255, 0];
$('Pio*0:eye.right.rgb').d = [255, 255, 0];
```

### Python Code
```python
# Set Piobot left eye to black
__('Pio*0:eye.left.rgb').d = [0, 0, 0]

# Set Piobot right eye to red
__('Pio*0:eye.right.rgb').d = [255, 0, 0]

# Set both Piobot eyes to yellow
__('Pio*0:eye.left.rgb').d = [255, 255, 0]
__('Pio*0:eye.right.rgb').d = [255, 255, 0]
```

## Set Eye LED Color Using the Color Category Block
Sets the PioBot’s eye LED color using a color category block.  
You can change the eye LED color for the left, right, or both eyes.


<img src="https://github.com/user-attachments/assets/265965e9-fa74-4bce-917f-b503cd527d07" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Applied LED direction | left, right, both |
| color | Input | Eye LED color | RGB array | 

### JavaScript Code
```javascript
// Set Piobot left eye to red
$('Pio*0:eye.left.rgb').d = [255, 0, 0];

// Set Piobot right eye to R:255, G:255, B:255
$('Pio*0:eye.right.rgb').d = [255, 255, 255];

// Set both Piobot eyes to a random color
$('Pio*0:eye.left.rgb').d = __randomColor();
$('Pio*0:eye.right.rgb').d = __randomColor();
```

### Python Code
```python
# Set Piobot left eye to red
__('Pio*0:eye.left.rgb').d = [255, 0, 0]

# Set Piobot right eye to R:255, G:255, B:255
__('Pio*0:eye.right.rgb').d = [255, 255, 255]

# Set both Piobot eyes to a random color
__('Pio*0:eye.left.rgb').d = __randomColor()
__('Pio*0:eye.right.rgb').d = __randomColor()
```

## Change Eye LED Color by the Specified RGB Amount
Changes the PioBot’s eye LED color by the specified R, G, B values.  
You can set the left, right, or both eye colors.


<img src="https://github.com/user-attachments/assets/2de2eae2-c400-45a7-9af6-545b5dddb2cc" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Applied LED direction | left, right, both |
| color | Input | Delta R, G, B values | Integers for each of R, G, B: -255 ~ 255 | 

### JavaScript Code
```javascript
// Change Piobot left eye by R: 1, G: 2, B: 3
$('Pio*0:eye.left.rgb').d = [$('Pio*0:eye.left.rgb').d[0] + 1, $('Pio*0:eye.left.rgb').d[1] + 2, $('Pio*0:eye.left.rgb').d[2] + 3];

// Change Piobot right eye by R: -1, G: -2, B: -3
$('Pio*0:eye.right.rgb').d = [$('Pio*0:eye.right.rgb').d[0] + -1, $('Pio*0:eye.right.rgb').d[1] + -2, $('Pio*0:eye.right.rgb').d[2] + -3];

// Change both Piobot eyes by R: 10, G: 20, B: 30
$('Pio*0:eye.left.rgb').d = [$('Pio*0:eye.left.rgb').d[0] + 10, $('Pio*0:eye.left.rgb').d[1] + 20, $('Pio*0:eye.left.rgb').d[2] + 30];
$('Pio*0:eye.right.rgb').d = [$('Pio*0:eye.right.rgb').d[0] + 10, $('Pio*0:eye.right.rgb').d[1] + 20, $('Pio*0:eye.right.rgb').d[2] + 30];
```

### Python Code
```python
# Change Piobot left eye by R: 1, G: 2, B: 3
__('Pio*0:eye.left.rgb').d = [__('Pio*0:eye.left.rgb').d[0] + 1, __('Pio*0:eye.left.rgb').d[1] + 2, __('Pio*0:eye.left.rgb').d[2] + 3]

# Change Piobot right eye by R: -1, G: -2, B: -3
__('Pio*0:eye.right.rgb').d = [__('Pio*0:eye.right.rgb').d[0] + -1, __('Pio*0:eye.right.rgb').d[1] + -2, __('Pio*0:eye.right.rgb').d[2] + -3]

# Change both Piobot eyes by R: 10, G: 20, B: 30
__('Pio*0:eye.left.rgb').d = [__('Pio*0:eye.left.rgb').d[0] + 10, __('Pio*0:eye.left.rgb').d[1] + 20, __('Pio*0:eye.left.rgb').d[2] + 30]
__('Pio*0:eye.right.rgb').d = [__('Pio*0:eye.right.rgb').d[0] + 10, __('Pio*0:eye.right.rgb').d[1] + 20, __('Pio*0:eye.right.rgb').d[2] + 30]
```

## Change Eye Pattern
Changes the PioBot’s eye pattern.  
You can choose a pattern and set the initial eye colors for each eye when the pattern starts.  
However, if you select the rainbow eye pattern, the eye color can only be chosen from Default, Yellow, Cyan, or Magenta.


<img src="https://github.com/user-attachments/assets/cf8ab672-bea7-491e-9d15-09e8f3ed4b65" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|pattern|Dropdown Option|Eye pattern|reset (0), blink (1), dimming (2), rainbow (3)|
|color|Dropdown Option|Left/Right eye LED color|Red (1), Yellow (2), Green (3), Cyan (4), Blue (5), Magenta (6), White (7) |

### JavaScript Code
```javascript
// Set Piobot eye pattern to Blink | Left eye: Red, Right eye: Yellow
$('Pio*0:eye.pattern.mode').d = 1;
$('Pio*0:eye.pattern.parameter').d = [1,0,0,2,0,0];

// Set Piobot eye pattern to Dimming | Left eye: Green, Right eye: Blue
$('Pio*0:eye.pattern.mode').d = 2;
$('Pio*0:eye.pattern.parameter').d = [3,0,0,5,0,0];

// Set Piobot eye pattern to Rainbow | Left eye: Cyan, Right eye: Magenta
$('Pio*0:eye.pattern.mode').d = 3;
$('Pio*0:eye.pattern.parameter').d = [3,0,0,5,0,0];
```

### Python Code
```python
# Set Piobot eye pattern to Blink | Left eye: Red, Right eye: Yellow
__('Pio*0:eye.pattern.mode').d = 1
__('Pio*0:eye.pattern.parameter').d = [1,0,0,2,0,0]

# Set Piobot eye pattern to Dimming | Left eye: Green, Right eye: Blue
__('Pio*0:eye.pattern.mode').d = 2
__('Pio*0:eye.pattern.parameter').d = [3,0,0,5,0,0]

# Set Piobot eye pattern to Rainbow | Left eye: Cyan, Right eye: Magenta
__('Pio*0:eye.pattern.mode').d = 3
__('Pio*0:eye.pattern.parameter').d = [3,0,0,5,0,0]
```

## Turn Off LED
Turns off the PioBot’s eye LED colors.  
You can turn off the left, right, or both eye LED colors.

<img src="https://github.com/user-attachments/assets/4bc3d309-3fbb-4cd4-abf2-c2aa087656fb" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Applied LED direction | left, right, both |

### JavaScript Code
```javascript
// Turn off Piobot left eye
$('Pio*0:eye.left.rgb').d = [0, 0, 0];

// Turn off Piobot right eye
$('Pio*0:eye.right.rgb').d = [0, 0, 0];

// Turn off both Piobot eyes
$('Pio*0:eye.left.rgb').d = [0, 0, 0];
$('Pio*0:eye.right.rgb').d = [0, 0, 0];
```

### Python Code
```python
# Turn off Piobot left eye
__('Pio*0:eye.left.rgb').d = [0, 0, 0]

# Turn off Piobot right eye
__('Pio*0:eye.right.rgb').d = [0, 0, 0]

# Turn off both Piobot eyes
__('Pio*0:eye.left.rgb').d = [0, 0, 0]
__('Pio*0:eye.right.rgb').d = [0, 0, 0]
```

## Set Buzzer Sound
Sets the PioBot’s buzzer to the specified frequency.  
The frequency range is 10 ~ 4200 Hz.

<img src="https://github.com/user-attachments/assets/f75bc190-3efb-4433-b3c7-d0d793e6dec4" width="100%" height="100%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| sound | Input | Buzzer frequency | 10 ~ 4200 (Hz) |

### JavaScript Code
```javascript
// Set buzzer frequency to 4200Hz
__stopSound('Pio*0');
$('Pio*0:sound.buzz').d = 4200;
```

### Python Code
```python
# Set buzzer frequency to 4200Hz
__stopSound('Pio*0')
__('Pio*0:sound.buzz').d = 4200
```

## Play a Note
Plays the specified musical note on the Piobot.


<img src="https://github.com/user-attachments/assets/284fb646-d84a-4dad-ad2c-99a50ea6cf22" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| note | Dropdown Option | Note | Do, Do#, Re, Re#, Mi, Fa, Fa#, So, So#, La, La#, Si |
| octave | Dropdown Option | Octave | 1 ~ 7 |

### JavaScript Code
```javascript
// Play Do in octave 1
__stopSound('Pio*0');
$('Pio*0:sound.note').d = 4;

// Play Re in octave 1
__stopSound('Pio*0');
$('Pio*0:sound.note').d = 6;

// Play Do in octave 2
__stopSound('Pio*0');
$('Pio*0:sound.note').d = 16;

// Play Si in octave 7
__stopSound('Pio*0');
$('Pio*0:sound.note').d = 87;
```

### Python Code
```python
# Play Do in octave 1
__stopSound('Pio*0')
__('Pio*0:sound.note').d = 4

# Play Re in octave 1
__stopSound('Pio*0')
__('Pio*0:sound.note').d = 6

# Play Do in octave 2
__stopSound('Pio*0')
__('Pio*0:sound.note').d = 16

# Play Si in octave 7
__stopSound('Pio*0')
__('Pio*0:sound.note').d = 87
```

## Play Sound Clip
Plays a specific sound clip on the Piobot.  
If wait is checked, it waits until playback is completed.  
However, if wait is checked, it can only be used inside an async function.

<img src="https://github.com/user-attachments/assets/e158987b-b61c-4c9f-aac1-beef48657745" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| sound_clip | Dropdown Option | Sound clip | beep(1), beep2(2), beep3(3), beep_repeat(4), beep_random(5), beep_random_repeat(6), snore(7), snore_repeat(8), siren(9), siren_repeat(10), engine(11), engine_repeat(12), fart_a(13), fart_b(14), noise(15), noise_repeat(16), whistle(17), chop(18), chop_repeat(19), melody(20), robot_r2d2(21), connect(22), happy(81) |

### JavaScript Code
```javascript
// Play beep (1) | Wait O
__stopSound('Pio*0');
$('Pio*0:sound.clip').d = 1;
await $('Pio*0:sound.!clip').w();

// Play happy (81) | Wait X
__stopSound('Pio*0');
$('Pio*0:sound.clip').d = 81;
```

### Python Code
```python
# Play beep (1) | Wait O
__stopSound('Pio*0')
__('Pio*0:sound.clip').d = 1
await __('Pio*0:sound.!clip').w()

# Play happy (81) | Wait X
__stopSound('Pio*0')
__('Pio*0:sound.clip').d = 81
```

## Play a Melody
Plays a specific melody on the Piobot.  
If wait is checked, it waits until playback is completed.  
However, if wait is checked, it can only be used inside an async function.

<img src="https://github.com/user-attachments/assets/7653788f-4433-4f82-8784-7b0185abd8cc" width="90%" height="90%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| melody | Dropdown Option | Melody | happy(1), angry(2), sad(3), sleep(4), march(5), birthday(6), dee_bee(7), finish(8), toy_poop(9), toy_bath(10), toy_sad(11), toy_happy(12), toy_angry(13), toy_sleep(14) |

### JavaScript Code
```javascript
// Play toy_happy (12) melody | Wait O
__stopSound('Pio*0');
$('Pio*0:sound.melody').d = 12;
await $('Pio*0:sound.!melody').w();

// Play sleep (4) melody | Wait X
__stopSound('Pio*0');
$('Pio*0:sound.melody').d = 4;
```

### Python Code
```python
# Play toy_happy (12) melody | Wait O
__stopSound('Pio*0')
__('Pio*0:sound.melody').d = 12
await __('Pio*0:sound.!melody').w()

# Play sleep (4) melody | Wait X
__stopSound('Pio*0')
__('Pio*0:sound.melody').d = 4
```

## Turn Off Sound
Turns off the PioBot’s sound.


<img src="https://github.com/user-attachments/assets/d29e899f-805e-4e05-a7f1-6df19f6b14c4" width="30%" height="30%" >

### JavaScript Code
```javascript
// Turn off Piobot sound
__stopSound('Pio*0');
```

### Python Code
```python
# Turn off Piobot sound
__stopSound('Pio*0')
```

## Is Sound Playing?
Returns whether the PioBot’s sound is currently playing as **True (1) / False (0)**.


<img src="https://github.com/user-attachments/assets/824c0d4a-d54c-4960-84bd-234232afe630" width="70%" height="70%" >

### JavaScript Code
```javascript
// Is Piobot sound playing? - true if playing, false otherwise
$('Pio*0:sound.playing').d;
```

### Python Code
```python
# Is Piobot sound playing? - True if playing, False otherwise
__('Pio*0:sound.playing').d
```

## Wheel Speed Value
Gets the set wheel speed value of the Piobot.


<img src="https://github.com/user-attachments/assets/38353872-79cc-4211-ac81-70459108baaa" width="50%" height="50%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | Left (left), Right (right) |

### JavaScript Code
```javascript
// Left wheel speed
__getSpeedInput('Pio*0', $('Pio*0:wheel.speed.left').d);

// Right wheel speed
__getSpeedInput('Pio*0', $('Pio*0:wheel.speed.right').d);
```

### Python Code
```python
# Left wheel speed
__getSpeedInput('Pio*0', __('Pio*0:wheel.speed.left').d)

# Right wheel speed
__getSpeedInput('Pio*0', __('Pio*0:wheel.speed.right').d)
```

## Signal Strength Value
Gets the PioBot’s signal strength value.

<img src="https://github.com/user-attachments/assets/951cf383-c33a-4968-a68b-8b8e035c4b94" width="40%" height="40%" >

### JavaScript Code
```javascript
// Signal strength value
$('Pio*0:signal_strength').d;
```

### Python Code
```python
# Signal strength value
__('Pio*0:signal_strength').d
```

## Battery Level Value
Gets the PioBot’s battery level value.


<img src="https://github.com/user-attachments/assets/593d1335-e8f2-47d3-8ee8-a81ae83f6301" width="40%" height="40%" >

### JavaScript Code
```javascript
// Battery level value
$('Pio*0:battery.level').d;
```

### Python Code
```python
# Battery level value
__('Pio*0:battery.level').d
```

## Was the Last Pressed Button ~ ?
Returns **True (1) / False (0)** depending on the button the user pressed most recently.


<img src="https://github.com/user-attachments/assets/0b287e67-35fd-4e23-9c3c-164459189071" width="90%" height="90%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|condition|Dropdown Option|Last pressed button|move forward (2), move backward (4), move left (8), move right (16), play (1), action (32), repeat (64), delete (128)|

### JavaScript Code
```javascript
// Did the user press the Piobot move forward (2) button?
$('Pio*0:keypad').e && $('Pio*0:keypad').d == 2

// Did the user press the Piobot move backward (4) button?
$('Pio*0:keypad').e && $('Pio*0:keypad').d == 4

// Did the user press the Piobot move left (8) button?
$('Pio*0:keypad').e && $('Pio*0:keypad').d == 8

// Did the user press the Piobot move right (16) button?
$('Pio*0:keypad').e && $('Pio*0:keypad').d == 16

// Did the user press the Piobot run (1) button?
$('Pio*0:keypad').e && $('Pio*0:keypad').d == 1

// Did the user press the Piobot act (32) button?
$('Pio*0:keypad').e && $('Pio*0:keypad').d == 32

// Did the user press the Piobot repeat (64) button?
$('Pio*0:keypad').e && $('Pio*0:keypad').d == 64

// Did the user press the Piobot delete (128) button?
$('Pio*0:keypad').e && $('Pio*0:keypad').d == 128
```

### Python Code
```python
# Did the user press the Piobot move forward (2) button?
__('Pio*0:keypad').e and __('Pio*0:keypad').d == 2

# Did the user press the Piobot move backward (4) button?
__('Pio*0:keypad').e and __('Pio*0:keypad').d == 4

# Did the user press the Piobot move left (8) button?
__('Pio*0:keypad').e and __('Pio*0:keypad').d == 8

# Did the user press the Piobot move right (16) button?
__('Pio*0:keypad').e and __('Pio*0:keypad').d == 16

# Did the user press the Piobot run (1) button?
__('Pio*0:keypad').e and __('Pio*0:keypad').d == 1

# Did the user press the Piobot act (32) button?
__('Pio*0:keypad').e and __('Pio*0:keypad').d == 32

# Did the user press the Piobot repeat (64) button?
__('Pio*0:keypad').e and __('Pio*0:keypad').d == 64

# Did the user press the Piobot delete (128) button?
__('Pio*0:keypad').e and __('Pio*0:keypad').d == 128
```