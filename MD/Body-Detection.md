# Open Dashboard
**Open Dashboard** is not a block that can be used for block coding,  
but it allows you to open a dashboard where you can check how the model used in the extension module is applied.

## Dashboard Screen
When you click Open Dashboard, you can see the following screen.

<img src="https://github.com/user-attachments/assets/825397a3-278d-48ef-8d94-6cd09a79f76b" width="100%" height="100%" >

## Detailed Features

### Power
Turns the selected camera on or off.

### Load Model 
Loads a trained body model. This step is required to use the 'Body Detection' extension module.

### Detect
Starts or stops body detection.  
You can choose whether to run it once with the Once button or continuously with the Continuous button.  
You can also stop detection using the Stop button.

### Show Result
Displays the body detection result on the camera screen.

### Sensory Data
Outputs data values corresponding to the selected body part.

#### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| parts | Dropdown Option | Body part | eye, ear, nose, mouth, neck, shoulder, elbow, wrist, hand, hip, knee, ankle, foot |

<br>

# Blocks
## Select Camera
Selects the camera to be used for the body detection module.


<img src="https://github.com/user-attachments/assets/d4a75062-0e48-4bc8-950a-d1c4d901bfee" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|camera|Dropdown Option|Camera to use|List of connected cameras|

### JavaScript Code
```javascript
// Set a specific camera as the camera for body detection (id is an example)
$('BodyDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb';
```

### Python Code
```python
# Set a specific camera as the camera for body detection (id is an example)
__('BodyDetection*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb'
```

<br>  

## Load Body Model
Loads a trained body model. This step is required to use the functions of the 'Body Detection' module.  
If wait is checked, it waits until model loading is completed.  
However, if wait is checked, it can only be used inside an async function.


<img src="https://github.com/user-attachments/assets/88087601-ddf6-4ffa-a5e3-d22d11ce42fd" width="100%" height="100%" >


### JavaScript Code
```javascript
// Load body model | Wait O
$('BodyDetection*0:load_model').d = 1;
await $('BodyDetection*0:!load_model').w();

// Load body model | Wait X
$('BodyDetection*0:load_model').d = 1;
```

### Python Code
```python
# Load body model | Wait O
__('BodyDetection*0:load_model').d = 1
await __('BodyDetection*0:!load_model').w()

# Load body model | Wait X
__('BodyDetection*0:load_model').d = 1
```

## Detect Body Once
Finds the body currently on the screen and displays it only once.


<img src="https://github.com/user-attachments/assets/0f8c4850-b0ce-4cdd-ae69-200d69963b8b" width="70%" height="70%" >

### JavaScript Code
```javascript
// Detect body once
$('BodyDetection*0:detect.once').d = 1;
```

### Python Code
```python
# Detect body once
__('BodyDetection*0:detect.once').d = 1
```

## Continuous Body Detection
Starts or stops continuous body detection.  
When continuous detection starts, it keeps tracking the body currently on the screen and displays it.


<img src="https://github.com/user-attachments/assets/75815dbd-8278-42ea-be12-ec9213ef260d" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown Option|Body detection|Start (1), Stop (0)|

### JavaScript Code
```javascript
// Start continuous body detection
$('BodyDetection*0:detect.continuous').d = 1;

// Stop continuous body detection
$('BodyDetection*0:detect.continuous').d = 0;
```

### Python Code
```python
# Start continuous body detection
__('BodyDetection*0:detect.continuous').d = 1

# Stop continuous body detection
__('BodyDetection*0:detect.continuous').d = 0
```

## Show Body Detection Result
Determines whether to display body detection results on the camera screen.


<img src="https://github.com/user-attachments/assets/326c23cb-0225-449b-af90-6e2e541314d1" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown Option|Body detection result|Show (1), Hide (0)|

### JavaScript Code
```javascript
// Show body detection result
$('BodyDetection*0:display').d = 1;

// Hide body detection result
$('BodyDetection*0:display').d = 0;
```

### Python Code
```python
# Show body detection result
__('BodyDetection*0:display').d = 1

# Hide body detection result
__('BodyDetection*0:display').d = 0
```

## Body Data
Returns data of the selected body part.

