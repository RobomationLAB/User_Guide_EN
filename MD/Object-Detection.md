# Open Dashboard
**Open Dashboard** is not a block that can be used in block coding,  
but it allows you to open a dashboard where you can check how the model used in the extension module is applied.

## Dashboard Screen
When you click Open Dashboard, you can see the following screen.

<img src="https://github.com/user-attachments/assets/18681f75-ccd6-465d-b033-b7f76f1bc1a9" width="100%" height="100%" >

## Detailed Features

### Power
Turns the selected camera on or off.

### Load Model
Loads the trained object detection model.  
This is a required step to use the “Object Detection” extension module.

### Detect
Starts or stops object detection.  
You can choose whether to run it only once with the Once button, or continuously with the Continuous button.  
You can also stop detection using the Stop button.

### Show Result
Displays object detection results on the camera screen.

### Object Data
Displays data values according to the selected object.

#### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| object | Dropdown Option | Object | person, bicycle, car, motorcycle, airplane, bus, train, truck, boat, traffic light, fire hydrant, stop sign, parking meter, bench, bird, cat, dog, horse, sheep, cow, elephant, bear, zebra, giraffe, backpack, umbrella, handbag, tie, suitcase, frisbee, skis, snowboard, sports ball, kite, baseball bat, baseball glove, skateboard, surfboard, tennis racket, bottle, wine glass, cup, fork, knife, spoon, bowl, banana, apple, sandwich, orange, broccoli, carrot, hot dog, pizza, donut, cake, chair, couch, potted plant, bed, dining table, toilet, tv, laptop, mouse, remote, keyboard, cell phone, microwave, oven, toaster, sink, refrigerator, book, clock, vase, scissors, teddy bear, hair drier, toothbrush |

<br>

# Blocks
## Select Camera
Selects the camera to use for the Object Detection module.


<img src="https://github.com/user-attachments/assets/3b2d5e1f-db32-4918-b337-48bdde634524" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| camera | Dropdown Option | Camera to use | Connected camera list |

### JavaScript Code
```javascript
// Set a specific camera for object detection (id is an example)
$('ObjectDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb';
```

### Python Code
```python
# Set a specific camera for object detection (id is an example)
__('ObjectDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb'
```

## Load Object Model
Loads the trained object model. This step is required to use the features of the “Object Detection” module.  
If wait is checked, it waits until model loading is completed.  
However, if wait is checked, it can only be used inside an async function.


<img src="https://github.com/user-attachments/assets/c4f659cc-1e76-45ec-8935-7ab522199211" width="80%" height="80%" >

### JavaScript Code
```javascript
// Load object model | Wait O
$('ObjectDetection*0:load_model').d = 1;
await $('ObjectDetection*0:!load_model').w();

// Load object model | Wait X
$('ObjectDetection*0:load_model').d = 1;
```

### Python Code
```python
# Load object model | Wait O
__('ObjectDetection*0:load_model').d = 1
await __('ObjectDetection*0:!load_model').w()

# Load object model | Wait X
__('ObjectDetection*0:load_model').d = 1
```

## Set Max Number of Objects to Detect
Sets the maximum number of objects that can be detected.  
The range is 0 ~ 10.


<img src="https://github.com/user-attachments/assets/cd5c25ca-7fa3-43b9-b1cd-c8dc064ffaf7" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| pivot | Input | Number of objects to detect | Integer 0 ~ 10 |

### JavaScript Code
```javascript
// Set the max number of objects to 5
$('ObjectDetection*0:maxObjects').d = 5;
```

### Python Code
```python
# Set the max number of objects to 5
__('ObjectDetection*0:maxObjects').d = 5
```

## Set Minimum Detection Confidence
Sets the minimum confidence threshold for object detection.  
Only results with confidence greater than or equal to this value are displayed.  
The confidence range is 0 ~ 1.

<img src="https://github.com/user-attachments/assets/30f50e32-1342-434e-8e6c-3752a475597e" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| reliability | Input | Object detection confidence | Real number 0 ~ 1 |

### JavaScript Code
```javascript
// Set minimum confidence threshold to 0.5
$('ObjectDetection*0:confidenceThreshold').d = 0.5;
```

