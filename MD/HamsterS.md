# Blocks 
## Set Wheel Speed
Sets the wheel speed of Hamster S.  
If the wheel speed is positive, it rotates forward, and if the wheel speed is negative, it rotates backward.  
For example, if the wheel speed is 100, it rotates forward at speed 100,  
and if the wheel speed is -100, it rotates backward at speed 100.  
Once you set the wheel speed, Hamster S will keep moving at that speed until you set the wheel speed again.

<img src="https://github.com/user-attachments/assets/7b691c83-98ef-423d-a854-dcea2edc5979" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type | left, right, both |
| velocity | Input Value | Wheel speed | Integer -100 ~ 100, 0: stop | 
 
### JavaScript Code
```javascript
// Set left wheel speed to 50
if($('HamsterS*0:wheel.move').d != 0) {
    $('HamsterS*0:wheel.move').d = 0;
}
$('HamsterS*0:wheel.speed.left').d = __getSpeed('HamsterS*0', 50);

// Set right wheel speed to 50
if($('HamsterS*0:wheel.move').d != 0) {
    $('HamsterS*0:wheel.move').d = 0;
}
$('HamsterS*0:wheel.speed.right').d = __getSpeed('HamsterS*0', 50);
```

### Python Code
```python
# Set both wheel speeds to 50
if __('HamsterS*0:wheel.move').d != 0:
    __('HamsterS*0:wheel.move').d = 0
__('HamsterS*0:wheel.speed.left').d = __getSpeed('HamsterS*0', 50)
__('HamsterS*0:wheel.speed.right').d = __getSpeed('HamsterS*0', 50)
```

## Move by Distance
Sets the distance Hamster S will move.  
If wheel speed is not set, it will not move.  
If the distance value is 0, it keeps moving without stopping at the currently set wheel speed.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.


<img src="https://github.com/user-attachments/assets/cbb0e89b-5d25-45c2-96d2-f6a96502db3d" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| distance | Input Value | Distance value | Real number ≥ 0 |
| unit | Dropdown Option | Distance unit | cm, mm, inch | 

### JavaScript Code
```javascript
// Move 5 cm | Wait O
$('HamsterS*0:wheel.move').d = __getDistance('HamsterS*0', 5, 'cm');  // (robot, distance, unit)
await $('HamsterS*0:wheel.!move').w();

// Move 1000 mm | Wait X
$('HamsterS*0:wheel.move').d = __getDistance('HamsterS*0', 1000, 'mm');  // (robot, distance, unit)
```

### Python Code
```python
# Move 5 cm | Wait O
__('HamsterS*0:wheel.move').d = __getDistance('HamsterS*0', 5, 'cm')  # (robot, distance, unit)
await __('HamsterS*0:wheel.!move').w()

# Move 1000 mm | Wait X
__('HamsterS*0:wheel.move').d = __getDistance('HamsterS*0', 1000, 'mm')  # (robot, distance, unit)
```

## Move by Time
Sets the time Hamster S will move.  
If wheel speed is not set, it will not move.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  


<img src="https://github.com/user-attachments/assets/1aa72587-ddfc-43aa-a7fc-ba11d96d349e" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| time | Input Value | Time value | Real number ≥ 0 |
| unit | Dropdown Option | Time unit | seconds, milliseconds | 

If you set the option to milliseconds, the input will be the value of time divided by 1000.

### JavaScript Code
```javascript
// Move 5 seconds | Wait O
await __stopAfterDelay('HamsterS*0', 5, true);  // (robot, time, wait_w)

// Move 5000 milliseconds | Wait X
__stopAfterDelay('HamsterS*0', 5, false);  // (robot, time, wait_w)
```

### Python Code
```python
# Move 5 seconds | Wait O
await __stopAfterDelay('HamsterS*0', 5, True)  # (robot, time, wait_w)

# Move 5000 milliseconds | Wait X
__stopAfterDelay('HamsterS*0', 5, False)  # (robot, time, wait_w)
```

## Turn in Place
Sets the direction and angle for Hamster S to rotate in place.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/f622573e-5de4-45cb-bc82-66f1de7fd4d8" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Turn direction | left, right |
| degree | Input Value | Turn angle | Integer ≥ 0 | 

### JavaScript Code
```javascript
// Turn left 90 degrees | Wait O
await __turn_degree_left('HamsterS*0', 90, true);  // (robot, degree, wait_w)

// Turn right 270 degrees | Wait X
__turn_degree_right('HamsterS*0', 270, false);  // (robot, degree, wait_w)
```

### Python Code
```python
# Turn left 90 degrees | Wait O
await __turn_degree_left('HamsterS*0', 90, True)  # (robot, degree, wait_w)

# Turn right 270 degrees | Wait X
__turn_degree_right('HamsterS*0', 270, False)  # (robot, degree, wait_w)
```

## Change Wheel Speed
Changes the wheel speed of Hamster S.  
The new wheel speed becomes the current wheel speed plus the input value.  
The new wheel speed is clamped to the range -100 ~ 100.


<img src="https://github.com/user-attachments/assets/1799be48-5af0-4218-8a6a-db8b354c62f0" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| wheel | Dropdown Option | Wheel type | left, right, both |
| velocity | Input Value | Value to add to current speed | Integer -200 ~ 200, 0: stop | 
 
### JavaScript Code
```javascript
// Change left wheel speed by +50
if($('HamsterS*0:wheel.move').d != 0) {
    $('HamsterS*0:wheel.move').d = 0;
}
$('HamsterS*0:wheel.speed.left').d = $('HamsterS*0:wheel.speed.left').d + __getSpeed('HamsterS*0', 50);

// Change right wheel speed by +50
if($('HamsterS*0:wheel.move').d != 0) {
    $('HamsterS*0:wheel.move').d = 0;
}
$('HamsterS*0:wheel.speed.right').d = $('HamsterS*0:wheel.speed.right').d + __getSpeed('HamsterS*0', 50);

// Change both wheel speeds by +50
if($('HamsterS*0:wheel.move').d != 0) {
    $('HamsterS*0:wheel.move').d = 0;
}
$('HamsterS*0:wheel.speed.left').d = $('HamsterS*0:wheel.speed.left').d + __getSpeed('HamsterS*0', 50);
$('HamsterS*0:wheel.speed.right').d = $('HamsterS*0:wheel.speed.right').d + __getSpeed('HamsterS*0', 50);
```

