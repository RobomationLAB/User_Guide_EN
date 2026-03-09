# Open Dashboard
**Open Dashboard** is not a block that can be used in block coding,  
but it allows you to open a dashboard where you can check how the model used in the extension module is applied.

## Dashboard Screen
When you click Open Dashboard, you can see the following screen.  

<img src="https://github.com/user-attachments/assets/c0b9d3bf-4789-494f-bdcd-1d9e1565e871" width="100%" height="100%" >

## Detailed Features

### Power
Turns the selected camera on or off.

### Load Model
Loads the trained hand model. This is a required step to use the **Hand Detection** extension module.

### Detect
Starts or stops hand detection.  
You can choose whether to run it only once with the Once button, or continuously with the Continuous button.  
You can also stop detection using the Stop button.

### Show Result
Displays hand detection results on the camera screen.

### Max Hands
Selects the maximum number of hands to detect.

#### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| hand | Dropdown Option | Number of hands to detect | one hand, both hands |

### Sensory Data
Displays data values based on the selected hand part.

#### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| parts | Dropdown Option | Hand part | hand, palm, wrist, thumbs, index, middle, ring, pinky |

<br>

# Blocks
## Select Camera
Selects the camera to use for the Hand Detection module.


<img src="https://github.com/user-attachments/assets/43993d4b-0a8e-4cc1-83bc-0b1aa0f3cf7a" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| camera | Dropdown Option | Camera to use | Connected camera list |

### JavaScript Code
```javascript
// Set a specific camera for hand detection (id is an example)
$('HandDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb';
```

### Python Code
```python
# Set a specific camera for hand detection (id is an example)
__('HandDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb'
```

## Load Hand Model
Loads the trained hand model. This must be done to use the features of the Hand Detection module.  
If **Wait** is checked, it waits until the model finishes loading.  
If **Wait** is checked, it can only be used inside an async function.


<img src="https://github.com/user-attachments/assets/a8dcf7fd-6417-4a1c-af81-f061e9017dfb" width="80%" height="80%" >

### JavaScript Code
```javascript
// Load hand model | Wait: O
$('HandDetection*0:load_model').d = 1;
await $('HandDetection*0:!load_model').w();

// Load hand model | Wait: X
$('HandDetection*0:load_model').d = 1;
```

### Python Code
```python
# Load hand model | Wait: O
__('HandDetection*0:load_model').d = 1
await __('HandDetection*0:!load_model').w()

# Load hand model | Wait: X
__('HandDetection*0:load_model').d = 1
```

## Set Detection Target
Decides whether to detect based on **one hand** or **both hands**.


<img src="https://github.com/user-attachments/assets/26f0866c-50eb-4f01-b515-dd47177857c4" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| pivot | Dropdown Option | Detection target | One hand (1), Both hands (2) |

### JavaScript Code
```javascript
// Set to detect one hand
$('HandDetection*0:maxHands').d = 1;

// Set to detect both hands
$('HandDetection*0:maxHands').d = 2;
```

### Python Code
```python
# Set to detect one hand
__('HandDetection*0:maxHands').d = 1

# Set to detect both hands
__('HandDetection*0:maxHands').d = 2
```

## Detect Hands Once
Detects hands currently on the screen and displays them only once.

<img src="https://github.com/user-attachments/assets/70030e53-6bcf-4725-8d61-93662835b3ce" width="70%" height="70%" >

### JavaScript Code
```javascript
// Detect hands once
$('HandDetection*0:detect.once').d = 1;
```

### Python Code
```python
# Detect hands once
__('HandDetection*0:detect.once').d = 1
```

## Detect Hands Continuously
Starts or stops continuous hand detection.  
When continuous detection starts, it keeps tracking and displaying hands currently on the screen.


<img src="https://github.com/user-attachments/assets/d3a3e97b-7e89-404d-ac1e-6fc4a2e4b237" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Hand detection | Start (1), Stop (0) |

### JavaScript Code
```javascript
// Start continuous hand detection
$('HandDetection*0:detect.continuous').d = 1;

// Stop continuous hand detection
$('HandDetection*0:detect.continuous').d = 0;
```

### Python Code
```python
# Start continuous hand detection
__('HandDetection*0:detect.continuous').d = 1

# Stop continuous hand detection
__('HandDetection*0:detect.continuous').d = 0
```

## Show Hand Detection Result
Decides whether to display hand detection results on the camera screen.


<img src="https://github.com/user-attachments/assets/775f8e75-2816-4859-a5db-35e5a7d2ce70" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Show results | Show (1), Hide (0) |

### JavaScript Code
```javascript
// Show hand detection results
$('HandDetection*0:display').d = 1;

// Hide hand detection results
$('HandDetection*0:display').d = 0;
```