### Python Code
```python
# Set minimum confidence threshold to 0.5
__('ObjectDetection*0:confidenceThreshold').d = 0.5
```

## Detect Once
Detects objects currently on the screen and displays the result only once.


<img src="https://github.com/user-attachments/assets/1b9ed395-8804-449d-9871-20c2f45079b9" width="70%" height="70%" >

### JavaScript Code
```javascript
// Detect objects once
$('ObjectDetection*0:detect.once').d = 1;
```

### Python Code
```python
# Detect objects once
__('ObjectDetection*0:detect.once').d = 1
```

## Detect Continuously
Starts or stops continuous object detection.  
When continuous detection starts, it keeps tracking and displaying objects on the screen.

<img src="https://github.com/user-attachments/assets/b1f6ce68-e6c3-404f-8976-889330bc4276" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Object detection | Start (1), Stop (0) |

### JavaScript Code
```javascript
// Start continuous detection
$('ObjectDetection*0:detect.continuous').d = 1;

// Stop continuous detection
$('ObjectDetection*0:detect.continuous').d = 0;
```

### Python Code
```python
# Start continuous detection
__('ObjectDetection*0:detect.continuous').d = 1

# Stop continuous detection
__('ObjectDetection*0:detect.continuous').d = 0
```

## Show Object Detection Result
Decides whether to display object detection results on the camera screen.


<img src="https://github.com/user-attachments/assets/484c70dd-1ffe-45b2-8a1c-32d207ad596a" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Show results | Show (1), Hide (0) |

### JavaScript Code
```javascript
// Show detection results
$('ObjectDetection*0:display').d = 1;

// Hide detection results
$('ObjectDetection*0:display').d = 0;
```

### Python Code
```python
# Show detection results
__('ObjectDetection*0:display').d = 1

# Hide detection results
__('ObjectDetection*0:display').d = 0
```

## Object Data
Returns data for the selected object.


<img src="https://github.com/user-attachments/assets/21322e36-751b-4ddf-a9f4-3504b0038724" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| object | Dropdown Option | Object | Person (0), Bicycle (1), Car (2), Motorcycle (3), Airplane (4), Bus (5), Train (6), Truck (7), Boat (8), Traffic light (9), Fire hydrant (10), Stop sign (11), Parking meter (12), Bench (13), Bird (14), Cat (15), Dog (16), Horse (17), Sheep (18), Cow (19), Elephant (20), Bear (21), Zebra (22), Giraffe (23), Backpack (24), Umbrella (25), Handbag (26), Tie (27), Suitcase (28), Frisbee (29), Skis (30), Snowboard (31), Sports ball (32), Kite (33), Baseball bat (34), Baseball glove (35), Skateboard (36), Surfboard (37), Tennis racket (38), Bottle (39), Wine glass (40), Cup (41), Fork (42), Knife (43), Spoon (44), Bowl (45), Banana (46), Apple (47), Sandwich (48), Orange (49), Broccoli (50), Carrot (51), Hot dog (52), Pizza (53), Donut (54), Cake (55), Chair (56), Couch (57), Potted plant (58), Bed (59), Dining table (60), Toilet (61), TV (62), Laptop (63), Mouse (64), Remote (65), Keyboard (66), Cell phone (67), Microwave (68), Oven (69), Toaster (70), Sink (71), Refrigerator (72), Book (73), Clock (74), Vase (75), Scissors (76), Teddy bear (77), Hair drier (78), Toothbrush (79) |
| axis | Dropdown Option | Coordinate axis | x, y |

### JavaScript Code
```javascript
// Person (0) x coordinate
$('ObjectDetection*0:object.x').d[0];

// Toothbrush (79) y coordinate
$('ObjectDetection*0:object.y').d[79];
```

### Python Code
```python
# Person (0) x coordinate
__('ObjectDetection*0:object.x').d[0]

# Toothbrush (79) y coordinate
__('ObjectDetection*0:object.y').d[79]
```

## Bounding Box Data Around Object
Defines the detected object area as a rectangle and returns rectangle data.