### Python Code
```python
# Change left wheel speed by +50
if __('HamsterS*0:wheel.move').d != 0:
    __('HamsterS*0:wheel.move').d = 0
__('HamsterS*0:wheel.speed.left').d = __('HamsterS*0:wheel.speed.left').d + __getSpeed('HamsterS*0', 50)

# Change right wheel speed by +50
if __('HamsterS*0:wheel.move').d != 0:
    __('HamsterS*0:wheel.move').d = 0
__('HamsterS*0:wheel.speed.right').d = __('HamsterS*0:wheel.speed.right').d + __getSpeed('HamsterS*0', 50)

# Change both wheel speeds by +50
if __('HamsterS*0:wheel.move').d != 0:
    __('HamsterS*0:wheel.move').d = 0
__('HamsterS*0:wheel.speed.left').d = __('HamsterS*0:wheel.speed.left').d + __getSpeed('HamsterS*0', 50)
__('HamsterS*0:wheel.speed.right').d = __('HamsterS*0:wheel.speed.right').d + __getSpeed('HamsterS*0', 50)
```

## Stop
Stops Hamster S movement.  
Both wheel speeds are reset to 0.


<img src="https://github.com/user-attachments/assets/f0c4ebb3-f9fc-4db5-9166-6ca3c291dd71" width="40%" height="40%" >

### JavaScript Code
```javascript
__stopMove('HamsterS*0');
```

### Python Code
```python
__stopMove('HamsterS*0')
```

## Are the Wheels Moving?
Returns whether Hamster S wheels are moving as **True(1) / False(0)**.


<img src="https://github.com/user-attachments/assets/71183e9d-3020-4422-a381-208a237ca401" width="70%" height="70%" >

### JavaScript Code
```javascript
$('HamsterS*0:wheel.moving').d
```

### Python Code
```python
__('HamsterS*0:wheel.moving').d
```

## Move One Tile Forward on the Board
Moves Hamster S forward by one tile on the board.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  


<img src="https://github.com/user-attachments/assets/105c22d8-16b3-4227-9855-ec80a98fb727" width="70%" height="70%" >

### JavaScript Code
```javascript
// Move one tile forward | Wait O
await __grid_move_forward('HamsterS*0', true);  // (robot, wait_w)

// Move one tile forward | Wait X
__grid_move_forward('HamsterS*0', false);  // (robot, wait_w)
```

### Python Code
```python
# Move one tile forward | Wait O
await __grid_move_forward('HamsterS*0', True) # (robot, wait_w)

# Move one tile forward | Wait X
__grid_move_forward('HamsterS*0', False) # (robot, wait_w)
```

## Turn Once on the Board
Rotates Hamster S 90 degrees on the board in the given direction.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  

<img src="https://github.com/user-attachments/assets/a79e684e-751d-41b5-a064-b87f709659a4" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Turn direction | left, right |

### JavaScript Code
```javascript
// Turn left once on the board | Wait O
await __grid_turn_left('HamsterS*0', true); // (robot, wait_w)

// Turn left once on the board | Wait X
__grid_turn_left('HamsterS*0', false); // (robot, wait_w)

// Turn right once on the board | Wait O
await __grid_turn_right('HamsterS*0', true); // (robot, wait_w)

// Turn right once on the board | Wait X
__grid_turn_right('HamsterS*0', false); // (robot, wait_w)
```

### Python Code
```python
# Turn left once on the board | Wait O
await __grid_turn_left('HamsterS*0', True) # (robot, wait_w)

# Turn left once on the board | Wait X
__grid_turn_left('HamsterS*0', False) # (robot, wait_w)

# Turn right once on the board | Wait O
await __grid_turn_right('HamsterS*0', True) # (robot, wait_w)

# Turn right once on the board | Wait X
__grid_turn_right('HamsterS*0', False) # (robot, wait_w)
```

## Pivot Turn (Pen Holder Reference)
While using the pen holder, sets the pivot reference and direction/degree for Hamster S to rotate in place.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  


<img src="https://github.com/user-attachments/assets/7334b643-c637-44ea-b052-1a768fa87f4b" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| pivot | Dropdown Option | Pivot reference | left pen, right pen, left wheel, right wheel |
| direction | Dropdown Option | Direction | forward, backward |
| degree | Input Value | Rotation angle | Integer ≥ 0 |

### JavaScript Code
```javascript
// Pivot on left pen, forward, 90 degrees | Wait O
await __pivot('HamsterS*0', 'left pen', 'forward', 90, true); //(robot, pivot, direction, degree, wait_w)

// Pivot on left pen, backward, 90 degrees | Wait X
__pivot('HamsterS*0', 'left pen', 'backward', 90, false); //(robot, pivot, direction, degree, wait_w)

// Pivot on right pen, forward, 90 degrees | Wait O
await __pivot('HamsterS*0', 'right pen', 'forward', 90, true); //(robot, pivot, direction, degree, wait_w)

// Pivot on right pen, backward, 90 degrees | Wait X
__pivot('HamsterS*0', 'right pen', 'backward', 90, false); //(robot, pivot, direction, degree, wait_w)

// Pivot on left wheel, forward, 90 degrees | Wait O
await __pivot('HamsterS*0', 'left wheel', 'forward', 90, true); //(robot, pivot, direction, degree, wait_w)

// Pivot on left wheel, backward, 90 degrees | Wait X
__pivot('HamsterS*0', 'left wheel', 'backward', 90, false); //(robot, pivot, direction, degree, wait_w)

// Pivot on right wheel, forward, 90 degrees | Wait O
await __pivot('HamsterS*0', 'right wheel', 'forward', 90, true); //(robot, pivot, direction, degree, wait_w)

// Pivot on right wheel, backward, 90 degrees | Wait X
__pivot('HamsterS*0', 'right wheel', 'backward', 90, false); //(robot, pivot, direction, degree, wait_w)
```