### Python Code
```python
# Show hand detection results
__('HandDetection*0:display').d = 1

# Hide hand detection results
__('HandDetection*0:display').d = 0
```

## Hand-Related Data
Returns the data of the selected hand part.


<img src="https://github.com/user-attachments/assets/bd9c1534-2359-4791-b5ac-0df95f91ed3c" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Hand side | left, right |
| part | Dropdown Option | Hand part | palm, wrist |
| axis | Dropdown Option | Coordinate axis | x, y |

### JavaScript Code
```javascript
// Right palm x coordinate
$('HandDetection*0:right.palm.x').d;

// Right palm y coordinate
$('HandDetection*0:right.palm.y').d;

// Right wrist x coordinate
$('HandDetection*0:right.wrist.x').d;

// Right wrist y coordinate
$('HandDetection*0:right.wrist.y').d;

// Left palm x coordinate
$('HandDetection*0:left.palm.x').d;

// Left palm y coordinate
$('HandDetection*0:left.palm.y').d;

// Left wrist x coordinate
$('HandDetection*0:left.wrist.x').d;

// Left wrist y coordinate
$('HandDetection*0:left.wrist.y').d;
```

### Python Code
```python
# Right palm x coordinate
__('HandDetection*0:right.palm.x').d

# Right palm y coordinate
__('HandDetection*0:right.palm.y').d

# Right wrist x coordinate
__('HandDetection*0:right.wrist.x').d

# Right wrist y coordinate
__('HandDetection*0:right.wrist.y').d

# Left palm x coordinate
__('HandDetection*0:left.palm.x').d

# Left palm y coordinate
__('HandDetection*0:left.palm.y').d

# Left wrist x coordinate
__('HandDetection*0:left.wrist.x').d

# Left wrist y coordinate
__('HandDetection*0:left.wrist.y').d
```

## Finger Joint Data
Returns the selected finger joint data.


<img src="https://github.com/user-attachments/assets/36f2b5d7-cd4c-41d4-b70d-132135c3943c" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Hand side | left, right |
| finger | Dropdown Option | Finger | thumb, index, middle, ring, pinky |
| joint | Dropdown Option | Finger joint | first, second, third, last |
| axis | Dropdown Option | Coordinate axis | x, y |

### JavaScript Code
```javascript
// Right thumb first joint x coordinate
$('HandDetection*0:right.thumb.first.x').d;

// Right index second joint x coordinate
$('HandDetection*0:right.index.second.x').d;

// Right middle third joint x coordinate
$('HandDetection*0:right.middle.third.x').d;

// Right ring first joint y coordinate
$('HandDetection*0:right.ring.first.y').d;

// Right pinky first joint y coordinate
$('HandDetection*0:right.pinky.first.y').d;
```

### Python Code
```python
# Right thumb first joint x coordinate
__('HandDetection*0:right.thumb.first.x').d

# Right index second joint x coordinate
__('HandDetection*0:right.index.second.x').d

# Right middle third joint x coordinate
__('HandDetection*0:right.middle.third.x').d

# Right ring first joint y coordinate
__('HandDetection*0:right.ring.first.y').d

# Right pinky first joint y coordinate
__('HandDetection*0:right.pinky.first.y').d
```

## Hand Bounding Box Data
Defines the area around the detected hand as a rectangle and returns that rectangle’s data.


<img src="https://github.com/user-attachments/assets/9cd36396-a229-439c-86fd-54ebb50a391e" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction | Dropdown Option | Hand side | left, right |
| part | Dropdown Option | Hand part | hand, palm |
| axis | Dropdown Option | Rectangle data | min_x, max_x, min_y, max_y, width, height, area |

### JavaScript Code
```javascript
// Right hand min x
$('HandDetection*0:right.hand.min_x').d;

// Right hand max x
$('HandDetection*0:right.hand.max_x').d;

// Right hand min y
$('HandDetection*0:right.hand.min_y').d;

// Right hand max y
$('HandDetection*0:right.hand.max_y').d;

// Right hand width
$('HandDetection*0:right.hand.width').d;

// Right hand height
$('HandDetection*0:right.hand.height').d;

// Right hand area
$('HandDetection*0:right.hand.area').d;

// Left palm area
$('HandDetection*0:left.palm.area').d;
```

### Python Code
```python
# Right hand min x
__('HandDetection*0:right.hand.min_x').d

# Right hand max x
__('HandDetection*0:right.hand.max_x').d

# Right hand min y
__('HandDetection*0:right.hand.min_y').d

# Right hand max y
__('HandDetection*0:right.hand.max_y').d

# Right hand width
__('HandDetection*0:right.hand.width').d

# Right hand height
__('HandDetection*0:right.hand.height').d

# Right hand area
__('HandDetection*0:right.hand.area').d

# Left palm area
__('HandDetection*0:left.palm.area').d
```