<img src="https://github.com/user-attachments/assets/f6b96622-1da7-481f-b608-984cc81991d9" width="100%" height="100%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|part|Dropdown Option|Body part| Left eye (eye.left), Right eye (eye.right), Left ear (ear.left), Right ear (ear.right), Nose (nose), Mouth (mouth), Neck (neck), Left shoulder (shoulder.left), Right shoulder (shoulder.right), Left elbow (elbow.left), Right elbow (elbow.right), Left wrist (wrist.left), Right wrist (wrist.right), Left hand (hand.left), Right hand (hand.right), Left hip (hip.left), Right hip (hip.right), Left knee (knee.left), Right knee (knee.right), Left ankle (ankle.left), Right ankle (ankle.right), Left foot (foot.left), Right foot (foot.right) |
|axis|Dropdown Option|Coordinate axis|x, y|

### JavaScript Code
```javascript
// Left eye x coordinate
$('BodyDetection*0:eye.left.x').d;

// Right eye x coordinate
$('BodyDetection*0:eye.right.x').d;

// Left ear x coordinate
$('BodyDetection*0:ear.left.x').d;

// Right ear x coordinate
$('BodyDetection*0:ear.right.x').d;

// Nose x coordinate
$('BodyDetection*0:nose.x').d;

// Mouth x coordinate
$('BodyDetection*0:mouth.x').d;

// Neck x coordinate
$('BodyDetection*0:neck.x').d;

// Left shoulder x coordinate
$('BodyDetection*0:shoulder.left.x').d;

// Right shoulder x coordinate
$('BodyDetection*0:shoulder.right.x').d;

// Left elbow x coordinate
$('BodyDetection*0:elbow.left.x').d;

// Right elbow x coordinate
$('BodyDetection*0:elbow.right.x').d;

// Left wrist x coordinate
$('BodyDetection*0:wrist.left.x').d;

// Right wrist x coordinate
$('BodyDetection*0:wrist.right.x').d;

// Left hand x coordinate
$('BodyDetection*0:hand.left.x').d;

// Right hand x coordinate
$('BodyDetection*0:hand.right.x').d;

// Left hip y coordinate
$('BodyDetection*0:hip.left.y').d;

// Right hip y coordinate
$('BodyDetection*0:hip.right.y').d;

// Left knee y coordinate
$('BodyDetection*0:knee.left.y').d;

// Right knee y coordinate
$('BodyDetection*0:knee.right.y').d;

// Left ankle y coordinate
$('BodyDetection*0:ankle.left.y').d;

// Right ankle y coordinate
$('BodyDetection*0:ankle.right.y').d;

// Left foot y coordinate
$('BodyDetection*0:foot.left.y').d;

// Right foot y coordinate
$('BodyDetection*0:foot.right.y').d;
```

### Python Code
```python
# Left eye x coordinate
__('BodyDetection*0:eye.left.x').d

# Right eye x coordinate
__('BodyDetection*0:eye.right.x').d

# Left ear x coordinate
__('BodyDetection*0:ear.left.x').d

# Right ear x coordinate
__('BodyDetection*0:ear.right.x').d

# Nose x coordinate
__('BodyDetection*0:nose.x').d

# Mouth x coordinate
__('BodyDetection*0:mouth.x').d

# Neck x coordinate
__('BodyDetection*0:neck.x').d

# Left shoulder x coordinate
__('BodyDetection*0:shoulder.left.x').d

# Right shoulder x coordinate
__('BodyDetection*0:shoulder.right.x').d

# Left elbow x coordinate
__('BodyDetection*0:elbow.left.x').d

# Right elbow x coordinate
__('BodyDetection*0:elbow.right.x').d

# Left wrist x coordinate
__('BodyDetection*0:wrist.left.x').d

# Right wrist x coordinate
__('BodyDetection*0:wrist.right.x').d

# Left hand x coordinate
__('BodyDetection*0:hand.left.x').d

# Right hand x coordinate
__('BodyDetection*0:hand.right.x').d

# Left hip y coordinate
__('BodyDetection*0:hip.left.y').d

# Right hip y coordinate
__('BodyDetection*0:hip.right.y').d

# Left knee y coordinate
__('BodyDetection*0:knee.left.y').d

# Right knee y coordinate
__('BodyDetection*0:knee.right.y').d

# Left ankle y coordinate
__('BodyDetection*0:ankle.left.y').d

# Right ankle y coordinate
__('BodyDetection*0:ankle.right.y').d

# Left foot y coordinate
__('BodyDetection*0:foot.left.y').d

# Right foot y coordinate
__('BodyDetection*0:foot.right.y').d
```

## Distance Between Two Body Parts
Returns the distance between two selected body parts.