### Python Code
```python
# Pivot on left pen, forward, 90 degrees | Wait O
await __pivot('HamsterS*0', 'left pen', 'forward', 90, True) # (robot, pivot, direction, degree, wait_w)

# Pivot on left pen, backward, 90 degrees | Wait X
__pivot('HamsterS*0', 'left pen', 'backward', 90, False) # (robot, pivot, direction, degree, wait_w)

# Pivot on right pen, forward, 90 degrees | Wait O
await __pivot('HamsterS*0', 'right pen', 'forward', 90, True) # (robot, pivot, direction, degree, wait_w)

# Pivot on right pen, backward, 90 degrees | Wait X
__pivot('HamsterS*0', 'right pen', 'backward', 90, False) # (robot, pivot, direction, degree, wait_w)

# Pivot on left wheel, forward, 90 degrees | Wait O
await __pivot('HamsterS*0', 'left wheel', 'forward', 90, True) # (robot, pivot, direction, degree, wait_w)

# Pivot on left wheel, backward, 90 degrees | Wait X
__pivot('HamsterS*0', 'left wheel', 'backward', 90, False) # (robot, pivot, direction, degree, wait_w)

# Pivot on right wheel, forward, 90 degrees | Wait O
await __pivot('HamsterS*0', 'right wheel', 'forward', 90, True) # (robot, pivot, direction, degree, wait_w)

# Pivot on right wheel, backward, 90 degrees | Wait X
__pivot('HamsterS*0', 'right wheel', 'backward', 90, False) # (robot, pivot, direction, degree, wait_w)
```

## Pivot Circle (Draw a Circle with Pen Holder)
While using the pen holder, sets pivot, direction, radius, and degree for Hamster S to draw a circular path.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  


<img src="https://github.com/user-attachments/assets/988bdb91-422c-4fb8-8ecb-018cbf39db02" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| pivot | Dropdown Option | Pivot reference | left pen, right pen |
| direction | Dropdown Option | Direction | left forward, left backward, right forward, right backward |
| radius | Input Value | Circle radius | Real number ≥ 0 |
| unit | Dropdown Option | Distance unit | cm, mm, inch |
| degree | Input Value | Rotation angle | Real number ≥ 0 |

### JavaScript Code
```javascript
// Left pen, left forward, radius 1cm, 90 degrees | Wait X
__pivot_circle('HamsterS*0', 'left pen', 'left forward', __getDistance('HamsterS*0', 1, 'cm'), 90, false); // (robot, pivot, direction, radius, degree, wait_w)

// Left pen, left backward, radius 1cm, 90 degrees | Wait O
await __pivot_circle('HamsterS*0', 'left pen', 'left backward', __getDistance('HamsterS*0', 1, 'cm'), 90, true); // (robot, pivot, direction, radius, degree, wait_w)

// Left pen, right forward, radius 1cm, 90 degrees | Wait X
__pivot_circle('HamsterS*0', 'left pen', 'right forward', __getDistance('HamsterS*0', 1, 'cm'), 90, false); // (robot, pivot, direction, radius, degree, wait_w)

// Left pen, right backward, radius 1cm, 90 degrees | Wait O
await __pivot_circle('HamsterS*0', 'left pen', 'right backward', __getDistance('HamsterS*0', 1, 'cm'), 90, true); // (robot, pivot, direction, radius, degree, wait_w)

// Right pen, left forward, radius 1mm, 90 degrees | Wait X
__pivot_circle('HamsterS*0', 'right pen', 'left forward', __getDistance('HamsterS*0', 1, 'mm'), 90, false); // (robot, pivot, direction, radius, degree, wait_w)

// Right pen, left backward, radius 1mm, 90 degrees | Wait O
await __pivot_circle('HamsterS*0', 'right pen', 'left backward', __getDistance('HamsterS*0', 1, 'mm'), 90, true); // (robot, pivot, direction, radius, degree, wait_w)

// Right pen, right forward, radius 1mm, 90 degrees | Wait X
__pivot_circle('HamsterS*0', 'right pen', 'right forward', __getDistance('HamsterS*0', 1, 'mm'), 90, false); // (robot, pivot, direction, radius, degree, wait_w)

// Right pen, right backward, radius 1mm, 90 degrees | Wait O
await __pivot_circle('HamsterS*0', 'right pen', 'right backward', __getDistance('HamsterS*0', 1, 'mm'), 90, true); // (robot, pivot, direction, radius, degree, wait_w)
```

### Python Code
```python
# Left pen, left forward, radius 1cm, 90 degrees | Wait X
__pivot_circle('HamsterS*0', 'left pen', 'left forward', __getDistance('HamsterS*0', 1, 'cm'), 90, False) # (robot, pivot, direction, radius, degree, wait_w)

# Left pen, left backward, radius 1cm, 90 degrees | Wait O
await __pivot_circle('HamsterS*0', 'left pen', 'left backward', __getDistance('HamsterS*0', 1, 'cm'), 90, True) # (robot, pivot, direction, radius, degree, wait_w)

# Left pen, right forward, radius 1cm, 90 degrees | Wait X
__pivot_circle('HamsterS*0', 'left pen', 'right forward', __getDistance('HamsterS*0', 1, 'cm'), 90, False) # (robot, pivot, direction, radius, degree, wait_w)

# Left pen, right backward, radius 1cm, 90 degrees | Wait O
await __pivot_circle('HamsterS*0', 'left pen', 'right backward', __getDistance('HamsterS*0', 1, 'cm'), 90, True) # (robot, pivot, direction, radius, degree, wait_w)

# Right pen, left forward, radius 1mm, 90 degrees | Wait X
__pivot_circle('HamsterS*0', 'right pen', 'left forward', __getDistance('HamsterS*0', 1, 'mm'), 90, False) # (robot, pivot, direction, radius, degree, wait_w)

# Right pen, left backward, radius 1mm, 90 degrees | Wait O
await __pivot_circle('HamsterS*0', 'right pen', 'left backward', __getDistance('HamsterS*0', 1, 'mm'), 90, True) # (robot, pivot, direction, radius, degree, wait_w)

# Right pen, right forward, radius 1mm, 90 degrees | Wait X
__pivot_circle('HamsterS*0', 'right pen', 'right forward', __getDistance('HamsterS*0', 1, 'mm'), 90, False) # (robot, pivot, direction, radius, degree, wait_w)

# Right pen, right backward, radius 1mm, 90 degrees | Wait O
await __pivot_circle('HamsterS*0', 'right pen', 'right backward', __getDistance('HamsterS*0', 1, 'mm'), 90, True) # (robot, pivot, direction, radius, degree, wait_w)
```