## Distance Between Two Hands
Returns the distance between two hands.


<img src="https://github.com/user-attachments/assets/9d100db2-cb1c-47ab-9ddc-f4d281a13f2f" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction 1 | Dropdown Option | Hand side | right, left |
| part 1 | Dropdown Option | Hand part | hand, palm |
| direction 2 | Dropdown Option | Hand side | right, left |
| part 2 | Dropdown Option | Hand part | hand, palm |
| distance | Dropdown Option | Distance type | distance, horizontal distance, vertical distance |

### JavaScript Code
```javascript
// Distance from right hand to left hand
Math.sqrt( Math.pow(($('HandDetection*0:left.hand.x').d - $('HandDetection*0:right.hand.x').d), 2) + Math.pow(($('HandDetection*0:left.hand.y').d - $('HandDetection*0:right.hand.y').d), 2) );

// Horizontal distance from right palm to left palm
Math.abs($('HandDetection*0:left.palm.x').d - $('HandDetection*0:right.palm.x').d);

// Vertical distance from right hand to left palm
Math.abs($('HandDetection*0:left.palm.y').d - $('HandDetection*0:right.hand.y').d);
```

### Python Code
```python
# Distance from right hand to left hand
math.sqrt( math.pow((__('HandDetection*0:left.hand.x').d - __('HandDetection*0:right.hand.x').d), 2) + math.pow((__('HandDetection*0:left.hand.y').d - __('HandDetection*0:right.hand.y').d), 2) )

# Horizontal distance from right palm to left palm
math.fabs(__('HandDetection*0:left.palm.x').d - __('HandDetection*0:right.palm.x').d)

# Vertical distance from right hand to left palm
math.fabs(__('HandDetection*0:left.palm.y').d - __('HandDetection*0:right.hand.y').d)
```

## Distance Between Hand and Finger Joint
Returns the distance between a hand part and a finger joint.

<img src="https://github.com/user-attachments/assets/a3e3d49a-ed01-42c4-bd04-9e9ef3076d37" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction 1 | Dropdown Option | Hand side | right, left |
| part 1 | Dropdown Option | Hand part | hand, palm |
| direction 2 | Dropdown Option | Hand side | right, left |
| finger 2 | Dropdown Option | Finger | thumb, index, middle, ring, pinky |
| joint 2 | Dropdown Option | Finger joint | first, second, third, last |
| distance | Dropdown Option | Distance type | distance, horizontal distance, vertical distance |

### JavaScript Code
```javascript
// Distance from right palm to right thumb first joint
Math.sqrt( Math.pow(($('HandDetection*0:right.thumb.first.x').d - $('HandDetection*0:right.palm.x').d), 2) + Math.pow(($('HandDetection*0:right.thumb.first.y').d - $('HandDetection*0:right.palm.y').d), 2) );

// Horizontal distance from right palm to right index second joint
Math.abs($('HandDetection*0:right.index.second.x').d - $('HandDetection*0:right.palm.x').d);

// Vertical distance from right palm to right middle third joint
Math.abs($('HandDetection*0:right.middle.third.y').d - $('HandDetection*0:right.palm.y').d);

// Distance from right palm to right ring last joint
Math.sqrt( Math.pow(($('HandDetection*0:right.ring.last.x').d - $('HandDetection*0:right.palm.x').d), 2) + Math.pow(($('HandDetection*0:right.ring.last.y').d - $('HandDetection*0:right.palm.y').d), 2) );

// Distance from right palm to right pinky last joint
Math.sqrt( Math.pow(($('HandDetection*0:right.pinky.last.x').d - $('HandDetection*0:right.palm.x').d), 2) + Math.pow(($('HandDetection*0:right.pinky.last.y').d - $('HandDetection*0:right.palm.y').d), 2) );
```

### Python Code
```python
# Distance from right palm to right thumb first joint
math.sqrt( math.pow((__('HandDetection*0:right.thumb.first.x').d - __('HandDetection*0:right.palm.x').d), 2) + math.pow((__('HandDetection*0:right.thumb.first.y').d - __('HandDetection*0:right.palm.y').d), 2) )

# Horizontal distance from right palm to right index second joint
math.fabs(__('HandDetection*0:right.index.second.x').d - __('HandDetection*0:right.palm.x').d)

# Vertical distance from right palm to right middle third joint
math.fabs(__('HandDetection*0:right.middle.third.y').d - __('HandDetection*0:right.palm.y').d)

# Distance from right palm to right ring last joint
math.sqrt( math.pow((__('HandDetection*0:right.ring.last.x').d - __('HandDetection*0:right.palm.x').d), 2) + math.pow((__('HandDetection*0:right.ring.last.y').d - __('HandDetection*0:right.palm.y').d), 2) )

# Distance from right palm to right pinky last joint
math.sqrt( math.pow((__('HandDetection*0:right.pinky.last.x').d - __('HandDetection*0:right.palm.x').d), 2) + math.pow((__('HandDetection*0:right.pinky.last.y').d - __('HandDetection*0:right.palm.y').d), 2) )
```

