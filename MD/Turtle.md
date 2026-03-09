# Blocks
## Set Wheel Speed
Sets the turtle’s wheel speed.  
If the wheel speed is positive, it rotates forward, and if the wheel speed is negative, it rotates backward.  
For example, if the wheel speed is 100, it rotates forward at speed 100,  
and if the wheel speed is -100, it rotates backward at speed 100.  
Once you set the wheel speed, the turtle will keep moving at that speed until you set the wheel speed again.

<img src="https://github.com/user-attachments/assets/91e7d7a5-5441-427d-b51b-f8ed37a66a5e" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type | left, right, both |
| speed | Input Value | Wheel speed | Integer -100 ~ 100, 0: stop | 
 
### JavaScript Code
```javascript
// Set left wheel speed to 50
if($('Turtle*0:wheel.move').d != 0) {
    $('Turtle*0:wheel.move').d = 0;
}
$('Turtle*0:wheel.speed.left').d = __getSpeed('Turtle*0', 50);

// Set right wheel speed to 40
if($('Turtle*0:wheel.move').d != 0) {
    $('Turtle*0:wheel.move').d = 0;
}
$('Turtle*0:wheel.speed.right').d = __getSpeed('Turtle*0', 40);

// Set both wheel speeds to 30
if($('Turtle*0:wheel.move').d != 0) {
    $('Turtle*0:wheel.move').d = 0;
}
$('Turtle*0:wheel.speed.left').d = __getSpeed('Turtle*0', 30);
$('Turtle*0:wheel.speed.right').d = __getSpeed('Turtle*0', 30);
```

### Python Code
```python
# Set left wheel speed to 50
if __('Turtle*0:wheel.move').d != 0:
    __('Turtle*0:wheel.move').d = 0
__('Turtle*0:wheel.speed.left').d = __getSpeed('Turtle*0', 50)

# Set right wheel speed to 40
if __('Turtle*0:wheel.move').d != 0:
    __('Turtle*0:wheel.move').d = 0
__('Turtle*0:wheel.speed.right').d = __getSpeed('Turtle*0', 40)

# Set both wheel speeds to 30
if __('Turtle*0:wheel.move').d != 0:
    __('Turtle*0:wheel.move').d = 0
__('Turtle*0:wheel.speed.left').d = __getSpeed('Turtle*0', 30)
__('Turtle*0:wheel.speed.right').d = __getSpeed('Turtle*0', 30)
```

## Move by Distance
Sets the distance the turtle will move.  
If wheel speed is not set, it will not move.  
If the distance value is 0, it will keep moving without stopping at the currently set wheel speed.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.

<img src="https://github.com/user-attachments/assets/84933df7-1be9-4dcd-b50f-4047444cc404" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| distance | Input Value | Distance value | Real number ≥ 0 |
| unit | Dropdown Option | Distance unit | cm, mm, inch | 

### JavaScript Code
```javascript
// Move 50cm | Wait O
$('Turtle*0:wheel.move').d = __getDistance('Turtle*0', 50, 'cm');
await $('Turtle*0:wheel.!move').w();

// Move 50mm | Wait X
$('Turtle*0:wheel.move').d = __getDistance('Turtle*0', 50, 'mm');

// Move 50inch | Wait X
$('Turtle*0:wheel.move').d = __getDistance('Turtle*0', 50, 'inch');
```

### Python Code
```python
# Move 50cm | Wait O
__('Turtle*0:wheel.move').d = __getDistance('Turtle*0', 50, 'cm')
await __('Turtle*0:wheel.!move').w()

# Move 50mm | Wait X
__('Turtle*0:wheel.move').d = __getDistance('Turtle*0', 50, 'mm')

# Move 50inch | Wait X
__('Turtle*0:wheel.move').d = __getDistance('Turtle*0', 50, 'inch')
```

## Move by Time
Sets the time the turtle will move.  
If wheel speed is not set, it will not move.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/2a4622e6-1629-49da-aa4b-50b28bede2b1"  width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| time | Input Value | Time value | Real number ≥ 0 |
| unit | Dropdown Option | Time unit | seconds, milliseconds | 

If you set the option to milliseconds, the input will be the value of time divided by 1000.

### JavaScript Code
```javascript
// Move 5 seconds | Wait O
await __stopAfterDelay('Turtle*0', 5, true);

// Move 5 milliseconds | Wait X
__stopAfterDelay('Turtle*0', 0.005, false);
```

### Python Code
```python
# Move 5 seconds | Wait O
await __stopAfterDelay('Turtle*0', 5, True)

# Move 5 milliseconds | Wait X
__stopAfterDelay('Turtle*0', 0.005, False)
```