## Follow a Line Using Sensors
Hamster S follows a specific line using the floor sensors.


<img src="https://github.com/user-attachments/assets/8dda0178-195e-4888-8f3a-0e800a8a72c2" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Floor sensor position | left, right, center |
| color | Dropdown Option | Line color | black, white |

### JavaScript Code
```javascript
$('HamsterS*0:wheel.trace.mode').d = 1; // Follow black line with left floor sensor
$('HamsterS*0:wheel.trace.mode').d = 2; // Follow black line with right floor sensor
$('HamsterS*0:wheel.trace.mode').d = 3; // Follow black line with center floor sensor
$('HamsterS*0:wheel.trace.mode').d = 8; // Follow white line with left floor sensor
$('HamsterS*0:wheel.trace.mode').d = 9; // Follow white line with right floor sensor
$('HamsterS*0:wheel.trace.mode').d = 10; // Follow white line with center floor sensor
```

### Python Code
```python
__('HamsterS*0:wheel.trace.mode').d = 1 # Follow black line with left floor sensor
__('HamsterS*0:wheel.trace.mode').d = 2 # Follow black line with right floor sensor
__('HamsterS*0:wheel.trace.mode').d = 3 # Follow black line with center floor sensor
__('HamsterS*0:wheel.trace.mode').d = 8 # Follow white line with left floor sensor
__('HamsterS*0:wheel.trace.mode').d = 9 # Follow white line with right floor sensor
__('HamsterS*0:wheel.trace.mode').d = 10 # Follow white line with center floor sensor
```

## Turn, Then Follow Line & Stop at the Next Intersection
Hamster S turns in the specified direction, then moves along the line until it reaches the next intersection.  
If you check “wait”, it waits until the move is completed.  
If you check “wait”, it can only be used inside an async function.  


<img src="https://github.com/user-attachments/assets/1c416e83-53cf-42b9-9b5f-11a137804daf" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Move direction | turn left, turn right, move forward, uturn |
| color | Dropdown Option | Line color | black, white |

### JavaScript Code
```javascript
$('HamsterS*0:wheel.trace.mode').d = 4; // Turn left, follow black line, stop at next intersection | Wait O
await $('HamsterS*0:wheel.trace.!mode').w();

$('HamsterS*0:wheel.trace.mode').d = 5; // Turn right, follow black line, stop at next intersection | Wait X

$('HamsterS*0:wheel.trace.mode').d = 6; // Go forward, follow black line, stop at next intersection | Wait O
await $('HamsterS*0:wheel.trace.!mode').w();

$('HamsterS*0:wheel.trace.mode').d = 7; // U-turn, follow black line, stop at next intersection | Wait X

$('HamsterS*0:wheel.trace.mode').d = 11; // Turn left, follow white line, stop at next intersection | Wait O
await $('HamsterS*0:wheel.trace.!mode').w();

$('HamsterS*0:wheel.trace.mode').d = 12; // Turn right, follow white line, stop at next intersection | Wait X

$('HamsterS*0:wheel.trace.mode').d = 13; // Go forward, follow white line, stop at next intersection | Wait O
await $('HamsterS*0:wheel.trace.!mode').w();

$('HamsterS*0:wheel.trace.mode').d = 14; // U-turn, follow white line, stop at next intersection | Wait X
```

### Python Code
```python
__('HamsterS*0:wheel.trace.mode').d = 4 # Turn left, follow black line, stop at next intersection | Wait O
await __('HamsterS*0:wheel.trace.!mode').w()

__('HamsterS*0:wheel.trace.mode').d = 5 # Turn right, follow black line, stop at next intersection | Wait X

__('HamsterS*0:wheel.trace.mode').d = 6 # Go forward, follow black line, stop at next intersection | Wait O
await __('HamsterS*0:wheel.trace.!mode').w()

__('HamsterS*0:wheel.trace.mode').d = 7 # U-turn, follow black line, stop at next intersection | Wait X

__('HamsterS*0:wheel.trace.mode').d = 11 # Turn left, follow white line, stop at next intersection | Wait O
await __('HamsterS*0:wheel.trace.!mode').w()

__('HamsterS*0:wheel.trace.mode').d = 12 # Turn right, follow white line, stop at next intersection | Wait X

__('HamsterS*0:wheel.trace.mode').d = 13 # Go forward, follow white line, stop at next intersection | Wait O
await __('HamsterS*0:wheel.trace.!mode').w()

__('HamsterS*0:wheel.trace.mode').d = 14 # U-turn, follow white line, stop at next intersection | Wait X
```

## Set Line Tracing Speed
Sets Hamster S line tracing speed.  
Speed range is 1 ~ 10.


<img src="https://github.com/user-attachments/assets/8471b806-838c-43a2-be0a-a08ac4e4f1c7" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| velocity | Input Value | line tracing speed | Integer 1 ~ 10 | 

### JavaScript Code
```javascript
$('HamsterS*0:wheel.trace.speed').d = 1; // Set line tracing speed to 1
```

### Python Code
```python
__('HamsterS*0:wheel.trace.speed').d = 1 # Set line tracing speed to 1
```

## Set Line Tracing Gain
Sets Hamster S line tracing gain.  
Gain range is 1 ~ 10.


<img src="https://github.com/user-attachments/assets/db3fffd9-dfd3-4a11-be3a-6ca99afe6cb8" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| gain | Input Value | line tracing gain | Integer 1 ~ 10 | 

### JavaScript Code
```javascript
$('HamsterS*0:wheel.trace.gain').d = 5; // Set line tracing gain to 5
```