## Distance Between Two Finger Joints
Returns the distance between two finger joints.

<img src="https://github.com/user-attachments/assets/1e193ef0-4162-4c4b-887c-2a3dc35d4050" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| direction 1 | Dropdown Option | Hand side | right, left |
| finger 1 | Dropdown Option | Finger | thumb, index, middle, ring, pinky |
| joint 1 | Dropdown Option | Finger joint | first, second, third, last |
| direction 2 | Dropdown Option | Hand side | right, left |
| finger 2 | Dropdown Option | Finger | thumb, index, middle, ring, pinky |
| joint 2 | Dropdown Option | Finger joint | first, second, third, last |
| distance | Dropdown Option | Distance type | distance, horizontal distance, vertical distance |

### JavaScript Code
```javascript
// Distance from right thumb first joint to left thumb first joint
Math.sqrt( Math.pow(($('HandDetection*0:left.thumb.first.x').d - $('HandDetection*0:right.thumb.first.x').d), 2) + Math.pow(($('HandDetection*0:left.thumb.first.y').d - $('HandDetection*0:right.thumb.first.y').d), 2) );

// Distance from right thumb first joint to left index second joint
Math.sqrt( Math.pow(($('HandDetection*0:left.index.second.x').d - $('HandDetection*0:right.thumb.first.x').d), 2) + Math.pow(($('HandDetection*0:left.index.second.y').d - $('HandDetection*0:right.thumb.first.y').d), 2) );

// Distance from right thumb first joint to left middle third joint
Math.sqrt( Math.pow(($('HandDetection*0:left.middle.third.x').d - $('HandDetection*0:right.thumb.first.x').d), 2) + Math.pow(($('HandDetection*0:left.middle.third.y').d - $('HandDetection*0:right.thumb.first.y').d), 2) );

// Horizontal distance from right thumb first joint to left ring second joint
Math.abs($('HandDetection*0:left.ring.second.x').d - $('HandDetection*0:right.thumb.first.x').d);

// Vertical distance from right thumb first joint to left pinky second joint
Math.abs($('HandDetection*0:left.pinky.second.y').d - $('HandDetection*0:right.thumb.first.y').d);
```

### Python Code
```python
# Distance from right thumb first joint to left thumb first joint
math.sqrt( math.pow((__('HandDetection*0:left.thumb.first.x').d - __('HandDetection*0:right.thumb.first.x').d), 2) + math.pow((__('HandDetection*0:left.thumb.first.y').d - __('HandDetection*0:right.thumb.first.y').d), 2) )

# Distance from right thumb first joint to left index second joint
math.sqrt( math.pow((__('HandDetection*0:left.index.second.x').d - __('HandDetection*0:right.thumb.first.x').d), 2) + math.pow((__('HandDetection*0:left.index.second.y').d - __('HandDetection*0:right.thumb.first.y').d), 2) )

# Distance from right thumb first joint to left middle third joint
math.sqrt( math.pow((__('HandDetection*0:left.middle.third.x').d - __('HandDetection*0:right.thumb.first.x').d), 2) + math.pow((__('HandDetection*0:left.middle.third.y').d - __('HandDetection*0:right.thumb.first.y').d), 2) )

# Horizontal distance from right thumb first joint to left ring second joint
math.fabs(__('HandDetection*0:left.ring.second.x').d - __('HandDetection*0:right.thumb.first.x').d)

# Vertical distance from right thumb first joint to left pinky second joint
math.fabs(__('HandDetection*0:left.pinky.second.y').d - __('HandDetection*0:right.thumb.first.y').d)
```

## Hand Model State Value
Returns the hand model loading state.  
Returns 0 if not loaded, 1 if loading, and 2 if loading is complete.

<img src="https://github.com/user-attachments/assets/145235c8-ac7d-4657-81c7-400a3035c004" width="100%" height="100%" >

### JavaScript Code
```javascript
// Hand model state value
$('HandDetection*0:model_state').d;
```

### Python Code
```python
# Hand model state value
__('HandDetection*0:model_state').d
```

## Was a Hand Detected?
Returns whether a hand was detected as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/2dbeb02a-15ca-4fb5-808a-8270764e5315" width="50%" height="50%" >

### JavaScript Code
```javascript
// Was a hand detected?
$('HandDetection*0:detected').d;
```

### Python Code
```python
# Was a hand detected?
__('HandDetection*0:detected').d
```