## Turn in Place
Sets the direction and degree for the turtle to rotate in place.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/e54a2f3a-03eb-40cb-8d23-d1d4305240cf" width="100%" height="100%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Turn direction | left, right |
| degree | Input Value | Turn degree | Integer ≥ 0 | 

### JavaScript Code
```javascript
// Turn left 90 degrees in place | Wait O
await __turn_degree_left('Turtle*0', 90, true);

// Turn right 270 degrees in place | Wait X
__turn_degree_right('Turtle*0', 270, false);
```

### Python Code
```python
# Turn left 90 degrees in place | Wait O
await __turn_degree_left('Turtle*0', 90, True)

# Turn right 270 degrees in place | Wait X
__turn_degree_right('Turtle*0', 270, False)
```

## Change Wheel Speed
Changes the turtle’s wheel speed.  
The new wheel speed becomes the current wheel speed plus the input value.  
The new wheel speed is clamped to the range -100 ~ 100.

<img src="https://github.com/user-attachments/assets/3b57dd09-2aab-4ff8-b180-49a50c305196" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type | left, right, left & right |
| speed | Input Value | Value to add to current speed | Integer -200 ~ 200 | 
 
### JavaScript Code
```javascript
// Change left wheel speed by +50
if($('Turtle*0:wheel.move').d != 0) {
    $('Turtle*0:wheel.move').d = 0;
}
$('Turtle*0:wheel.speed.left').d = $('Turtle*0:wheel.speed.left').d + __getSpeed('Turtle*0', 50);

// Change right wheel speed by -40
if($('Turtle*0:wheel.move').d != 0) {
    $('Turtle*0:wheel.move').d = 0;
}
$('Turtle*0:wheel.speed.right').d = $('Turtle*0:wheel.speed.right').d + __getSpeed('Turtle*0', (-40));

// Change both wheel speeds by +200
if($('Turtle*0:wheel.move').d != 0) {
    $('Turtle*0:wheel.move').d = 0;
}
$('Turtle*0:wheel.speed.left').d = $('Turtle*0:wheel.speed.left').d + __getSpeed('Turtle*0', 200);
$('Turtle*0:wheel.speed.right').d = $('Turtle*0:wheel.speed.right').d + __getSpeed('Turtle*0', 200);
```

### Python Code
```python
# Change left wheel speed by +50
if __('Turtle*0:wheel.move').d != 0:
    __('Turtle*0:wheel.move').d = 0
__('Turtle*0:wheel.speed.left').d = __('Turtle*0:wheel.speed.left').d + __getSpeed('Turtle*0', 50)

# Change right wheel speed by -40
if __('Turtle*0:wheel.move').d != 0:
    __('Turtle*0:wheel.move').d = 0
__('Turtle*0:wheel.speed.right').d = __('Turtle*0:wheel.speed.right').d + __getSpeed('Turtle*0', (-40))

# Change both wheel speeds by +200
if __('Turtle*0:wheel.move').d != 0:
    __('Turtle*0:wheel.move').d = 0
__('Turtle*0:wheel.speed.left').d = __('Turtle*0:wheel.speed.left').d + __getSpeed('Turtle*0', 200)
__('Turtle*0:wheel.speed.right').d = __('Turtle*0:wheel.speed.right').d + __getSpeed('Turtle*0', 200)
```

## Stop
Stops the turtle’s movement.  
Both wheel speeds are reset to 0.

<img src="https://github.com/user-attachments/assets/8b197263-df3a-4715-9274-da6bef483ae5" width="35%" height="35%" >

### JavaScript Code
```javascript
__stopMove('Turtle*0');
```

### Python Code
```python
__stopMove('Turtle*0')
```

## Are the Wheels Moving?
Returns whether the turtle’s wheels are moving as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/49dea5c0-b4bb-4f5e-8e52-8d55f3ee303a" width="65%" height="65%" >


### JavaScript Code
```javascript
$('Turtle*0:wheel.speed.left').d !== 0 || $('Turtle*0:wheel.speed.right').d !== 0
```

### Python Code
```python
__('Turtle*0:wheel.speed.left').d != 0 or __('Turtle*0:wheel.speed.right').d != 0
```

## Pivot Turn (Rotate Around a Wheel)

Sets the pivot wheel, direction, and angle for the turtle to rotate in place.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/ebb82203-690e-47dd-8c34-48cad94cde0d" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| pivot | Dropdown Option | Pivot wheel | left wheel, right wheel |
| direction | Dropdown Option | Direction | forward, backward |
| degree | Input Value | Rotation angle | Integer ≥ 0 | 

### JavaScript Code
```javascript
// Pivot on left wheel, forward, 90 degrees | Wait O
await __pivot('Turtle*0', 'left wheel', 'forward', 90, true);

// Pivot on left wheel, backward, 90 degrees | Wait X
__pivot('Turtle*0', 'left wheel', 'backward', 90, false);

// Pivot on right wheel, forward, 90 degrees | Wait O
await __pivot('Turtle*0', 'right wheel', 'forward', 90, true);

// Pivot on right wheel, backward, 90 degrees | Wait X
__pivot('Turtle*0', 'right wheel', 'backward', 90, false);
```