### Python Code
```python
__('HamsterS*0:wheel.trace.gain').d = 5 # Set line tracing gain to 5
```

## Stop Line Tracing
Stops Hamster S line tracing feature.


<img src="https://github.com/user-attachments/assets/784ad1dc-eb07-4d6d-9464-efe9388fd3a1" width="50%" height="50%" >

### JavaScript Code
```javascript
$('HamsterS*0:wheel.trace.mode').d = 0; // Stop line tracing
```

### Python Code
```python
__('HamsterS*0:wheel.trace.mode').d = 0 # Stop line tracing
```

## Set LED Color
Sets Hamster S LED color.  
You can set the left, right, or both LEDs.


<img src="https://github.com/user-attachments/assets/21f868d3-537b-409e-b275-32e37a11a63d" width="60%" height="60%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | LED side | left, right, both |
| color | Dropdown Option | Color | black([0, 0, 0]), red([255, 0, 0]), yellow([255, 255, 0]), green([0, 255, 0])<br>cyan([0, 255, 255]), blue([0, 0, 255]), magenta([255, 0, 255]), white([255, 255, 255]) | 

### JavaScript Code
```javascript
// Set left LED color to red
$('HamsterS*0:led.left').d = [255, 0, 0];

// Set right LED color to green
$('HamsterS*0:led.right').d = [0, 255, 0];

// Set both LED colors to blue
$('HamsterS*0:led.left').d = [0, 0, 255]; 
$('HamsterS*0:led.right').d = [0, 0, 255];
```

### Python Code
```python
# Set left LED color to red
__('HamsterS*0:led.left').d = [255, 0, 0]

# Set right LED color to green
__('HamsterS*0:led.right').d = [0, 255, 0]

# Set both LED colors to blue
__('HamsterS*0:led.left').d = [0, 0, 255]
__('HamsterS*0:led.right').d = [0, 0, 255]
```

## Set LED Color Using Color Category Blocks
Sets Hamster S LED color using blocks from the Color category.  
You can set the left, right, or both LEDs.

<img src="https://github.com/user-attachments/assets/d1c094cf-e2bf-46b6-bbd9-58bf4f0a29ac" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | LED side | left, right, both |
| color | Input Value | LED color | RGB array | 

### JavaScript Code
```javascript
// Set left LED color to R:255, G:255, B:255
$('HamsterS*0:led.left').d = [255, 255, 255];

// Set right LED color to R:255, G:255, B:255 
$('HamsterS*0:led.right').d = [255, 255, 255];

// Set both LED colors to random colors
$('HamsterS*0:led.left').d = __randomColor();
$('HamsterS*0:led.right').d = __randomColor();
```

### Python Code
```python
# Set left LED color to R:255, G:255, B:255
__('HamsterS*0:led.left').d = [255, 255, 255]

# Set right LED color to R:255, G:255, B:255
__('HamsterS*0:led.right').d = [255, 255, 255]

# Set both LED colors to random colors
__('HamsterS*0:led.left').d = __randomColor()
__('HamsterS*0:led.right').d = __randomColor()
```

## Change LED Color by Specified RGB Amount
Changes Hamster S LED color by the specified R, G, B values.  
You can change the left, right, or both LEDs.


<img src="https://github.com/user-attachments/assets/b2fc2f3f-bb87-4e99-9fa5-72196d9d3bb9" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | LED side | left, right, both |
| color | Input Value | Delta R,G,B values | Integers for each of R, G, B: -255 ~ 255 | 

### JavaScript Code
```javascript
// Change left LED color by R:10, G:10, B:10
$('HamsterS*0:led.left').d = [$('HamsterS*0:led.left').d[0] + 10, $('HamsterS*0:led.left').d[1] + 10, $('HamsterS*0:led.left').d[2] + 10];

// Change right LED color by R:100, G:100, B:100
$('HamsterS*0:led.right').d = [$('HamsterS*0:led.right').d[0] + 100, $('HamsterS*0:led.right').d[1] + 100, $('HamsterS*0:led.right').d[2] + 100];

// Change both LED colors by R:-50, G:-50, B:-50
$('HamsterS*0:led.left').d = [$('HamsterS*0:led.left').d[0] + -50, $('HamsterS*0:led.left').d[1] + -50, $('HamsterS*0:led.left').d[2] + -50];
$('HamsterS*0:led.right').d = [$('HamsterS*0:led.right').d[0] + -50, $('HamsterS*0:led.right').d[1] + -50, $('HamsterS*0:led.right').d[2] + -50];
```

### Python Code
```python
# Change left LED color by R:10, G:10, B:10
__('HamsterS*0:led.left').d = [__('HamsterS*0:led.left').d[0] + 10, __('HamsterS*0:led.left').d[1] + 10, __('HamsterS*0:led.left').d[2] + 10]

# Change right LED color by R:100, G:100, B:100
__('HamsterS*0:led.right').d = [__('HamsterS*0:led.right').d[0] + 100, __('HamsterS*0:led.right').d[1] + 100, __('HamsterS*0:led.right').d[2] + 100]

# Change both LED colors by R:-50, G:-50, B:-50
__('HamsterS*0:led.left').d = [__('HamsterS*0:led.left').d[0] + -50, __('HamsterS*0:led.left').d[1] + -50, __('HamsterS*0:led.left').d[2] + -50]
__('HamsterS*0:led.right').d = [__('HamsterS*0:led.right').d[0] + -50, __('HamsterS*0:led.right').d[1] + -50, __('HamsterS*0:led.right').d[2] + -50]
	
```

## Turn Off LED
Turns off Hamster S LED color.  
You can turn off the left, right, or both LEDs.


<img src="https://github.com/user-attachments/assets/86d7b944-4b2c-4338-a8bb-ddc1ba6e0bea" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | LED side | left, right, both |

### JavaScript Code
```javascript
// Turn off left LED
$('HamsterS*0:led.left').d = [0, 0, 0];

// Turn off right LED
$('HamsterS*0:led.right').d = [0, 0, 0];

// Turn off both LEDs
$('HamsterS*0:led.left').d = [0, 0, 0];
$('HamsterS*0:led.right').d = [0, 0, 0];
```

