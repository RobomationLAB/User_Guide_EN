# Open Dashboard
**Open Dashboard** is not a block that can be used in block coding,  
but it allows you to open a dashboard where you can check how the model used in the extension module is applied.

## Dashboard Screen
When you click Open Dashboard, you can see the following screen.

<img src="https://github.com/user-attachments/assets/c443dd1d-5911-42a2-b150-cb5d87d1d54d" width="100%" height="100%" >

## Detailed Features

### Power
Turns the selected camera on or off.

### Load Model
Loads the trained detailed face detection model.  
This is a required step to use the “Detailed Face Detection” extension module.

### Detect
Starts or stops detailed face detection.  
You can choose whether to run it only once with the Once button, or continuously with the Continuous button.  
You can also stop detection using the Stop button.

### Show Result
Displays detailed face detection results on the camera screen.

### Sensory Data
Displays face data values detected by face detection.  
You can check the x,y coordinates of the selected face part.

#### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| part | Dropdown Option | Face part | face, left eye, right eye, left pupil, right pupil, nose, mouth, left lip, right lip, upper lip, lower lip |

<br>

# Blocks
## Select Camera
Selects the camera to use for the Detailed Face Detection module.


<img src="https://github.com/user-attachments/assets/4878836f-b961-48f5-aca3-69258e2da339" width="100%" height="100%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| camera | Dropdown Option | Camera to use | Connected camera list |

### JavaScript Code
```javascript
// Set a specific camera for detailed face detection (id is an example)
$('DetailedFaceDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb';
```

### Python Code
```python
# Set a specific camera for detailed face detection (id is an example)
__('DetailedFaceDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb'
```

## Load Face Model
Loads the trained face model. This step is required to use the features of the “Detailed Face Detection” module.  
If wait is checked, it waits until model loading is completed.  
However, if wait is checked, it can only be used inside an async function.


<img src="https://github.com/user-attachments/assets/dfc81a58-efdf-439c-88cb-b31bcf1bf208" width="80%" height="80%" >

### JavaScript Code
```javascript
// Load face model | Wait O
$('DetailedFaceDetection*0:load_model').d = 1;
await $('DetailedFaceDetection*0:!load_model').w();

// Load face model | Wait X
$('DetailedFaceDetection*0:load_model').d = 1;
```

### Python Code
```python
# Load face model | Wait O
__('DetailedFaceDetection*0:load_model').d = 1
await __('DetailedFaceDetection*0:!load_model').w()

# Load face model | Wait X
__('DetailedFaceDetection*0:load_model').d = 1
```

## Detect Face Once
Detects faces currently on the screen and displays the result only once.


<img src="https://github.com/user-attachments/assets/7bc48397-2247-43e2-8117-1e900c3b02f6" width="70%" height="70%" >

### JavaScript Code
```javascript
// Detect face once
$('DetailedFaceDetection*0:detect.once').d = 1;
```

### Python Code
```python
# Detect face once
__('DetailedFaceDetection*0:detect.once').d = 1
```

## Detect Face Continuously
Starts or stops continuous face detection.  
When continuous detection starts, it keeps tracking and displaying faces on the screen.


<img src="https://github.com/user-attachments/assets/919f73c4-ee73-44b0-af5c-fc53f5189472" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Face detection | Start (1), Stop (0) |

### JavaScript Code
```javascript
// Start continuous face detection
$('DetailedFaceDetection*0:detect.continuous').d = 1;

// Stop continuous face detection
$('DetailedFaceDetection*0:detect.continuous').d = 0;
```

### Python Code
```python
# Start continuous face detection
__('DetailedFaceDetection*0:detect.continuous').d = 1

# Stop continuous face detection
__('DetailedFaceDetection*0:detect.continuous').d = 0
```

## Show Detailed Face Detection Result
Decides whether to display detailed face detection results on the camera screen.


<img src="https://github.com/user-attachments/assets/5288291e-423f-49ef-8bf0-361c7225e118" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Show results | Show (1), Hide (0) |

### JavaScript Code
```javascript
// Show detailed face detection results
$('DetailedFaceDetection*0:display').d = 1;

// Hide detailed face detection results
$('DetailedFaceDetection*0:display').d = 0;
```

### Python Code
```python
# Show detailed face detection results
__('DetailedFaceDetection*0:display').d = 1

# Hide detailed face detection results
__('DetailedFaceDetection*0:display').d = 0
```

## Face Data
Returns face data obtained from face detection.