### Python Code
```python
# Pivot on left wheel, forward, 90 degrees | Wait O
await __pivot('Turtle*0', 'left wheel', 'forward', 90, True)

# Pivot on left wheel, backward, 90 degrees | Wait X
__pivot('Turtle*0', 'left wheel', 'backward', 90, False)

# Pivot on right wheel, forward, 90 degrees | Wait O
await __pivot('Turtle*0', 'right wheel', 'forward', 90, True)

# Pivot on right wheel, backward, 90 degrees | Wait X
__pivot('Turtle*0', 'right wheel', 'backward', 90, False)
```

## Draw a Circle While Turning

Sets the direction, radius, and angle when drawing a circle using the pen.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/da4b832f-4d23-41ef-89ce-8e9cacbd7070" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left forward, left backward, right forward, right backward |
| radius | Input Value | Circle radius | Real number ≥ 0 |
| unit | Dropdown Option | Distance unit | cm, mm, inch |
| degree | Input Value | Rotation angle | Real number ≥ 0 |

### JavaScript Code
```javascript
// Turn left forward, draw a circle with radius 1cm, rotate 90 degrees | Wait O
await __pivot_circle('Turtle*0', '', 'left forward', __getDistance('Turtle*0', 1, 'cm'), 90, true); //(robot, pivot, direction, radius, degree, wait_w)

// Turn left backward, draw a circle with radius 1mm, rotate 90 degrees | Wait O
await __pivot_circle('Turtle*0', '', 'left backward', __getDistance('Turtle*0', 1, 'mm'), 90, true); //(robot, pivot, direction, radius, degree, wait_w)

// Turn right forward, draw a circle with radius 1inch, rotate 90 degrees | Wait X
__pivot_circle('Turtle*0', '', 'right forward', __getDistance('Turtle*0', 1, 'inch'), 90, false); //(robot, pivot, direction, radius, degree, wait_w)

// Turn right backward, draw a circle with radius 1cm, rotate 90 degrees | Wait X
__pivot_circle('Turtle*0', '', 'right backward', __getDistance('Turtle*0', 1, 'cm'), 90, false); //(robot, pivot, direction, radius, degree, wait_w)
```

### Python Code
```python
# Turn left forward, draw a circle with radius 1cm, rotate 90 degrees | Wait O
await __pivot_circle('Turtle*0', '', 'left forward', __getDistance('Turtle*0', 1, 'cm'), 90, True) #(robot, pivot, direction, radius, degree, wait_w)

# Turn left backward, draw a circle with radius 1mm, rotate 90 degrees | Wait O
await __pivot_circle('Turtle*0', '', 'left backward', __getDistance('Turtle*0', 1, 'mm'), 90, True) #(robot, pivot, direction, radius, degree, wait_w)


# Turn right forward, draw a circle with radius 1inch, rotate 90 degrees | Wait X
__pivot_circle('Turtle*0', '', 'right forward', __getDistance('Turtle*0', 1, 'inch'), 90, False) #(robot, pivot, direction, radius, degree, wait_w)


# Turn right backward, draw a circle with radius 1cm, rotate 90 degrees | Wait X
__pivot_circle('Turtle*0', '', 'right backward', __getDistance('Turtle*0', 1, 'cm'), 90, False) #(robot, pivot, direction, radius, degree, wait_w)
```

## Follow a Line Using Sensor

The turtle follows a specific line using the bottom color sensor.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/59baee79-5b38-4455-8472-586ef9a7ae2f" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Line color | black(8), red(9), green(11), blue(13), any(15) |

### JavaScript Code
```javascript
// Follow a black line (8) | Wait O
$('Turtle*0:trace.mode').d = 8;
await $('Turtle*0:trace.!mode').w();

// Follow a red line (9) | Wait O
$('Turtle*0:trace.mode').d = 9;
await $('Turtle*0:trace.!mode').w();

// Follow a green line (11) | Wait O
$('Turtle*0:trace.mode').d = 11;
await $('Turtle*0:trace.!mode').w();

// Follow a blue line (13) | Wait X
$('Turtle*0:trace.mode').d = 13;

// Follow any line (15) | Wait X
$('Turtle*0:trace.mode').d = 15;
```

### Python Code
```python
# Follow a black line (8) | Wait O
__('Turtle*0:trace.mode').d = 8
await __('Turtle*0:trace.!mode').w()

# Follow a red line (9) | Wait O
__('Turtle*0:trace.mode').d = 9
await __('Turtle*0:trace.!mode').w()

# Follow a green line (11) | Wait O
__('Turtle*0:trace.mode').d = 11
await __('Turtle*0:trace.!mode').w()

# Follow a blue line (13) | Wait X
__('Turtle*0:trace.mode').d = 13

# Follow any line (15) | Wait X
__('Turtle*0:trace.mode').d = 15
```