### Python Code
```python
# Turn off left LED
__('HamsterS*0:led.left').d = [0, 0, 0]

# Turn off right LED
__('HamsterS*0:led.right').d = [0, 0, 0]

# Turn off both LEDs
__('HamsterS*0:led.left').d = [0, 0, 0]
__('HamsterS*0:led.right').d = [0, 0, 0]
```

## Set Buzzer Frequency
Sets Hamster S buzzer sound to the specified frequency.  
Frequency range is 10 ~ 4200Hz.


<img src="https://github.com/user-attachments/assets/32fff242-7400-4b0a-b606-e5d2172cca06" width="60%" height="60%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| sound | Input Value | Buzzer frequency | 10 ~ 4200 (Hz) |

### JavaScript Code
```javascript
// Set buzzer frequency to 4200Hz
$('HamsterS*0:sound.buzz').d = 4200;
```

### Python Code
```python
# Set buzzer frequency to 4200Hz
__('HamsterS*0:sound.buzz').d = 4200
```

## Play a Note
Hamster S plays the specified musical note.


<img src="https://github.com/user-attachments/assets/1210e0ea-8553-4316-a88e-88b3d93e05c4" width="60%" height="60%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| note | Dropdown Option | Note | Do, Do#, Re, Re#, Mi, Fa, Fa#, So, So#, La, La#, Si |
| octave | Dropdown Option | Octave | 1 ~ 7 |

### JavaScript Code
```javascript
// Play octave 1 Do
$('HamsterS*0:sound.note').d = 4;

// Play octave 1 Re
$('HamsterS*0:sound.note').d = 6;

// Play octave 2 Do
$('HamsterS*0:sound.note').d = 16;

// Play octave 7 Si
$('HamsterS*0:sound.note').d = 87;
```

### Python Code
```python
# Play octave 1 Do
__('HamsterS*0:sound.note').d = 4

# Play octave 1 Re
__('HamsterS*0:sound.note').d = 6

# Play octave 2 Do
__('HamsterS*0:sound.note').d = 16

# Play octave 7 Si
__('HamsterS*0:sound.note').d = 87
```

## Play Sound Clip
Hamster S plays a specific sound clip.  
If you check “wait”, it waits until playback is complete.  
If you check “wait”, it can only be used inside an async function.  


<img src="https://github.com/user-attachments/assets/831efd79-671a-4491-a4f4-a868a79c7cd5" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| sound_clip | Dropdown Option | Sound clip | beep(1), beep2(2), beep3(3), beep_repeat(4), beep_random(5), beep_random_repeat(6), snore(7), snore_repeat(8), siren(9), siren_repeat(10), engine(11), engine_repeat(12), fart_a(13), fart_b(14), noise(15), noise_repeat(16), whistle(17), chop_chop(18), chop_chop_repeat(19), robot(32), dibidibidip(33), melody(34), mission_complete(35), happy(48), angry(49), sad(50), sleep(51), toy_march(52), birthday(53) |

### JavaScript Code
```javascript
// Play beep | Wait O
$('HamsterS*0:sound.clip').d = 1;
await $('HamsterS*0:sound.!clip').w();

// Play birthday | Wait X
$('HamsterS*0:sound.clip').d = 53;
```

### Python Code
```python
# Play beep | Wait O
__('HamsterS*0:sound.clip').d = 1
await __('HamsterS*0:sound.!clip').w()

# Play birthday | Wait X
__('HamsterS*0:sound.clip').d = 53
```

## Stop Sound
Stops Hamster S sound.


<img src="https://github.com/user-attachments/assets/0b46cc99-6797-49bf-a94a-aab9ff6e6509" width="40%" height="40%" >

### JavaScript Code
```javascript
// Stop Hamster S sound
__stopSound('HamsterS*0');
```

### Python Code
```python
# Stop Hamster S sound
__stopSound('HamsterS*0')
```

## Is Sound Playing?
Returns whether Hamster S sound is playing as **True(1) / False(0)**.


<img src="https://github.com/user-attachments/assets/581a73d0-faa7-403e-97ae-cfe6f76c15ea" width="60%" height="60%" >

### JavaScript Code
```javascript
// Is Hamster S sound playing? - true if playing, false otherwise
$('HamsterS*0:sound.playing').d;
```

### Python Code
```python
# Is Hamster S sound playing? - True if playing, False otherwise
__('HamsterS*0:sound.playing').d
```

## Wheel Speed Value
Gets the specified Hamster S wheel speed value.


<img src="https://github.com/user-attachments/assets/f312ffa1-cbfd-44d1-ab2d-8ccd369882e8" width="90%" height="90%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left, right |

### JavaScript Code
```javascript
// Left wheel speed
__getSpeedInput('HamsterS*0', $('HamsterS*0:wheel.speed.left').d);

// Right wheel speed
__getSpeedInput('HamsterS*0', $('HamsterS*0:wheel.speed.right').d);
```

### Python Code
```python
# Left wheel speed
__getSpeedInput('HamsterS*0', __('HamsterS*0:wheel.speed.left').d)

# Right wheel speed
__getSpeedInput('HamsterS*0', __('HamsterS*0:wheel.speed.right').d)
```

## Proximity Sensor Value
Gets the specified Hamster S proximity sensor value.


<img src="https://github.com/user-attachments/assets/ee1b85ba-2d65-4e09-8cb0-3da3a496c86a" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left, right |

### JavaScript Code
```javascript
// Left proximity sensor value
$('HamsterS*0:proximity.left').d;

// Right proximity sensor value
$('HamsterS*0:proximity.right').d;
```

### Python Code
```python
# Left proximity sensor value
__('HamsterS*0:proximity.left').d

# Right proximity sensor value
__('HamsterS*0:proximity.right').d
```

## Floor Sensor Value
Gets the specified Hamster S floor sensor value.


<img src="https://github.com/user-attachments/assets/6b0e71a3-a901-4976-a50d-23433329c75d" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Direction | left, right |

### JavaScript Code
```javascript
// Left floor sensor value
$('HamsterS*0:floor.left').d;

// Right floor sensor value
$('HamsterS*0:floor.right').d;
```