<img src="https://github.com/user-attachments/assets/1c659814-045b-4646-b8a2-c6bd80e88cdd" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| object | Dropdown Option | Object | Person (0), Bicycle (1), Car (2), Motorcycle (3), Airplane (4), Bus (5), Train (6), Truck (7), Boat (8), Traffic light (9), Fire hydrant (10), Stop sign (11), Parking meter (12), Bench (13), Bird (14), Cat (15), Dog (16), Horse (17), Sheep (18), Cow (19), Elephant (20), Bear (21), Zebra (22), Giraffe (23), Backpack (24), Umbrella (25), Handbag (26), Tie (27), Suitcase (28), Frisbee (29), Skis (30), Snowboard (31), Sports ball (32), Kite (33), Baseball bat (34), Baseball glove (35), Skateboard (36), Surfboard (37), Tennis racket (38), Bottle (39), Wine glass (40), Cup (41), Fork (42), Knife (43), Spoon (44), Bowl (45), Banana (46), Apple (47), Sandwich (48), Orange (49), Broccoli (50), Carrot (51), Hot dog (52), Pizza (53), Donut (54), Cake (55), Chair (56), Couch (57), Potted plant (58), Bed (59), Dining table (60), Toilet (61), TV (62), Laptop (63), Mouse (64), Remote (65), Keyboard (66), Cell phone (67), Microwave (68), Oven (69), Toaster (70), Sink (71), Refrigerator (72), Book (73), Clock (74), Vase (75), Scissors (76), Teddy bear (77), Hair drier (78), Toothbrush (79) |
| axis | Dropdown Option | Rectangle data | min_x, max_x, min_y, max_y, width, height, area |

### JavaScript Code
```javascript
// Bus (5) rectangle min x
$('ObjectDetection*0:object.face.min_x').d[5];

// Bus (5) rectangle max x
$('ObjectDetection*0:object.face.max_x').d[5];

// Bus (5) rectangle min y
$('ObjectDetection*0:object.face.min_y').d[5];

// Bus (5) rectangle max y
$('ObjectDetection*0:object.face.max_y').d[5];

// Bus (5) rectangle width
$('ObjectDetection*0:object.face.width').d[5];

// Bus (5) rectangle height
$('ObjectDetection*0:object.face.height').d[5];

// Bus (5) rectangle area
$('ObjectDetection*0:object.face.area').d[5];
```

### Python Code
```python
# Bus (5) rectangle min x
__('ObjectDetection*0:object.face.min_x').d[5]

# Bus (5) rectangle max x
__('ObjectDetection*0:object.face.max_x').d[5]

# Bus (5) rectangle min y
__('ObjectDetection*0:object.face.min_y').d[5]

# Bus (5) rectangle max y
__('ObjectDetection*0:object.face.max_y').d[5]

# Bus (5) rectangle width
__('ObjectDetection*0:object.face.width').d[5]

# Bus (5) rectangle height
__('ObjectDetection*0:object.face.height').d[5]

# Bus (5) rectangle area
__('ObjectDetection*0:object.face.area').d[5]
```

## Distance Between Two Objects
Returns the distance between two selected objects.