## Follow Black Line Until a Specific Color
Using the bottom color sensor, the turtle follows a black line until it encounters the specified color.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/078fad38-2f79-46ca-bc79-cc0dcf1232a3" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Target color | red(49), green(51), cyan(52), blue(53), magenta(54), any(55) |

### JavaScript Code
```javascript
// Follow black line until red (49) | Wait O
$('Turtle*0:trace.mode').d = 49;
await $('Turtle*0:trace.!mode').w();

// Follow black line until green (51) | Wait O
$('Turtle*0:trace.mode').d = 51;
await $('Turtle*0:trace.!mode').w();

// Follow black line until cyan (52) | Wait O
$('Turtle*0:trace.mode').d = 52;
await $('Turtle*0:trace.!mode').w();

// Follow black line until blue (53) | Wait X
$('Turtle*0:trace.mode').d = 53;

// Follow black line until magenta (54) | Wait X
$('Turtle*0:trace.mode').d = 54;

// Follow black line until any color (55) | Wait X
$('Turtle*0:trace.mode').d = 55;
```

### Python Code
```python
# Follow black line until red (49) | Wait O
__('Turtle*0:trace.mode').d = 49
await __('Turtle*0:trace.!mode').w()

# Follow black line until green (51) | Wait O
__('Turtle*0:trace.mode').d = 51
await __('Turtle*0:trace.!mode').w()

# Follow black line until cyan (52) | Wait O
__('Turtle*0:trace.mode').d = 52
await __('Turtle*0:trace.!mode').w()

# Follow black line until blue (53) | Wait X
__('Turtle*0:trace.mode').d = 53

# Follow black line until magenta (54) | Wait X
__('Turtle*0:trace.mode').d = 54

# Follow black line until any color (55) | Wait X
__('Turtle*0:trace.mode').d = 55
```

## Follow a Specific Color Line Until Black
Using the bottom color sensor, the turtle follows a specific color line until it encounters black.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/528288fd-7513-4a08-995f-2eec21e117c0" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Line color | red(57), green(59), blue(61), any(63) |

### JavaScript Code
```javascript
// Follow red line until black (57) | Wait O
$('Turtle*0:trace.mode').d = 57;
await $('Turtle*0:trace.!mode').w();

// Follow green line until black (59) | Wait O
$('Turtle*0:trace.mode').d = 59;
await $('Turtle*0:trace.!mode').w();

// Follow blue line until black (61) | Wait X
$('Turtle*0:trace.mode').d = 61;

// Follow any color line until black (63) | Wait X
$('Turtle*0:trace.mode').d = 63;
```

### Python Code
```python
# Follow red line until black (57) | Wait O
__('Turtle*0:trace.mode').d = 57
await __('Turtle*0:trace.!mode').w()

# Follow green line until black (59) | Wait O
__('Turtle*0:trace.mode').d = 59
await __('Turtle*0:trace.!mode').w()

# Follow blue line until black (61) | Wait X
__('Turtle*0:trace.mode').d = 61

# Follow any color line until black (63) | Wait X
__('Turtle*0:trace.mode').d = 63
```

## Behavior at a Black Intersection
Using the bottom color sensor, when the turtle detects a black intersection it performs the specified behavior.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/5c6fc05b-20ca-48ef-8811-901a278d2922" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| behavior | Dropdown Option | Action at black intersection | move forward(16), turn left(24), turn right(32), u-turn(40) |

### JavaScript Code
```javascript
// At black intersection: move forward (16) | Wait O
$('Turtle*0:trace.mode').d = 16;
await $('Turtle*0:trace.!mode').w();

// At black intersection: turn left (24) | Wait O
$('Turtle*0:trace.mode').d = 24;
await $('Turtle*0:trace.!mode').w();

// At black intersection: turn right (32) | Wait X
$('Turtle*0:trace.mode').d = 32;

// At black intersection: u-turn (40) | Wait X
$('Turtle*0:trace.mode').d = 40;
```

### Python Code
```python
# At black intersection: move forward (16) | Wait O
__('Turtle*0:trace.mode').d = 16
await __('Turtle*0:trace.!mode').w()

# At black intersection: turn left (24) | Wait O
__('Turtle*0:trace.mode').d = 24
await __('Turtle*0:trace.!mode').w()

# At black intersection: turn right (32) | Wait X
__('Turtle*0:trace.mode').d = 32

# At black intersection: u-turn (40) | Wait X
__('Turtle*0:trace.mode').d = 40
```