<img src="https://github.com/user-attachments/assets/05d9f82b-42c2-4c7e-ad59-e772f997b2dd" width="80%" height="80%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| part | Dropdown Option | Face part | Face (face), Left eye (eye.left), Right eye (eye.right), Left pupil (pupil.left), Right pupil (pupil.right), Nose (nose), Mouth (mouth), Left lip corner (lip.left), Right lip corner (lip.right), Upper lip (lip.up), Lower lip (lip.down) |
| axis | Dropdown Option | Coordinate | x, y |

### JavaScript Code
```javascript
// Face x coordinate
$('DetailedFaceDetection*0:face.x').d;

// Face y coordinate
$('DetailedFaceDetection*0:face.y').d;

// Left eye x coordinate
$('DetailedFaceDetection*0:eye.left.x').d;

// Left eye y coordinate
$('DetailedFaceDetection*0:eye.left.y').d;

// Right eye x coordinate
$('DetailedFaceDetection*0:eye.right.x').d;

// Right eye y coordinate
$('DetailedFaceDetection*0:eye.right.y').d;

// Left pupil x coordinate
$('DetailedFaceDetection*0:pupil.left.x').d;

// Left pupil y coordinate
$('DetailedFaceDetection*0:pupil.left.y').d;

// Right pupil x coordinate
$('DetailedFaceDetection*0:pupil.right.x').d;

// Right pupil y coordinate
$('DetailedFaceDetection*0:pupil.right.y').d;

// Nose x coordinate
$('DetailedFaceDetection*0:nose.x').d;

// Nose y coordinate
$('DetailedFaceDetection*0:nose.y').d;

// Mouth x coordinate
$('DetailedFaceDetection*0:mouth.x').d;

// Mouth y coordinate
$('DetailedFaceDetection*0:mouth.y').d;

// Left lip corner x coordinate
$('DetailedFaceDetection*0:lip.left.x').d;

// Left lip corner y coordinate
$('DetailedFaceDetection*0:lip.left.y').d;

// Right lip corner x coordinate
$('DetailedFaceDetection*0:lip.right.x').d;

// Right lip corner y coordinate
$('DetailedFaceDetection*0:lip.right.y').d;

// Upper lip x coordinate
$('DetailedFaceDetection*0:lip.up.x').d;

// Upper lip y coordinate
$('DetailedFaceDetection*0:lip.up.y').d;

// Lower lip x coordinate
$('DetailedFaceDetection*0:lip.down.x').d;

// Lower lip y coordinate
$('DetailedFaceDetection*0:lip.down.y').d;
```

### Python Code
```python
# Face x coordinate
__('DetailedFaceDetection*0:face.x').d

# Face y coordinate
__('DetailedFaceDetection*0:face.y').d

# Left eye x coordinate
__('DetailedFaceDetection*0:eye.left.x').d

# Left eye y coordinate
__('DetailedFaceDetection*0:eye.left.y').d

# Right eye x coordinate
__('DetailedFaceDetection*0:eye.right.x').d

# Right eye y coordinate
__('DetailedFaceDetection*0:eye.right.y').d

# Left pupil x coordinate
__('DetailedFaceDetection*0:pupil.left.x').d

# Left pupil y coordinate
__('DetailedFaceDetection*0:pupil.left.y').d

# Right pupil x coordinate
__('DetailedFaceDetection*0:pupil.right.x').d

# Right pupil y coordinate
__('DetailedFaceDetection*0:pupil.right.y').d

# Nose x coordinate
__('DetailedFaceDetection*0:nose.x').d

# Nose y coordinate
__('DetailedFaceDetection*0:nose.y').d

# Mouth x coordinate
__('DetailedFaceDetection*0:mouth.x').d

# Mouth y coordinate
__('DetailedFaceDetection*0:mouth.y').d

# Left lip corner x coordinate
__('DetailedFaceDetection*0:lip.left.x').d

# Left lip corner y coordinate
__('DetailedFaceDetection*0:lip.left.y').d

# Right lip corner x coordinate
__('DetailedFaceDetection*0:lip.right.x').d

# Right lip corner y coordinate
__('DetailedFaceDetection*0:lip.right.y').d

# Upper lip x coordinate
__('DetailedFaceDetection*0:lip.up.x').d

# Upper lip y coordinate
__('DetailedFaceDetection*0:lip.up.y').d

# Lower lip x coordinate
__('DetailedFaceDetection*0:lip.down.x').d

# Lower lip y coordinate
__('DetailedFaceDetection*0:lip.down.y').d
```

## Bounding Box Data Around Face
Defines the detected face area as a rectangle and returns rectangle data.

<img src="https://github.com/user-attachments/assets/e8e43ed5-6eb0-4e68-beee-4f6b1029fb18" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| part | Dropdown Option | Face part | Face (face), Left eye (eye.left), Right eye (eye.right), Mouth (mouth) |
| data | Dropdown Option | Bounding box data | min_x, max_x, min_y, max_y, width, height, area |

