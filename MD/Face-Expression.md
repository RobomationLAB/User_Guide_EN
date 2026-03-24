# Open Dashboard
**Open Dashboard** is not a block that can be used in block coding,  
but it allows you to open a dashboard where you can check how the model used in the extension module is applied.

## Dashboard Screen
When you click Open Dashboard, you can see the following screen.  

![](https://github.com/user-attachments/assets/fabf7030-a7df-446c-8582-a6731cbd8c0a)

## Detailed Features

### Power
Turns the selected camera on or off.

### Load Model 
Loads the trained age, gender, expression models. This is a required step to use the 'Face Expression' extension module.

### Show Result
Displays the detected age, gender, and expression results on the camera screen.

### Detect
Starts or stops age, gender, expression detection.  
You can choose whether to run it once with the Once button or continuously with the Continuous button.  
You can also stop the detection using the Stop button.

### Sensory Data
Outputs the detected age, gender, expression detection data values.

<br>  

# Blocks
## Set Camera
Select the camera to be used for the Face Expression module.

<img src="https://github.com/user-attachments/assets/3b63f5c2-411b-45e1-b5c2-9303e7f737df" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|camera|Dropdown option|Camera to use|List of available cameras|

### JavaScript Code
```javascript
// Set a specific camera for face expression detection (id is an example)
$('FaceExpression*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb';
```

### Python Code
```python
# Set a specific camera for face expression detection (id is an example)
__('FaceExpression*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb'
```

## Load Face Expression Model
Loads the trained age, gender, expression model.  
This step is required to use the functions of the 'Face Expression' module.

<img src="https://github.com/user-attachments/assets/bc3d07e8-bfd9-4cd8-9a79-116abbb54b20" width="75%" height="75%" >

### JavaScript Code

```javascript
// Load age, gender, expression model | Wait O
$('FaceExpression*0:load_model').d = 1;
await $('FaceExpression*0:!load_model').w();

// Load age, gender, expression model | Wait X
$('FaceExpression*0:load_model').d = 1;
```

### Python Code
```python
# Load face model | Wait O
__('FaceExpression*0:load_model').d = 1
await __('FaceExpression*0:!load_model').w()

# Load face model | Wait X
__('FaceExpression*0:load_model').d = 1
```

## Detect Age, Gender, Expression Once
Analyzes the face currently on the screen and displays the detected age, gender, and expression exactly once.

<img src="https://github.com/user-attachments/assets/7f630859-76a4-4360-a3a6-bb13a92a00b5" width="75%" height="75%" >

### JavaScript Code
```javascript
// Detect age, gender, and expression once
$('FaceExpression*0:detect.once').d = 1;
```

### Python Code
```python
# Detect age, gender, and expression once
__('FaceExpression*0:detect.once').d = 1
```

## Detect Age, Gender, Expression Continuously
Starts or stops continuous age, gender, expression detection.  
When continuous detection starts, it continuously follows the face currently on the screen and displays the detected results on the screen.

<img src="https://github.com/user-attachments/assets/d27ff59e-dc57-4093-bb40-00751dd5dd9b" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown option|Detect|Start (1), Stop (0)|

### JavaScript Code
```javascript
// Start continuous age, gender, expression detection
$('FaceExpression*0:detect.continuous').d = 1;

// Stop continuous age, gender, expression detection
$('FaceExpression*0:detect.continuous').d = 0;
```

### Python Code
```python
# Start continuous age, gender, expression detection
__('FaceExpression*0:detect.continuous').d = 1

# Stop continuous age, gender, expression detection
__('FaceExpression*0:detect.continuous').d = 0
```

## Show Age, Gender, Expression Detection Results
Determines whether to display the detected age, gender, and expression results on the camera screen.

<img src="https://github.com/user-attachments/assets/28ab9b3b-bee4-440d-abec-5779dc75a053" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown option|Detection results|Show (1), Hide (0)|

### JavaScript Code
```javascript
// Show age, gender, expression detection results
$('FaceExpression*0:display').d = 1;

// Hide age, gender, expression detection results
$('FaceExpression*0:display').d = 0;
```

### Python Code
```python
# Show age, gender, expression detection results
__('FaceExpression*0:display').d = 1

# Hide age, gender, expression detection results
__('FaceExpression*0:display').d = 0
```

## Age Detection Data
Returns the age detection result data.

<img src="https://github.com/user-attachments/assets/0669ebf9-9c6b-4e29-898f-b24f8eb2ba49" width="75%" height="75%" >

### JavaScript Code
```javascript
// Age detection data
$('FaceExpression*0:age').d;
```

### Python Code
```python
# Age detection data
__('FaceExpression*0:age').d
```

## Gender Detection Data
Returns the gender detection result data.  
The returned data is 'Male', 'Female'.

<img src="https://github.com/user-attachments/assets/b9e9a290-6a71-4a1d-9730-95a58d15f59a" width="75%" height="75%" >

### JavaScript Code
```javascript
// Gender detection data
$('FaceExpression*0:gender.name').d;
```

### Python Code
```python
# Gender detection data
__('FaceExpression*0:gender.name').d
```

## Expression Detection Data
Returns the expression detection result data.  
The returned data is 'happy', 'sad', 'angry', 'fearful', 'disgusted', 'surprised', and 'neutral'.


<img src="https://github.com/user-attachments/assets/131244d6-48d3-4acc-915b-d35c6b8ecb99" width="75%" height="75%" >

### JavaScript Code
```javascript
// Expression detection data
$('FaceExpression*0:expression.name').d;
```

### Python Code
```python
# Expression detection data
__('FaceExpression*0:expression.name').d
```

## Is Gender Detected?
Returns **True (1) / False (0)** depending on whether gender detection has been made.


<img src="https://github.com/user-attachments/assets/c155c7d5-d5bb-4951-95b7-acd9d4c8615d" width="75%" height="75%" >

### JavaScript Code

```javascript
// Is gender detected?
$('FaceExpression*0:gender.detected').d;
```

### Python Code
```python
# Is gender detected?
__('FaceExpression*0:gender.detected').d
```

## Is Gender ~ ?
Returns **True (1) / False (0)** depending on whether the selected gender matches the detected gender.

<img src="https://github.com/user-attachments/assets/869012b4-3ad0-44e1-8e2f-c0fc516b4e71" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|gender|Dropdown option|Gender|male, female|

### JavaScript Code
```javascript
// Is the detected gender male?
$('FaceExpression*0:gender.name').d === 'male';

// Is the detected gender female?
$('FaceExpression*0:gender.name').d === 'female';
```

### Python Code
```python
# Is the detected gender male?
__('FaceExpression*0:gender.name').d == 'male'

# Is the detected gender female?
__('FaceExpression*0:gender.name').d == 'female'
```

## Probability (Confidence) that Gender is ~
Returns the probability (confidence) that the selected gender matches the detected gender.  
The return value is a real number between 0 and 1.

<img src="https://github.com/user-attachments/assets/3cf23c26-8439-4c91-a9a6-77df561eb150" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|gender|Dropdown option|Gender|Male(0), Female(1)|

### JavaScript Code
```javascript
// Probability that the detected gender is male
$('FaceExpression*0:gender.confidence').d[0];

// Probability that the detected gender is female
$('FaceExpression*0:gender.confidence').d[1];
```

### Python Code
```python
# Probability that the detected gender is male
__('FaceExpression*0:gender.confidence').d[0]

# Probability that the detected gender is female
__('FaceExpression*0:gender.confidence').d[1]
```

## Is Expression Detected?
Returns **True (1) / False (0)** depending on whether expression detection has been made.

<img src="https://github.com/user-attachments/assets/cc816e4b-317a-4d81-a57c-88cd8ee1703e" width="75%" height="75%" >

### JavaScript Code
```javascript
// Is expression detected?
$('FaceExpression*0:expression.detected').d;
```

### Python Code
```python
# Is expression detected?
__('FaceExpression*0:expression.detected').d
```

## Is Expression ~ ?
Returns **True (1) / False (0)** depending on whether the selected expression matches the detected expression.

<img src="https://github.com/user-attachments/assets/07f030c8-870b-4a83-ae9c-c06f80270721" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|expression|Dropdown option|Expression|happy, sad, angry, fearful, disgusted, surprised, neutral|

### JavaScript Code
```javascript
// Is the detected expression happy?
$('FaceExpression*0:expression.name').d === 'happy';

// Is the detected expression sad?
$('FaceExpression*0:expression.name').d === 'sad';

// Is the detected expression angry?
$('FaceExpression*0:expression.name').d === 'angry';

// Is the detected expression fearful?
$('FaceExpression*0:expression.name').d === 'fearful';

// Is the detected expression disgusted?
$('FaceExpression*0:expression.name').d === 'disgusted';

// Is the detected expression surprised?
$('FaceExpression*0:expression.name').d === 'surprised';

// Is the detected expression neutral?
$('FaceExpression*0:expression.name').d === 'neutral';
```

### Python Code
```python
# Is the detected expression happy?
__('FaceExpression*0:expression.name').d == 'happy'

# Is the detected expression sad?
__('FaceExpression*0:expression.name').d == 'sad'

# Is the detected expression angry?
__('FaceExpression*0:expression.name').d == 'angry'

# Is the detected expression fearful?
__('FaceExpression*0:expression.name').d == 'fearful'

# Is the detected expression disgusted?
__('FaceExpression*0:expression.name').d == 'disgusted'

# Is the detected expression surprised?
__('FaceExpression*0:expression.name').d == 'surprised'

# Is the detected expression neutral?
__('FaceExpression*0:expression.name').d == 'neutral'
```

## Probability (Confidence) that Expression is ~
Returns the probability (confidence) that the selected expression matches the detected expression.  
The return value is a real number between 0 and 1.

<img src="https://github.com/user-attachments/assets/14ef15ca-a8ed-4076-a57b-088babd84428" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|expression|Dropdown option|Expression|happy, sad, angry, fearful, disgusted, surprised, neutral|

### JavaScript Code
```javascript
// Probability that the detected expression is happy
$('FaceExpression*0:expression.confidence').d[0];

// Probability that the detected expression is sad
$('FaceExpression*0:expression.confidence').d[1];

// Probability that the detected expression is angry
$('FaceExpression*0:expression.confidence').d[2];

// Probability that the detected expression is fearful
$('FaceExpression*0:expression.confidence').d[3];

// Probability that the detected expression is disgusted
$('FaceExpression*0:expression.confidence').d[4];

// Probability that the detected expression is surprised
$('FaceExpression*0:expression.confidence').d[5];

// Probability that the detected expression is neutral
$('FaceExpression*0:expression.confidence').d[6];
```

### Python Code

```python
# Probability that the detected expression is happy
__('FaceExpression*0:expression.confidence').d[0]

# Probability that the detected expression is sad
__('FaceExpression*0:expression.confidence').d[1]

# Probability that the detected expression is angry
__('FaceExpression*0:expression.confidence').d[2]

# Probability that the detected expression is fearful
__('FaceExpression*0:expression.confidence').d[3]

# Probability that the detected expression is disgusted
__('FaceExpression*0:expression.confidence').d[4]

# Probability that the detected expression is surprised
__('FaceExpression*0:expression.confidence').d[5]

# Probability that the detected expression is neutral
__('FaceExpression*0:expression.confidence').d[6]
```

## Age, Gender, Expression Model Loading State Value
Returns the loading state of the age, gender, and expression model.  
If it has not been loaded yet, it returns 0; if it is loading, it returns 1; if loading is complete, it returns 2.


<img src="https://github.com/user-attachments/assets/efb1eb5c-266a-4858-be02-ee57b428d4e0" width="75%" height="75%" >

### JavaScript Code
```javascript
// Age, gender, and expression model loading state value
$('FaceExpression*0:model_state').d;
```

### Python Code
```python
# Age, gender, and expression model loading state value
__('FaceExpression*0:model_state').d
```