## Set Line Tracing Speed
Sets the turtle’s line tracing speed.  
Speed range is 1 ~ 10.

<img src="https://github.com/user-attachments/assets/555467d7-f881-4c70-9a9a-ce14649f8e31" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| speed | Input Value | line tracing speed | Integer 1 ~ 10 | 

### JavaScript Code
```javascript
// Set line tracing speed to 5
$('Turtle*0:trace.speed').d = 5;
```

### Python Code
```python
# Set line tracing speed to 5
__('Turtle*0:trace.speed').d = 5
```

## Set Line Tracing Gain
Sets the direction change amount (gain) for line tracing.  
Gain range is 1 ~ 10.

<img src="https://github.com/user-attachments/assets/b82d28b9-1034-424a-b185-40a751b33aed" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| gain | Input Value | line tracing gain | Integer 1 ~ 10 | 

### JavaScript Code
```javascript
$('Turtle*0:trace.gain').d = 5; // Set direction gain to 5
```

### Python Code
```python
__('Turtle*0:trace.gain').d = 5 # Set direction gain to 5
```

## Stop Line Tracing
Stops the turtle’s line tracing feature.


<img src="https://github.com/user-attachments/assets/a2bd4f11-1c2d-49af-8499-1d32670dbfb2" width="70%" height="70%" >


### JavaScript Code
```javascript
$('Turtle*0:trace.mode').d = 0; // Stop line tracing
```

### Python Code
```python
__('Turtle*0:trace.mode').d = 0 # Stop line tracing
```

## Set LED Color
Sets the turtle’s head LED color.

<img src="https://github.com/user-attachments/assets/7083b3e3-b1b7-47e0-95bd-339022249828" width="60%" height="60%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Color | black([0, 0, 0]), red([255, 0, 0]), yellow([255, 255, 0]), green([0, 255, 0])<br>cyan([0, 255, 255]), blue([0, 0, 255]), magenta([255, 0, 255]), white([255, 255, 255]) | 

### JavaScript Code
```javascript
// Set head LED color to black
$('Turtle*0:head_led').d = [0, 0, 0];

// Set head LED color to red
$('Turtle*0:head_led').d = [255, 0, 0];

// Set head LED color to yellow
$('Turtle*0:head_led').d = [255, 255, 0];

// Set head LED color to green
$('Turtle*0:head_led').d = [0, 255, 0];

// Set head LED color to cyan
$('Turtle*0:head_led').d = [0, 255, 255];

// Set head LED color to blue
$('Turtle*0:head_led').d = [0, 0, 255];

// Set head LED color to magenta
$('Turtle*0:head_led').d = [255, 0, 255];

// Set head LED color to white
$('Turtle*0:head_led').d = [255, 255, 255];
```

### Python Code
```python
# Set head LED color to black
__('Turtle*0:head_led').d = [0, 0, 0]

# Set head LED color to red
__('Turtle*0:head_led').d = [255, 0, 0]

# Set head LED color to yellow
__('Turtle*0:head_led').d = [255, 255, 0]

# Set head LED color to green
__('Turtle*0:head_led').d = [0, 255, 0]

# Set head LED color to cyan
__('Turtle*0:head_led').d = [0, 255, 255]

# Set head LED color to blue
__('Turtle*0:head_led').d = [0, 0, 255]

# Set head LED color to magenta
__('Turtle*0:head_led').d = [255, 0, 255]

# Set head LED color to white
__('Turtle*0:head_led').d = [255, 255, 255]
```

## Set LED Color Using Color Category Blocks
Sets the turtle’s head LED color using blocks in the color category.

<img src="https://github.com/user-attachments/assets/311707ce-a370-4b85-b530-b8c562b03db7" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Input Value | LED color | RGB array | 

### JavaScript Code
```javascript
// Set head LED color to R:255, G:0, B:0
$('Turtle*0:head_led').d = [255, 0, 0];

// Set head LED color to R:255, G:255, B:0
$('Turtle*0:head_led').d = [255, 255, 0];

// Set head LED color to random color
$('Turtle*0:head_led').d = __randomColor();
```

### Python Code
```python
# Set head LED color to R:255, G:0, B:0
__('Turtle*0:head_led').d = [255, 0, 0]

# Set head LED color to R:255, G:255, B:0
__('Turtle*0:head_led').d = [255, 255, 0]

# Set head LED color to random color
__('Turtle*0:head_led').d = __randomColor()
```

## Change LED Color by RGB Delta
Changes the turtle’s head LED color by the specified R, G, B values.

<img src="https://github.com/user-attachments/assets/1392924d-f4ed-41ab-a109-5601a3d9ea01" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Input Value | R, G, B deltas | Each of R,G,B: Integer -255 ~ 255 | 