### JavaScript Code
```javascript
// Face bounding box min x
$('DetailedFaceDetection*0:face.min_x').d;

// Face bounding box max x
$('DetailedFaceDetection*0:face.max_x').d;

// Face bounding box min y
$('DetailedFaceDetection*0:face.min_y').d;

// Face bounding box max y
$('DetailedFaceDetection*0:face.max_y').d;

// Face bounding box width
$('DetailedFaceDetection*0:face.width').d;

// Face bounding box height
$('DetailedFaceDetection*0:face.height').d;

// Face bounding box area
$('DetailedFaceDetection*0:face.area').d;

// Left eye bounding box min x
$('DetailedFaceDetection*0:eye.left.min_x').d;

// Right eye bounding box min x
$('DetailedFaceDetection*0:eye.right.min_x').d;

// Mouth bounding box min x
$('DetailedFaceDetection*0:mouth.min_x').d;
```

### Python Code
```python
# Face bounding box min x
__('DetailedFaceDetection*0:face.min_x').d

# Face bounding box max x
__('DetailedFaceDetection*0:face.max_x').d

# Face bounding box min y
__('DetailedFaceDetection*0:face.min_y').d

# Face bounding box max y
__('DetailedFaceDetection*0:face.max_y').d

# Face bounding box width
__('DetailedFaceDetection*0:face.width').d

# Face bounding box height
__('DetailedFaceDetection*0:face.height').d

# Face bounding box area
__('DetailedFaceDetection*0:face.area').d

# Left eye bounding box min x
__('DetailedFaceDetection*0:eye.left.min_x').d

# Right eye bounding box min x
__('DetailedFaceDetection*0:eye.right.min_x').d

# Mouth bounding box min x
__('DetailedFaceDetection*0:mouth.min_x').d
```

## Distance Between Face Elements
Returns the distance between two face elements using face data detected by face detection.


<img src="https://github.com/user-attachments/assets/3dd8c7b1-4c80-49ed-a524-faf881f75c55" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| part 1 | Dropdown Option | Face part | Face (face), Left eye (eye.left), Right eye (eye.right), Left pupil (pupil.left), Right pupil (pupil.right), Nose (nose), Mouth (mouth), Left lip corner (lip.left), Right lip corner (lip.right), Upper lip (lip.up), Lower lip (lip.down) |
| part 2 | Dropdown Option | Face part | Face (face), Left eye (eye.left), Right eye (eye.right), Left pupil (pupil.left), Right pupil (pupil.right), Nose (nose), Mouth (mouth), Left lip corner (lip.left), Right lip corner (lip.right), Upper lip (lip.up), Lower lip (lip.down) |
| distance | Dropdown Option | Distance type | distance, horizontal distance, vertical distance |

### JavaScript Code
```javascript
// Distance from left eye to left eye
Math.sqrt( Math.pow(($('DetailedFaceDetection*0:eye.left.x').d - $('DetailedFaceDetection*0:eye.left.x').d), 2) + Math.pow(($('DetailedFaceDetection*0:eye.left.y').d - $('DetailedFaceDetection*0:eye.left.y').d), 2) );

// Distance from left eye to right eye
Math.sqrt( Math.pow(($('DetailedFaceDetection*0:eye.right.x').d - $('DetailedFaceDetection*0:eye.left.x').d), 2) + Math.pow(($('DetailedFaceDetection*0:eye.right.y').d - $('DetailedFaceDetection*0:eye.left.y').d), 2) );

// Horizontal distance from left eye to left pupil
Math.abs($('DetailedFaceDetection*0:pupil.left.x').d - $('DetailedFaceDetection*0:eye.left.x').d);

// Horizontal distance from left eye to right pupil
Math.abs($('DetailedFaceDetection*0:pupil.right.x').d - $('DetailedFaceDetection*0:eye.left.x').d);

// Vertical distance from left eye to nose
Math.abs($('DetailedFaceDetection*0:nose.y').d - $('DetailedFaceDetection*0:eye.left.y').d);

// Vertical distance from left eye to mouth
Math.abs($('DetailedFaceDetection*0:mouth.y').d - $('DetailedFaceDetection*0:eye.left.y').d);

// Distance from left eye to left lip corner
Math.sqrt( Math.pow(($('DetailedFaceDetection*0:lip.left.x').d - $('DetailedFaceDetection*0:eye.left.x').d), 2) + Math.pow(($('DetailedFaceDetection*0:lip.left.y').d - $('DetailedFaceDetection*0:eye.left.y').d), 2) );

// Distance from left eye to right lip corner
Math.sqrt( Math.pow(($('DetailedFaceDetection*0:lip.right.x').d - $('DetailedFaceDetection*0:eye.left.x').d), 2) + Math.pow(($('DetailedFaceDetection*0:lip.right.y').d - $('DetailedFaceDetection*0:eye.left.y').d), 2) );

// Distance from left eye to upper lip
Math.sqrt( Math.pow(($('DetailedFaceDetection*0:lip.up.x').d - $('DetailedFaceDetection*0:eye.left.x').d), 2) + Math.pow(($('DetailedFaceDetection*0:lip.up.y').d - $('DetailedFaceDetection*0:eye.left.y').d), 2) );

// Distance from left eye to lower lip
Math.sqrt( Math.pow(($('DetailedFaceDetection*0:lip.down.x').d - $('DetailedFaceDetection*0:eye.left.x').d), 2) + Math.pow(($('DetailedFaceDetection*0:lip.down.y').d - $('DetailedFaceDetection*0:eye.left.y').d), 2) );
```