### Python Code
```python
# Left floor sensor value
__('HamsterS*0:floor.left').d

# Right floor sensor value
__('HamsterS*0:floor.right').d
```

## Acceleration Value
Gets the acceleration value for a specific axis of Hamster S.


<img src="https://github.com/user-attachments/assets/8b498a1c-d09c-4883-b515-1fa5645c3dcb" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| axis | Dropdown Option | Axis | x, y, z |

### JavaScript Code
```javascript
// Acceleration value on x-axis
$('HamsterS*0:acceleration.x').d;

// Acceleration value on y-axis
$('HamsterS*0:acceleration.y').d;

// Acceleration value on z-axis
$('HamsterS*0:acceleration.z').d;
```

### Python Code
```python
# Acceleration value on x-axis
__('HamsterS*0:acceleration.x').d

# Acceleration value on y-axis
__('HamsterS*0:acceleration.y').d

# Acceleration value on z-axis
__('HamsterS*0:acceleration.z').d
```

## Light Sensor Value
Gets Hamster S light sensor value.


<img src="https://github.com/user-attachments/assets/c25b0bb7-a20c-4c8c-b9d4-c3a99e4319ee" width="50%" height="50%" >

### JavaScript Code
```javascript
// Light sensor value
$('HamsterS*0:light').d; 
```

### Python Code
```python
# Light sensor value
__('HamsterS*0:light').d
```

## Temperature Sensor Value
Gets Hamster S temperature sensor value.


<img src="https://github.com/user-attachments/assets/bb345265-ce99-4d4c-ab9f-ac2e0becf27f" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| unit | Dropdown Option | Temperature unit | °C, °F |

### JavaScript Code
```javascript
// Temperature in Celsius
__getTemperature($('HamsterS*0:temperature').d, '°C');

// Temperature in Fahrenheit
__getTemperature($('HamsterS*0:temperature').d, '°F');
```

### Python Code
```python
# Temperature in Celsius
__getTemperature(__('HamsterS*0:temperature').d, '°C')

# Temperature in Fahrenheit
__getTemperature(__('HamsterS*0:temperature').d, '°F')
```

## Signal Strength Value
Gets Hamster S signal strength value.


<img src="https://github.com/user-attachments/assets/08f9945f-a237-456d-b50e-5c433de5c978" width="50%" height="50%" >

### JavaScript Code
```javascript
// Signal strength value
$('HamsterS*0:signal_strength').d;
```

### Python Code
```python
# Signal strength value
__('HamsterS*0:signal_strength').d
```

## Battery Level Value
Gets Hamster S battery charge level value.


<img src="https://github.com/user-attachments/assets/8dc8a492-c2b8-44f4-9b1e-5456944d0dc1" width="50%" height="50%" >

### JavaScript Code
```javascript
// Battery level value
$('HamsterS*0:battery.level').d;
```

### Python Code
```python
# Battery level value
__('HamsterS*0:battery.level').d
```

## State Change Condition
Depending on the condition, returns whether Hamster S state has changed as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/a9a221eb-7ffd-4173-a01c-9e4c8e6948e3" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| condition | Dropdown Option | Pose / detect condition | tilt forward, tilt backward, tilt left, tilt right, flipped, not flipped, detected obstacle/hand, tap |

### JavaScript Code
```javascript
// Is Hamster S tilted forward?
$('HamsterS*0:acceleration.x').d > 5000;

// Is Hamster S tilted backward?
$('HamsterS*0:acceleration.x').d < -5000;

// Is Hamster S tilted left?
$('HamsterS*0:acceleration.y').d > 5000;

// Is Hamster S tilted right?
$('HamsterS*0:acceleration.y').d < -5000;

// Is Hamster S flipped over?
$('HamsterS*0:acceleration.z').d > 0;

// Is Hamster S not flipped?
$('HamsterS*0:acceleration.z').d < -3000;

// Did Hamster S detect obstacle/hand?
$('HamsterS*0:proximity.left').d > 50 || $('HamsterS*0:proximity.right').d > 50;

// Was Hamster S tapped?
$('HamsterS*0:acceleration.tap').e;
```

### Python Code
```python
# Is Hamster S tilted forward?
__('HamsterS*0:acceleration.x').d > 5000

# Is Hamster S tilted backward?
__('HamsterS*0:acceleration.x').d < -5000

# Is Hamster S tilted left?
__('HamsterS*0:acceleration.y').d > 5000

# Is Hamster S tilted right?
__('HamsterS*0:acceleration.y').d < -5000

# Is Hamster S flipped over?
__('HamsterS*0:acceleration.z').d > 0

# Is Hamster S not flipped?
__('HamsterS*0:acceleration.z').d < -3000

# Did Hamster S detect obstacle/hand?
__('HamsterS*0:proximity.left').d > 50 or __('HamsterS*0:proximity.right').d > 50

# Was Hamster S tapped?
__('HamsterS*0:acceleration.tap').e
```

## Set IO Port Input Mode
Sets the input mode of Hamster S I/O ports.  
You can set port A, port B, or both ports A and B.


<img src="https://github.com/user-attachments/assets/d8e75278-2387-41b2-9a1c-ee752767ae4d" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| port | Dropdown Option | I/O port selection | A, B, A and B |
| mode | Dropdown Option | Port mode | analog input, digital input, digital input(pull-up), digital input(pull-down), voltage input, servo output, pwm output, digital output |

### JavaScript Code
```javascript
// Set Hamster S port A to analog input
$('HamsterS*0:io.a.mode').d = 0;

// Set Hamster S port A to digital input
$('HamsterS*0:io.a.mode').d = 1;

// Set Hamster S port B to digital input (pull-up)
$('HamsterS*0:io.b.mode').d = 2;

// Set Hamster S port B to digital input (pull-down)
$('HamsterS*0:io.b.mode').d = 3;

// Set Hamster S ports A and B to voltage input
$('HamsterS*0:io.a.mode').d = 4;
$('HamsterS*0:io.b.mode').d = 4;

// Set Hamster S ports A and B to servo output
$('HamsterS*0:io.a.mode').d = 8;
$('HamsterS*0:io.b.mode').d = 8;

// Set Hamster S ports A and B to pwm output
$('HamsterS*0:io.a.mode').d = 9;
$('HamsterS*0:io.b.mode').d = 9;

// Set Hamster S ports A and B to digital output
$('HamsterS*0:io.a.mode').d = 10;
$('HamsterS*0:io.b.mode').d = 10;
```

