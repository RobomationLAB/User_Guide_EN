# Open Dashboard
**Open Dashboard** is not a block that can be used in block coding,  
but it allows you to open a dashboard where you can check how the model used in the extension module is applied.

## Dashboard Screen
When you click Open Dashboard, you can see the following screen.  

<img src="https://github.com/user-attachments/assets/53d8b1b5-c56e-4f50-b2dd-5b668143bf63" width="100%" height="100%" >

## Detailed Features

### Power
Turns the selected camera on or off.

### Load Model 
Loads the trained face model. This is a required step to use the **Face Detection** extension module.

### Detect
Starts or stops face detection.  
You can choose whether to run it only once with the Once button, or continuously with the Continuous button.  
You can also stop detection using the Stop button.

### Show Result
Displays face detection results on the camera screen.

### Sensory Data
Displays the face data values found by face detection.  
You can check the x, y coordinates of the selected face part.

#### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| part | Dropdown Option | Face part | face, ear, eye, nose, mouth |

<br>

# Blocks
## Select Camera
Selects the camera to use for the Face Detection module.

<img src="https://github.com/user-attachments/assets/5e6dded1-b445-450f-b737-be82d7f5d23d" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|camera|Dropdown Option|Camera to use|Connected camera list|

### JavaScript Code
```javascript
// Set a specific camera for face detection (id is an example)
$('FaceDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb';
```

### Python Code
```python
# Set a specific camera for face detection (id is an example)
__('FaceDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb'
```

## Load Face Model
Loads the trained face model. This must be done to use the features of the Face Detection module.  
If **Wait** is checked, it waits until the model finishes loading.  
If **Wait** is checked, it can only be used inside an async function.

<img src="https://github.com/user-attachments/assets/8200b1d8-6e67-4550-9ecd-bef6d5fc45c3" width="80%" height="80%" >

### JavaScript Code
```javascript
// Load face model | Wait: O
$('FaceDetection*0:load_model').d = 1;
await $('FaceDetection*0:!load_model').w();

// Load face model | Wait: X
$('FaceDetection*0:load_model').d = 1;
```

### Python Code
```python
# Load face model | Wait: O
__('FaceDetection*0:load_model').d = 1
await __('FaceDetection*0:!load_model').w()

# Load face model | Wait: X
__('FaceDetection*0:load_model').d = 1
```

## Detect Face Once
Detects faces currently on the screen and displays them only once.

<img src="https://github.com/user-attachments/assets/dd8930b0-3a14-4a39-b5dd-57a9ffa42d53" width="70%" height="70%" >

### JavaScript Code
```javascript
// Detect face once
$('FaceDetection*0:detect.once').d = 1;
```

### Python Code
```python
# Detect face once
__('FaceDetection*0:detect.once').d = 1
```

## Detect Face Continuously
Starts or stops continuous face detection.  
When continuous detection starts, it keeps tracking and displaying faces currently on the screen.


<img src="https://github.com/user-attachments/assets/af227fc6-7936-47a1-af06-6589109268b3" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown Option|Face detection|Start (1), Stop (0)|

### JavaScript Code
```javascript
// Start continuous face detection
$('FaceDetection*0:detect.continuous').d = 1;

// Stop continuous face detection
$('FaceDetection*0:detect.continuous').d = 0;
```

### Python Code
```python
# Start continuous face detection
__('FaceDetection*0:detect.continuous').d = 1

# Stop continuous face detection
__('FaceDetection*0:detect.continuous').d = 0
```

## Show Face Detection Result
Decides whether to display face detection results on the camera screen.

<img src="https://github.com/user-attachments/assets/6075b738-2ca9-4065-897e-ceae9568dbbb" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown Option|Show results|Show (1), Hide (0)|

### JavaScript Code
```javascript
// Show face detection results
$('FaceDetection*0:display').d = 1;

// Hide face detection results
$('FaceDetection*0:display').d = 0;
```

### Python Code
```python
# Show face detection results
__('FaceDetection*0:display').d = 1

# Hide face detection results
__('FaceDetection*0:display').d = 0
```

## Face Data
Returns the face data obtained from face detection.