<img src="https://github.com/user-attachments/assets/d7e9e30f-f4fc-401e-97ef-e9d41964efb9" width="100%" height="100%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|part 1|Dropdown Option|Body part| Left eye (eye.left), Right eye (eye.right), Left ear (ear.left), Right ear (ear.right), Nose (nose), Mouth (mouth), Neck (neck), Left shoulder (shoulder.left), Right shoulder (shoulder.right), Left elbow (elbow.left), Right elbow (elbow.right), Left wrist (wrist.left), Right wrist (wrist.right), Left hand (hand.left), Right hand (hand.right), Left hip (hip.left), Right hip (hip.right), Left knee (knee.left), Right knee (knee.right), Left ankle (ankle.left), Right ankle (ankle.right), Left foot (foot.left), Right foot (foot.right) |
|part 2|Dropdown Option|Body part| Left eye (eye.left), Right eye (eye.right), Left ear (ear.left), Right ear (ear.right), Nose (nose), Mouth (mouth), Neck (neck), Left shoulder (shoulder.left), Right shoulder (shoulder.right), Left elbow (elbow.left), Right elbow (elbow.right), Left wrist (wrist.left), Right wrist (wrist.right), Left hand (hand.left), Right hand (hand.right), Left hip (hip.left), Right hip (hip.right), Left knee (knee.left), Right knee (knee.right), Left ankle (ankle.left), Right ankle (ankle.right), Left foot (foot.left), Right foot (foot.right) |
|distance|Dropdown Option|Distance| Distance, Horizontal distance, Vertical distance |

### JavaScript Code
```javascript
// Distance from left eye to left eye
Math.sqrt( Math.pow(($('BodyDetection*0:eye.left.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:eye.left.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to right eye
Math.sqrt( Math.pow(($('BodyDetection*0:eye.right.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:eye.right.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to left ear 
Math.sqrt( Math.pow(($('BodyDetection*0:ear.left.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:ear.left.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to right ear
Math.sqrt( Math.pow(($('BodyDetection*0:ear.right.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:ear.right.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to nose
Math.sqrt( Math.pow(($('BodyDetection*0:nose.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:nose.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to mouth
Math.sqrt( Math.pow(($('BodyDetection*0:mouth.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:mouth.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to neck
Math.sqrt( Math.pow(($('BodyDetection*0:neck.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:neck.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to left shoulder
Math.sqrt( Math.pow(($('BodyDetection*0:shoulder.left.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:shoulder.left.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to right shoulder
Math.sqrt( Math.pow(($('BodyDetection*0:shoulder.right.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:shoulder.right.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to left elbow
Math.sqrt( Math.pow(($('BodyDetection*0:elbow.left.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:elbow.left.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Distance from left eye to right elbow
Math.sqrt( Math.pow(($('BodyDetection*0:elbow.right.x').d - $('BodyDetection*0:eye.left.x').d), 2) + Math.pow(($('BodyDetection*0:elbow.right.y').d - $('BodyDetection*0:eye.left.y').d), 2) );

// Horizontal distance from left eye to left wrist
Math.abs($('BodyDetection*0:wrist.left.x').d - $('BodyDetection*0:eye.left.x').d);

// Horizontal distance from left eye to right wrist
Math.abs($('BodyDetection*0:wrist.right.x').d - $('BodyDetection*0:eye.left.x').d);

// Horizontal distance from left eye to left hand
Math.abs($('BodyDetection*0:hand.left.x').d - $('BodyDetection*0:eye.left.x').d);

// Horizontal distance from left eye to right hand
Math.abs($('BodyDetection*0:hand.right.x').d - $('BodyDetection*0:eye.left.x').d);

// Horizontal distance from left eye to left hip
Math.abs($('BodyDetection*0:hip.left.x').d - $('BodyDetection*0:eye.left.x').d);

// Horizontal distance from left eye to right hip
Math.abs($('BodyDetection*0:hip.right.x').d - $('BodyDetection*0:eye.left.x').d);

// Vertical distance from left eye to left knee
Math.abs($('BodyDetection*0:knee.left.y').d - $('BodyDetection*0:eye.left.y').d);

// Vertical distance from left eye to right knee
Math.abs($('BodyDetection*0:knee.right.y').d - $('BodyDetection*0:eye.left.y').d);

// Vertical distance from left eye to left ankle
Math.abs($('BodyDetection*0:ankle.left.y').d - $('BodyDetection*0:eye.left.y').d);

// Vertical distance from left eye to right ankle
Math.abs($('BodyDetection*0:ankle.right.y').d - $('BodyDetection*0:eye.left.y').d);

// Vertical distance from left eye to left foot
Math.abs($('BodyDetection*0:foot.left.y').d - $('BodyDetection*0:eye.left.y').d);

// Vertical distance from left eye to right foot
Math.abs($('BodyDetection*0:foot.right.y').d - $('BodyDetection*0:eye.left.y').d);
```