### Python Code
```python
# Distance from left eye to left eye
math.sqrt( math.pow((__('DetailedFaceDetection*0:eye.left.x').d - __('DetailedFaceDetection*0:eye.left.x').d), 2) + math.pow((__('DetailedFaceDetection*0:eye.left.y').d - __('DetailedFaceDetection*0:eye.left.y').d), 2) )

# Distance from left eye to right eye
math.sqrt( math.pow((__('DetailedFaceDetection*0:eye.right.x').d - __('DetailedFaceDetection*0:eye.left.x').d), 2) + math.pow((__('DetailedFaceDetection*0:eye.right.y').d - __('DetailedFaceDetection*0:eye.left.y').d), 2) )

# Horizontal distance from left eye to left pupil
math.fabs(__('DetailedFaceDetection*0:pupil.left.x').d - __('DetailedFaceDetection*0:eye.left.x').d)

# Horizontal distance from left eye to right pupil
math.fabs(__('DetailedFaceDetection*0:pupil.right.x').d - __('DetailedFaceDetection*0:eye.left.x').d)

# Vertical distance from left eye to nose
math.fabs(__('DetailedFaceDetection*0:nose.y').d - __('DetailedFaceDetection*0:eye.left.y').d)

# Vertical distance from left eye to mouth
math.fabs(__('DetailedFaceDetection*0:mouth.y').d - __('DetailedFaceDetection*0:eye.left.y').d)

# Distance from left eye to left lip corner
math.sqrt( math.pow((__('DetailedFaceDetection*0:lip.left.x').d - __('DetailedFaceDetection*0:eye.left.x').d), 2) + math.pow((__('DetailedFaceDetection*0:lip.left.y').d - __('DetailedFaceDetection*0:eye.left.y').d), 2) )

# Distance from left eye to right lip corner
math.sqrt( math.pow((__('DetailedFaceDetection*0:lip.right.x').d - __('DetailedFaceDetection*0:eye.left.x').d), 2) + math.pow((__('DetailedFaceDetection*0:lip.right.y').d - __('DetailedFaceDetection*0:eye.left.y').d), 2) )

# Distance from left eye to upper lip
math.sqrt( math.pow((__('DetailedFaceDetection*0:lip.up.x').d - __('DetailedFaceDetection*0:eye.left.x').d), 2) + math.pow((__('DetailedFaceDetection*0:lip.up.y').d - __('DetailedFaceDetection*0:eye.left.y').d), 2) )

# Distance from left eye to lower lip
math.sqrt( math.pow((__('DetailedFaceDetection*0:lip.down.x').d - __('DetailedFaceDetection*0:eye.left.x').d), 2) + math.pow((__('DetailedFaceDetection*0:lip.down.y').d - __('DetailedFaceDetection*0:eye.left.y').d), 2) )
```

## Model Loading State
Returns the face model loading state.  
Returns 0 if not loaded yet, 1 if loading, and 2 if loading is complete.


<img src="https://github.com/user-attachments/assets/cbfce1de-3562-468a-9126-02f3a270f91e" width="80%" height="80%" >

### JavaScript Code
```javascript
// Face model loading state value
$('DetailedFaceDetection*0:model_state').d;
```

### Python Code
```python
# Face model loading state value
__('DetailedFaceDetection*0:model_state').d
```

## Was a Face Detected?
Returns whether a face was detected as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/8a1f2aa0-f254-41ba-a9e8-bef336af20c0" width="60%" height="60%" >

### JavaScript Code
```javascript
// Was a face detected?
$('DetailedFaceDetection*0:detected').d;
```

### Python Code
```python
# Was a face detected?
__('DetailedFaceDetection*0:detected').d
```