<img src="https://github.com/user-attachments/assets/bba10b91-cdd0-4666-99d1-b8e797499e2a" width="90%" height="90%" >

| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| part | Dropdown Option | Face part | face, eye.left, eye.right, ear.left, ear.right, nose, mouth |
| axis | Dropdown Option | Coordinate axis | x, y |

### JavaScript Code
```javascript
// Face x coordinate
$('FaceDetection*0:face.x').d;

// Face y coordinate
$('FaceDetection*0:face.y').d;

// Left eye x coordinate
$('FaceDetection*0:eye.left.x').d;

// Left eye y coordinate
$('FaceDetection*0:eye.left.y').d;

// Right eye x coordinate
$('FaceDetection*0:eye.right.x').d;

// Right eye y coordinate
$('FaceDetection*0:eye.right.y').d;

// Left ear x coordinate
$('FaceDetection*0:ear.left.x').d;

// Left ear y coordinate
$('FaceDetection*0:ear.left.y').d;

// Right ear x coordinate
$('FaceDetection*0:ear.right.x').d;

// Right ear y coordinate
$('FaceDetection*0:ear.right.y').d;

// Nose x coordinate
$('FaceDetection*0:nose.x').d;

// Nose y coordinate
$('FaceDetection*0:nose.y').d;

// Mouth x coordinate
$('FaceDetection*0:mouth.x').d;

// Mouth y coordinate
$('FaceDetection*0:mouth.y').d;
```

### Python Code
```python
# Face x coordinate
__('FaceDetection*0:face.x').d

# Face y coordinate
__('FaceDetection*0:face.y').d

# Left eye x coordinate
__('FaceDetection*0:eye.left.x').d

# Left eye y coordinate
__('FaceDetection*0:eye.left.y').d

# Right eye x coordinate
__('FaceDetection*0:eye.right.x').d

# Right eye y coordinate
__('FaceDetection*0:eye.right.y').d

# Left ear x coordinate
__('FaceDetection*0:ear.left.x').d

# Left ear y coordinate
__('FaceDetection*0:ear.left.y').d

# Right ear x coordinate
__('FaceDetection*0:ear.right.x').d

# Right ear y coordinate
__('FaceDetection*0:ear.right.y').d

# Nose x coordinate
__('FaceDetection*0:nose.x').d

# Nose y coordinate
__('FaceDetection*0:nose.y').d

# Mouth x coordinate
__('FaceDetection*0:mouth.x').d

# Mouth y coordinate
__('FaceDetection*0:mouth.y').d
```

## Face Bounding Box Data
Defines the area around the detected face as a rectangle and returns that rectangle’s data.

<img src="https://github.com/user-attachments/assets/e6499016-67de-46f5-aa08-a8fd1f72844e" width="100%" height="100%" >

| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| data | Dropdown Option | Rectangle data | min_x, max_x, min_y, max_y, width, height, area |

### JavaScript Code
```javascript
// Face rectangle min x
$('FaceDetection*0:face.min_x').d;

// Face rectangle max x
$('FaceDetection*0:face.max_x').d;

// Face rectangle min y
$('FaceDetection*0:face.min_y').d;

// Face rectangle max y
$('FaceDetection*0:face.max_y').d;

// Face rectangle width
$('FaceDetection*0:face.width').d;

// Face rectangle height
$('FaceDetection*0:face.height').d;

// Face rectangle area
$('FaceDetection*0:face.area').d;
```

### Python Code
```python
# Face rectangle min x
__('FaceDetection*0:face.min_x').d

# Face rectangle max x
__('FaceDetection*0:face.max_x').d

# Face rectangle min y
__('FaceDetection*0:face.min_y').d

# Face rectangle max y
__('FaceDetection*0:face.max_y').d

# Face rectangle width
__('FaceDetection*0:face.width').d

# Face rectangle height
__('FaceDetection*0:face.height').d

# Face rectangle area
__('FaceDetection*0:face.area').d
```

## Distance Between Face Parts
Returns the distance between two face parts using face detection data.


<img src="https://github.com/user-attachments/assets/faab7721-a4f9-4b2e-8bad-132155da9c5f" width="100%" height="100%" >

| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| part1 | Dropdown Option | Face part | face, eye.left, eye.right, ear.left, ear.right, nose, mouth |
| part2 | Dropdown Option | Face part | face, eye.left, eye.right, ear.left, ear.right, nose, mouth |
| distance | Dropdown Option | Distance type | distance, horizontal distance, vertical distance |

### JavaScript Code
```javascript
// Distance from left eye to left eye
Math.sqrt( Math.pow(($('FaceDetection*0:eye.left.x').d - $('FaceDetection*0:eye.left.x').d), 2) + Math.pow(($('FaceDetection*0:eye.left.y').d - $('FaceDetection*0:eye.left.y').d), 2) );

// Horizontal distance from left eye to right eye
Math.abs($('FaceDetection*0:eye.right.x').d - $('FaceDetection*0:eye.left.x').d);

// Vertical distance from left eye to left ear
Math.abs($('FaceDetection*0:ear.left.y').d - $('FaceDetection*0:eye.left.y').d);

// Distance from left eye to right ear
Math.sqrt( Math.pow(($('FaceDetection*0:ear.right.x').d - $('FaceDetection*0:eye.left.x').d), 2) + Math.pow(($('FaceDetection*0:ear.right.y').d - $('FaceDetection*0:eye.left.y').d), 2) );

// Distance from left eye to nose
Math.sqrt( Math.pow(($('FaceDetection*0:nose.x').d - $('FaceDetection*0:eye.left.x').d), 2) + Math.pow(($('FaceDetection*0:nose.y').d - $('FaceDetection*0:eye.left.y').d), 2) );

// Distance from left eye to mouth
Math.sqrt( Math.pow(($('FaceDetection*0:mouth.x').d - $('FaceDetection*0:eye.left.x').d), 2) + Math.pow(($('FaceDetection*0:mouth.y').d - $('FaceDetection*0:eye.left.y').d), 2) );
```

### Python Code
```python
# Distance from left eye to left eye
math.sqrt( math.pow((__('FaceDetection*0:eye.left.x').d - __('FaceDetection*0:eye.left.x').d), 2) + math.pow((__('FaceDetection*0:eye.left.y').d - __('FaceDetection*0:eye.left.y').d), 2) )

# Horizontal distance from left eye to right eye
math.fabs(__('FaceDetection*0:eye.right.x').d - __('FaceDetection*0:eye.left.x').d)

# Vertical distance from left eye to left ear
math.fabs(__('FaceDetection*0:ear.left.y').d - __('FaceDetection*0:eye.left.y').d)

# Distance from left eye to right ear
math.sqrt( math.pow((__('FaceDetection*0:ear.right.x').d - __('FaceDetection*0:eye.left.x').d), 2) + math.pow((__('FaceDetection*0:ear.right.y').d - __('FaceDetection*0:eye.left.y').d), 2) )

# Distance from left eye to nose
math.sqrt( math.pow((__('FaceDetection*0:nose.x').d - __('FaceDetection*0:eye.left.x').d), 2) + math.pow((__('FaceDetection*0:nose.y').d - __('FaceDetection*0:eye.left.y').d), 2) )

# Distance from left eye to mouth
math.sqrt( math.pow((__('FaceDetection*0:mouth.x').d - __('FaceDetection*0:eye.left.x').d), 2) + math.pow((__('FaceDetection*0:mouth.y').d - __('FaceDetection*0:eye.left.y').d), 2) )
```

## Face Model State Value
Returns the face model loading state.  
Returns 0 if not loaded, 1 if loading, and 2 if loading is complete.

<img src="https://github.com/user-attachments/assets/63c81e92-fb2e-4f11-aafe-938460d2003f" width="80%" height="80%" >

### JavaScript Code
```javascript
// Face model state value
$('FaceDetection*0:model_state').d;
```

### Python Code
```python
# Face model state value
__('FaceDetection*0:model_state').d
```

## Was a Face Detected?
Returns whether a face was detected as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/c2a6c2a0-f4e1-4148-b8b3-48937e51aa9d" width="60%" height="60%" >

### JavaScript Code
```javascript
// Was a face detected?
$('FaceDetection*0:detected').d;
```

### Python Code
```python
# Was a face detected?
__('FaceDetection*0:detected').d
```