### Python Code
```python
# Distance from left eye to left eye
math.sqrt( math.pow((__('BodyDetection*0:eye.left.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:eye.left.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to right eye
math.sqrt( math.pow((__('BodyDetection*0:eye.right.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:eye.right.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to left ear
math.sqrt( math.pow((__('BodyDetection*0:ear.left.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:ear.left.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to right ear 
math.sqrt( math.pow((__('BodyDetection*0:ear.right.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:ear.right.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to nose
math.sqrt( math.pow((__('BodyDetection*0:nose.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:nose.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to mouth
math.sqrt( math.pow((__('BodyDetection*0:mouth.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:mouth.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to neck
math.sqrt( math.pow((__('BodyDetection*0:neck.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:neck.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to left shoulder
math.sqrt( math.pow((__('BodyDetection*0:shoulder.left.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:shoulder.left.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to right shoulder
math.sqrt( math.pow((__('BodyDetection*0:shoulder.right.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:shoulder.right.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to left elbow
math.sqrt( math.pow((__('BodyDetection*0:elbow.left.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:elbow.left.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Distance from left eye to right elbow
math.sqrt( math.pow((__('BodyDetection*0:elbow.right.x').d - __('BodyDetection*0:eye.left.x').d), 2) + math.pow((__('BodyDetection*0:elbow.right.y').d - __('BodyDetection*0:eye.left.y').d), 2) )

# Horizontal distance from left eye to left wrist
math.fabs(__('BodyDetection*0:wrist.left.x').d - __('BodyDetection*0:eye.left.x').d)

# Horizontal distance from left eye to right wrist
math.fabs(__('BodyDetection*0:wrist.right.x').d - __('BodyDetection*0:eye.left.x').d)

# Horizontal distance from left eye to left hand
math.fabs(__('BodyDetection*0:hand.left.x').d - __('BodyDetection*0:eye.left.x').d)

# Horizontal distance from left eye to right hand
math.fabs(__('BodyDetection*0:hand.right.x').d - __('BodyDetection*0:eye.left.x').d)

# Horizontal distance from left eye to left hip
math.fabs(__('BodyDetection*0:hip.left.x').d - __('BodyDetection*0:eye.left.x').d)

# Horizontal distance from left eye to right hip
math.fabs(__('BodyDetection*0:hip.right.x').d - __('BodyDetection*0:eye.left.x').d)

# Vertical distance from left eye to left knee
math.fabs(__('BodyDetection*0:knee.left.y').d - __('BodyDetection*0:eye.left.y').d)

# Vertical distance from left eye to right knee
math.fabs(__('BodyDetection*0:knee.right.y').d - __('BodyDetection*0:eye.left.y').d)

# Vertical distance from left eye to left ankle
math.fabs(__('BodyDetection*0:ankle.left.y').d - __('BodyDetection*0:eye.left.y').d)

# Vertical distance from left eye to right ankle
math.fabs(__('BodyDetection*0:ankle.right.y').d - __('BodyDetection*0:eye.left.y').d)

# Vertical distance from left eye to left foot
math.fabs(__('BodyDetection*0:foot.left.y').d - __('BodyDetection*0:eye.left.y').d)

# Vertical distance from left eye to right foot
math.fabs(__('BodyDetection*0:foot.right.y').d - __('BodyDetection*0:eye.left.y').d)
```

## Body Model Loading State Value
Returns the body model loading state.  
If not loaded yet → returns 0  
If loading → returns 1  
If loading completed → returns 2


<img src="https://github.com/user-attachments/assets/487eec0e-7a24-43fc-a699-1fa5df53314e" width="90%" height="90%" >

### JavaScript Code
```javascript
// Body model loading state value
$('BodyDetection*0:model_state').d;
```

### Python Code
```python
# Body model loading state value
__('BodyDetection*0:model_state').d
```

## Was a Body Detected?
Returns whether a body was detected as **True (1) / False (0)**.


<img src="https://github.com/user-attachments/assets/bc36d292-1e4b-47cc-9feb-ffea7a2d4c8a" width="70%" height="70%" >

### JavaScript Code
```javascript
// Was a body detected?
$('BodyDetection*0:detected').d;
```

### Python Code
```python
# Was a body detected?
__('BodyDetection*0:detected').d
```