<img src="https://github.com/user-attachments/assets/3944cd18-daa4-4e17-9b25-67d62c6ee33e" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| object 1 | Dropdown Option | Object | Person (0), Bicycle (1), Car (2), Motorcycle (3), Airplane (4), Bus (5), Train (6), Truck (7), Boat (8), Traffic light (9), Fire hydrant (10), Stop sign (11), Parking meter (12), Bench (13), Bird (14), Cat (15), Dog (16), Horse (17), Sheep (18), Cow (19), Elephant (20), Bear (21), Zebra (22), Giraffe (23), Backpack (24), Umbrella (25), Handbag (26), Tie (27), Suitcase (28), Frisbee (29), Skis (30), Snowboard (31), Sports ball (32), Kite (33), Baseball bat (34), Baseball glove (35), Skateboard (36), Surfboard (37), Tennis racket (38), Bottle (39), Wine glass (40), Cup (41), Fork (42), Knife (43), Spoon (44), Bowl (45), Banana (46), Apple (47), Sandwich (48), Orange (49), Broccoli (50), Carrot (51), Hot dog (52), Pizza (53), Donut (54), Cake (55), Chair (56), Couch (57), Potted plant (58), Bed (59), Dining table (60), Toilet (61), TV (62), Laptop (63), Mouse (64), Remote (65), Keyboard (66), Cell phone (67), Microwave (68), Oven (69), Toaster (70), Sink (71), Refrigerator (72), Book (73), Clock (74), Vase (75), Scissors (76), Teddy bear (77), Hair drier (78), Toothbrush (79) |
| object 2 | Dropdown Option | Object | Person (0), Bicycle (1), Car (2), Motorcycle (3), Airplane (4), Bus (5), Train (6), Truck (7), Boat (8), Traffic light (9), Fire hydrant (10), Stop sign (11), Parking meter (12), Bench (13), Bird (14), Cat (15), Dog (16), Horse (17), Sheep (18), Cow (19), Elephant (20), Bear (21), Zebra (22), Giraffe (23), Backpack (24), Umbrella (25), Handbag (26), Tie (27), Suitcase (28), Frisbee (29), Skis (30), Snowboard (31), Sports ball (32), Kite (33), Baseball bat (34), Baseball glove (35), Skateboard (36), Surfboard (37), Tennis racket (38), Bottle (39), Wine glass (40), Cup (41), Fork (42), Knife (43), Spoon (44), Bowl (45), Banana (46), Apple (47), Sandwich (48), Orange (49), Broccoli (50), Carrot (51), Hot dog (52), Pizza (53), Donut (54), Cake (55), Chair (56), Couch (57), Potted plant (58), Bed (59), Dining table (60), Toilet (61), TV (62), Laptop (63), Mouse (64), Remote (65), Keyboard (66), Cell phone (67), Microwave (68), Oven (69), Toaster (70), Sink (71), Refrigerator (72), Book (73), Clock (74), Vase (75), Scissors (76), Teddy bear (77), Hair drier (78), Toothbrush (79) |
| distance | Dropdown Option | Distance type | distance, horizontal distance, vertical distance |

### JavaScript Code
```javascript
// Distance from person (0) to person (0)
Math.sqrt( Math.pow(($('ObjectDetection*0:object.x').d[0] - $('ObjectDetection*0:object.x').d[0]), 2) + Math.pow(($('ObjectDetection*0:object.y').d[0] - $('ObjectDetection*0:object.y').d[0]), 2) );

// Horizontal distance from person (0) to bicycle (1)
Math.abs($('ObjectDetection*0:object.x').d[1] - $('ObjectDetection*0:object.x').d[0]);

// Vertical distance from car (2) to bicycle (1)
Math.abs($('ObjectDetection*0:object.y').d[1] - $('ObjectDetection*0:object.y').d[2]);
```

### Python Code
```python
# Distance from person (0) to person (0)
math.sqrt( math.pow((__('ObjectDetection*0:object.x').d[0] - __('ObjectDetection*0:object.x').d[0]), 2) + math.pow((__('ObjectDetection*0:object.y').d[0] - __('ObjectDetection*0:object.y').d[0]), 2) )

# Horizontal distance from person (0) to bicycle (1)
math.fabs(__('ObjectDetection*0:object.x').d[1] - __('ObjectDetection*0:object.x').d[0])

# Vertical distance from car (2) to bicycle (1)
math.fabs(__('ObjectDetection*0:object.y').d[1] - __('ObjectDetection*0:object.y').d[2])
```

## Object Confidence (Reliability)
Returns the confidence (reliability) that the selected object is correct.  
The returned value is a real number between 0 and 1.


<img src="https://github.com/user-attachments/assets/dfa8cc7c-287f-45d8-b8ee-51cd3c891f0f" width="60%" height="60%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| object | Dropdown Option | Object | Person (0), Bicycle (1), Car (2), Motorcycle (3), Airplane (4), Bus (5), Train (6), Truck (7), Boat (8), Traffic light (9), Fire hydrant (10), Stop sign (11), Parking meter (12), Bench (13), Bird (14), Cat (15), Dog (16), Horse (17), Sheep (18), Cow (19), Elephant (20), Bear (21), Zebra (22), Giraffe (23), Backpack (24), Umbrella (25), Handbag (26), Tie (27), Suitcase (28), Frisbee (29), Skis (30), Snowboard (31), Sports ball (32), Kite (33), Baseball bat (34), Baseball glove (35), Skateboard (36), Surfboard (37), Tennis racket (38), Bottle (39), Wine glass (40), Cup (41), Fork (42), Knife (43), Spoon (44), Bowl (45), Banana (46), Apple (47), Sandwich (48), Orange (49), Broccoli (50), Carrot (51), Hot dog (52), Pizza (53), Donut (54), Cake (55), Chair (56), Couch (57), Potted plant (58), Bed (59), Dining table (60), Toilet (61), TV (62), Laptop (63), Mouse (64), Remote (65), Keyboard (66), Cell phone (67), Microwave (68), Oven (69), Toaster (70), Sink (71), Refrigerator (72), Book (73), Clock (74), Vase (75), Scissors (76), Teddy bear (77), Hair drier (78), Toothbrush (79) |