### JavaScript Code
```javascript
// Change head LED color by R:+1, G:+2, B:+3
$('Turtle*0:head_led').d = [$('Turtle*0:head_led').d[0] + 1, $('Turtle*0:head_led').d[1] + 2, $('Turtle*0:head_led').d[2] + 3];
```

### Python Code
```python
# Change head LED color by R:+1, G:+2, B:+3
__('Turtle*0:head_led').d = [__('Turtle*0:head_led').d[0] + 1, __('Turtle*0:head_led').d[1] + 2, __('Turtle*0:head_led').d[2] + 3]
```

## Turn Off LED
Turns off the turtle’s head LED.

<img src="https://github.com/user-attachments/assets/369738c9-e49b-4729-a5f4-035ba41cbeb7" width="60%" height="60%" >

### JavaScript Code
```javascript
// Turn off head LED
$('Turtle*0:head_led').d = [0, 0, 0];
```

### Python Code
```python
# Turn off head LED
__('Turtle*0:head_led').d = [0, 0, 0]
```

## Set Buzzer Frequency
Sets the turtle’s buzzer sound to the specified frequency.  
Frequency range is 10 ~ 4200Hz.


<img src="https://github.com/user-attachments/assets/95d6eb62-3ae7-441f-be73-a3b626af1e9a" width="60%" height="60%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| sound | Input Value | Buzzer frequency | 10 ~ 4200 (Hz) |

### JavaScript Code
```javascript
// Set buzzer frequency to 4200Hz
$('Turtle*0:sound.buzz').d = 4200;
```

### Python Code
```python
# Set buzzer frequency to 4200Hz
__('Turtle*0:sound.buzz').d = 4200
```

## Play a Note
Plays the specified musical note.


<img src="https://github.com/user-attachments/assets/49640b49-e3b2-4f42-9c84-8aa1facf4d1d" width="60%" height="60%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| note | Dropdown Option | Note | Do, Do#, Re, Re#, Mi, Fa, Fa#, So, So#, La, La#, Si |
| octave | Dropdown Option | Octave | 1 ~ 7 |

### JavaScript Code
```javascript
// Play octave 1 Do
$('Turtle*0:sound.note').d = 4;

// Play octave 1 Re
$('Turtle*0:sound.note').d = 6;

// Play octave 2 Do
$('Turtle*0:sound.note').d = 16;

// Play octave 7 Si
$('Turtle*0:sound.note').d = 87;
```

### Python Code
```python
# Play octave 1 Do
__('Turtle*0:sound.note').d = 4

# Play octave 1 Re
__('Turtle*0:sound.note').d = 6

# Play octave 2 Do
__('Turtle*0:sound.note').d = 16

# Play octave 7 Si
__('Turtle*0:sound.note').d = 87
```

## Play a Sound Clip
Plays a specific sound clip.  
If you check “wait”, it waits until playback completes.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/65357749-1446-4509-9447-7c1a04801391" width="100%" height="100%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| sound_clip | Dropdown Option | Sound clip | beep(1), beep2(2), beep3(3), beep_repeat(4), beep_random(5), beep2_random(6), beep3_random(7), beep_random_repeat(8), siren(16), siren_repeat(17), engine(32), engine_repeat(33), noise_random(34), r2d2(48), toy_march(64), birthday(65), dibidibidip(66), mission_complete(67) |

### JavaScript Code
```javascript
// Play dibidibidip(66) | Wait O
$('Turtle*0:sound.clip').d = 66;
await $('Turtle*0:sound.!clip').w();

// Play mission_complete(67) | Wait X
$('Turtle*0:sound.clip').d = 67;
```

### Python Code
```python
# Play dibidibidip(66) | Wait O
__('Turtle*0:sound.clip').d = 66
await __('Turtle*0:sound.!clip').w()

# Play mission_complete(67) | Wait X
__('Turtle*0:sound.clip').d = 67
```

## Stop Sound
Turns off the turtle’s sound.

<img src="https://github.com/user-attachments/assets/23caec83-596e-4add-8028-81760f2a9b9f" width="40%" height="40%" >

### JavaScript Code
```javascript
// Stop turtle sound
__stopSound('Turtle*0');
```

### Python Code
```python
# Stop turtle sound
__stopSound('Turtle*0')
```

## Is Sound Playing?
Returns whether the turtle’s sound is playing as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/4d4e5f38-4dd7-4625-98e4-4467efcf1e2b"width="70%" height="70%" >

### JavaScript Code
```javascript
// Is turtle sound playing? - true if playing, false otherwise
$('Turtle*0:sound.playing').d;
```

### Python Code
```python
# Is turtle sound playing? - True if playing, False otherwise
__('Turtle*0:sound.playing').d
```

## Wheel Speed Value
Gets the specified wheel speed value.


<img src="https://github.com/user-attachments/assets/2109d634-19f9-42d2-91a3-77b721e41ecc" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left, right |