### Python Code
```python
# Set Hamster S port A to analog input
__('HamsterS*0:io.a.mode').d = 0

# Set Hamster S port A to digital input
__('HamsterS*0:io.a.mode').d = 1

# Set Hamster S port B to digital input (pull-up)
__('HamsterS*0:io.b.mode').d = 2

# Set Hamster S port B to digital input (pull-down)
__('HamsterS*0:io.b.mode').d = 3

# Set Hamster S ports A and B to voltage input
__('HamsterS*0:io.a.mode').d = 4
__('HamsterS*0:io.b.mode').d = 4

# Set Hamster S ports A and B to servo output
__('HamsterS*0:io.a.mode').d = 8
__('HamsterS*0:io.b.mode').d = 8

# Set Hamster S ports A and B to pwm output
__('HamsterS*0:io.a.mode').d = 9
__('HamsterS*0:io.b.mode').d = 9

# Set Hamster S ports A and B to digital output
__('HamsterS*0:io.a.mode').d = 10
__('HamsterS*0:io.b.mode').d = 10
```

## Set IO Port Output Value
Sets the output value of Hamster S I/O ports.  
You can set port A, port B, or both ports A and B.

<img src="https://github.com/user-attachments/assets/27fbb5ca-235a-408b-a2fb-dd8c778d45a2" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| port | Dropdown Option | I/O port selection | A, B, A and B |
| output | Input Value | Output value | 0 ~ 180 |

### JavaScript Code
```javascript
// Set Hamster S port A output to 180
$('HamsterS*0:io.a.out').d = 180;

// Set Hamster S port B output to 0
$('HamsterS*0:io.b.out').d = 0;

// Set Hamster S ports A and B output to 100
$('HamsterS*0:io.a.out').d = 100;
$('HamsterS*0:io.b.out').d = 100;
```

### Python Code
```python
# Set Hamster S port A output to 180
__('HamsterS*0:io.a.out').d = 180

# Set Hamster S port B output to 0
__('HamsterS*0:io.b.out').d = 0

# Set Hamster S ports A and B output to 100
__('HamsterS*0:io.a.out').d = 100
__('HamsterS*0:io.b.out').d = 100
```

## Change IO Port Output Value
Changes the output value of Hamster S I/O ports.  
The new output value becomes the current port output value plus the input value.  
The new output value is clamped to the range 0 ~ 180.  
You can set port A, port B, or both ports A and B.


<img src="https://github.com/user-attachments/assets/c683ed60-cace-43b4-8692-74f7ab9d5c73" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| port | Dropdown Option | I/O port selection | A, B, A and B |
| value | Input Value | Delta value | Integer |

### JavaScript Code
```javascript
// Change Hamster S port A output by +10
$('HamsterS*0:io.a.out').d = $('HamsterS*0:io.a.out').d + 10;

// Change Hamster S port B output by +20
$('HamsterS*0:io.b.out').d = $('HamsterS*0:io.b.out').d + 20;

// Change Hamster S ports A and B output by +30
$('HamsterS*0:io.a.out').d = $('HamsterS*0:io.a.out').d + 30;
$('HamsterS*0:io.b.out').d = $('HamsterS*0:io.b.out').d + 30;
```

### Python Code
```python
# Change Hamster S port A output by +10
__('HamsterS*0:io.a.out').d = __('HamsterS*0:io.a.out').d + 10

# Change Hamster S port B output by +20
__('HamsterS*0:io.b.out').d = __('HamsterS*0:io.b.out').d + 20

# Change Hamster S ports A and B output by +30
__('HamsterS*0:io.a.out').d = __('HamsterS*0:io.a.out').d + 30
__('HamsterS*0:io.b.out').d = __('HamsterS*0:io.b.out').d + 30
```

## Open / Close Gripper
Opens or closes Hamster S gripper.


<img src="https://github.com/user-attachments/assets/c17a7506-07db-463d-95bf-a38b2060966d" width="60%" height="60%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Gripper toggle | open(1), close(2) |

### JavaScript Code
```javascript
// Open Hamster S gripper
$('HamsterS*0:io.gripper').d = 1;

// Close Hamster S gripper
$('HamsterS*0:io.gripper').d = 2;
```

### Python Code
```python
# Open Hamster S gripper
__('HamsterS*0:io.gripper').d = 1

# Close Hamster S gripper
__('HamsterS*0:io.gripper').d = 2
```

## Set Shooter Angle
Controls Hamster S by setting the shooter angle.  
Angle range is 0 ~ 255.


<img src="https://github.com/user-attachments/assets/e63043cb-d73b-4a21-a3ab-0eee36cc289d" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| angle | Input Value | Shooter angle | Integer 0 ~ 255 |

### JavaScript Code
```javascript
// Set Hamster S shooter angle to 255
$('HamsterS*0:io.shooter').d = 255;

// Set Hamster S shooter angle to 0
$('HamsterS*0:io.shooter').d = 0;
```

### Python Code
```python
# Set Hamster S shooter angle to 255
__('HamsterS*0:io.shooter').d = 255

# Set Hamster S shooter angle to 0
__('HamsterS*0:io.shooter').d = 0
```

## IO Port Input Value
Gets Hamster S I/O port input value.

<img src="https://github.com/user-attachments/assets/85288705-dc0a-4463-b796-17026fcf1536" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| port | Dropdown Option | I/O port | A, B |

### JavaScript Code
```javascript
// Hamster S port A input value
$('HamsterS*0:io.a.in').d;

// Hamster S port B input value
$('HamsterS*0:io.b.in').d;
```

### Python Code
```python
# Hamster S port A input value
__('HamsterS*0:io.a.in').d

# Hamster S port B input value
__('HamsterS*0:io.b.in').d
```