### JavaScript Code
```javascript
// Confidence that the predicted object is a person (0)
$('ObjectDetection*0:object.confidence').d[0];

// Confidence that the predicted object is a bicycle (1)
$('ObjectDetection*0:object.confidence').d[1];
```

### Python Code
```python
# Confidence that the predicted object is a person (0)
__('ObjectDetection*0:object.confidence').d[0]

# Confidence that the predicted object is a bicycle (1)
__('ObjectDetection*0:object.confidence').d[1]
```

## Model Loading State
Returns the model loading state.  
Returns 0 if not loaded yet, 1 if loading, and 2 if loading is complete.


<img src="https://github.com/user-attachments/assets/39036b2b-5b40-40cd-bebc-f2e5457d8ef5" width="90%" height="90%" >


### JavaScript Code
```javascript
// Model loading state value
$('ObjectDetection*0:model_state').d;
```

### Python Code
```python
# Model loading state value
__('ObjectDetection*0:model_state').d
```

## Was Any Object Detected?
Returns whether any object was detected as **True (1) / False (0)**.


<img src="https://github.com/user-attachments/assets/823f1712-59f3-4398-a38a-daeff14cd45c" width="60%" height="60%" >


### JavaScript Code
```javascript
// Was any object detected?
$('ObjectDetection*0:detected').d;
```

### Python Code
```python
# Was any object detected?
__('ObjectDetection*0:detected').d
```

## Was ~ Detected?
Returns whether the selected object was detected as **True (1) / False (0)**.


<img src="https://github.com/user-attachments/assets/ce3a93aa-1996-446b-83b7-a83300abb3aa" width="60%" height="60%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| object | Dropdown Option | Object | Person (0), Bicycle (1), Car (2), Motorcycle (3), Airplane (4), Bus (5), Train (6), Truck (7), Boat (8), Traffic light (9), Fire hydrant (10), Stop sign (11), Parking meter (12), Bench (13), Bird (14), Cat (15), Dog (16), Horse (17), Sheep (18), Cow (19), Elephant (20), Bear (21), Zebra (22), Giraffe (23), Backpack (24), Umbrella (25), Handbag (26), Tie (27), Suitcase (28), Frisbee (29), Skis (30), Snowboard (31), Sports ball (32), Kite (33), Baseball bat (34), Baseball glove (35), Skateboard (36), Surfboard (37), Tennis racket (38), Bottle (39), Wine glass (40), Cup (41), Fork (42), Knife (43), Spoon (44), Bowl (45), Banana (46), Apple (47), Sandwich (48), Orange (49), Broccoli (50), Carrot (51), Hot dog (52), Pizza (53), Donut (54), Cake (55), Chair (56), Couch (57), Potted plant (58), Bed (59), Dining table (60), Toilet (61), TV (62), Laptop (63), Mouse (64), Remote (65), Keyboard (66), Cell phone (67), Microwave (68), Oven (69), Toaster (70), Sink (71), Refrigerator (72), Book (73), Clock (74), Vase (75), Scissors (76), Teddy bear (77), Hair drier (78), Toothbrush (79) |

### JavaScript Code
```javascript
// Was person (0) detected?
$('ObjectDetection*0:object.confidence').d[0] >= $('ObjectDetection*0:confidenceThreshold');
```

### Python Code
```python
# Was person (0) detected?
__('ObjectDetection*0:object.confidence').d[0] >= __('ObjectDetection*0:confidenceThreshold').d