### JavaScript Code
```javascript
// Left wheel speed
__getSpeedInput('Turtle*0', $('Turtle*0:wheel.speed.left').d);

// Right wheel speed
__getSpeedInput('Turtle*0', $('Turtle*0:wheel.speed.right').d);
```

### Python Code
```python
# Left wheel speed
__getSpeedInput('Turtle*0', __('Turtle*0:wheel.speed.left').d)

# Right wheel speed
__getSpeedInput('Turtle*0', __('Turtle*0:wheel.speed.right').d)
```

## Color Sensor Value
Gets the turtle’s color sensor value.


<img src="https://github.com/user-attachments/assets/d7b05fd2-c6d3-488f-823f-6f70fdf78fd3" width="40%" height="40%" >

### JavaScript Code
```javascript
// Color sensor value
$('Turtle*0:line').d;
```

### Python Code
```python
# Color sensor value
__('Turtle*0:line').d
```

## Card Color Number Value
Returns the card color number read by the bottom color sensor.

<img src="https://github.com/user-attachments/assets/62d969fa-85ad-4224-93d6-8e1e767043ba" width="50%" height="50%" >

### JavaScript Code
```javascript
// Read card color number value
$('Turtle*0:color.name').d;
```

### Python Code
```python
# Read card color number value
__('Turtle*0:color.name').d
```

## Card Color Pattern Value
Returns the pattern of the card color read by the bottom color sensor.

<img src="https://github.com/user-attachments/assets/3212aa33-25fa-4e5d-8f49-215b86c7b19c" width="60%" height="60%" >

### JavaScript Code
```javascript
// Card color pattern value
$('Turtle*0:card').d;
```

### Python Code
```python
# Card color pattern value
__('Turtle*0:card').d
```

## Acceleration Value
Gets the acceleration value for a specific axis.

<img src="https://github.com/user-attachments/assets/54c50fc0-2c12-47d5-9adb-529db683ba52" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| axis | Dropdown Option | Axis | x, y, z |

### JavaScript Code
```javascript
// Acceleration value on x-axis
$('Turtle*0:acceleration.x').d;

// Acceleration value on y-axis
$('Turtle*0:acceleration.y').d;

// Acceleration value on z-axis
$('Turtle*0:acceleration.z').d;
```

### Python Code
```python
# Acceleration value on x-axis
__('Turtle*0:acceleration.x').d

# Acceleration value on y-axis
__('Turtle*0:acceleration.y').d

# Acceleration value on z-axis
__('Turtle*0:acceleration.z').d
```

## Temperature Sensor Value
Gets the turtle’s temperature sensor value.

<img src="https://github.com/user-attachments/assets/cecc17db-d2e0-41e0-9148-17bda5d9ed3d" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| unit | Dropdown Option | Temperature unit | °C, °F |

### JavaScript Code
```javascript
// Temperature in Celsius
__getTemperature($('Turtle*0:temperature').d, '°C');

// Temperature in Fahrenheit
__getTemperature($('Turtle*0:temperature').d, '°F');
```

### Python Code
```python
# Temperature in Celsius
__getTemperature(__('Turtle*0:temperature').d, '°C')

# Temperature in Fahrenheit
__getTemperature(__('Turtle*0:temperature').d, '°F')
```

## Signal Strength Value
Gets the turtle’s signal strength value.

<img src="https://github.com/user-attachments/assets/326c7ac2-5f96-49c0-b4f6-9ccdf0ea9f1c" width="60%" height="60%" >

### JavaScript Code
```javascript
// Signal strength value
$('Turtle*0:signal_strength').d;
```

### Python Code
```python
# Signal strength value
__('Turtle*0:signal_strength').d
```

## Battery Level Value
Gets the turtle’s battery charge level value.

<img src="https://github.com/user-attachments/assets/9274b4cf-b057-4658-ad06-baf06d668953" width="50%" height="50%" >

### JavaScript Code
```javascript
// Battery level value
$('Turtle*0:battery').d;
```

### Python Code
```python
# Battery level value
__('Turtle*0:battery').d
```

## Is Touching a Specific Color?
Using the turtle’s color sensor, returns whether it is touching the specified color as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/20eca365-6a21-4cd6-a7ed-03603730ff7c" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Detected color | red(1), yellow(2), green(3), cyan(4), blue(5), magenta(6), white(7) |

### JavaScript Code
```javascript
// Touching red?
$('Turtle*0:color.name').d === 1;

// Touching yellow?
$('Turtle*0:color.name').d === 2;

// Touching green?
$('Turtle*0:color.name').d === 3;

// Touching cyan?
$('Turtle*0:color.name').d === 4;

// Touching blue?
$('Turtle*0:color.name').d === 5;

// Touching magenta?
$('Turtle*0:color.name').d === 6;

// Touching white?
$('Turtle*0:color.name').d === 7;
```

### Python Code
```python
# Touching red?
__('Turtle*0:color.name').d == 1

# Touching yellow?
__('Turtle*0:color.name').d == 2

# Touching green?
__('Turtle*0:color.name').d == 3

# Touching cyan?
__('Turtle*0:color.name').d == 4

# Touching blue?
__('Turtle*0:color.name').d == 5

# Touching magenta?
__('Turtle*0:color.name').d == 6

# Touching white?
__('Turtle*0:color.name').d == 7
```

## Is the Card Color Pattern ~ ?
Depending on whether the detected card color pattern matches, returns **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/0f326b1d-afdb-4bdd-bb56-9dfd0389093f" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| pattern 1 | Dropdown Option | Card color pattern | red, yellow, green, cyan, blue, magenta |
| pattern 2 | Dropdown Option | Card color pattern | red, yellow, green, cyan, blue, magenta |

### JavaScript Code
```javascript
// Is card pattern red-red?
$('Turtle*0:card').d === 9;

// Is card pattern red-yellow?
$('Turtle*0:card').d === 10;

// Is card pattern red-green?
$('Turtle*0:card').d === 11;

// Is card pattern red-cyan?
$('Turtle*0:card').d === 12;

// Is card pattern red-blue?
$('Turtle*0:card').d === 13;

// Is card pattern red-magenta?
$('Turtle*0:card').d === 14;

// Is card pattern yellow-red?
$('Turtle*0:card').d === 17;

// Is card pattern green-red?
$('Turtle*0:card').d === 25;

// Is card pattern cyan-red?
$('Turtle*0:card').d === 33;

// Is card pattern blue-red?
$('Turtle*0:card').d === 41;

// Is card pattern magenta-red?
$('Turtle*0:card').d === 49;

// Is card pattern magenta-magenta?
$('Turtle*0:card').d === 54;
```

### Python Code
```python
# Is card pattern red-red?
__('Turtle*0:card').d == 9

# Is card pattern red-yellow?
__('Turtle*0:card').d == 10

# Is card pattern red-green?
__('Turtle*0:card').d == 11

# Is card pattern red-cyan?
__('Turtle*0:card').d == 12

# Is card pattern red-blue?
__('Turtle*0:card').d == 13

# Is card pattern red-magenta?
__('Turtle*0:card').d == 14

# Is card pattern yellow-red?
__('Turtle*0:card').d == 17

# Is card pattern green-red?
__('Turtle*0:card').d == 25

# Is card pattern cyan-red?
__('Turtle*0:card').d == 33

# Is card pattern blue-red?
__('Turtle*0:card').d == 41

# Is card pattern magenta-red?
__('Turtle*0:card').d == 49

# Is card pattern magenta-magenta?
__('Turtle*0:card').d == 54
```

## Was the Back Button Clicked?
Depending on back button click status, returns **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/fb0ffb26-32d6-47fa-815e-aab36974e157"  width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| action | Dropdown Option | Click type | click, long_click |

### JavaScript Code
```javascript
// Was back button clicked?
$('Turtle*0:button.click').e;

// Was back button long-clicked?
$('Turtle*0:button.long_click').e;
```

### Python Code
```python
# Was back button clicked?
__('Turtle*0:button.click').e

# Was back button long-clicked?
__('Turtle*0:button.long_click').e
```

## State Change Condition
Depending on the condition, returns whether the turtle’s state has changed as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/307e2c81-5143-40d1-8d8a-ec247dfc7fd4" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| condition | Dropdown Option | Pose condition | tilted forward, tilted backward, tilted left, tilted right, flipped over, not flipped |

### JavaScript Code
```javascript
// Is turtle tilted forward?
$('Turtle*0:acceleration.x').d > 5000;

// Is turtle tilted backward?
$('Turtle*0:acceleration.x').d < -5000;

// Is turtle tilted left?
$('Turtle*0:acceleration.y').d > 5000;

// Is turtle tilted right?
$('Turtle*0:acceleration.y').d < -5000;

// Is turtle flipped over?
$('Turtle*0:acceleration.z').d > 0;

// Is turtle not flipped?
$('Turtle*0:acceleration.z').d < -3000;
```

### Python Code
```python
# Is turtle tilted forward?
__('Turtle*0:acceleration.x').d > 5000

# Is turtle tilted backward?
__('Turtle*0:acceleration.x').d < -5000

# Is turtle tilted left?
__('Turtle*0:acceleration.y').d > 5000

# Is turtle tilted right?
__('Turtle*0:acceleration.y').d < -5000

# Is turtle flipped over?
__('Turtle*0:acceleration.z').d > 0

# Is turtle not flipped?
__('Turtle*0:acceleration.z').d < -3000
```