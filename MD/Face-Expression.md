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
Displays the predicted age, gender, and expression results on the camera screen.

### Predict
Starts or stops age, gender, expression recognition.  
You can choose whether to run it once with the Once button or continuously with the Continuous button.  
You can also stop the prediction using the Stop button.

### Sensory Data
Outputs the predicted age, gender, expression recognition data values.

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
// Set a specific camera for face expression recognition (id is an example)
$('FaceExpression*0:camera.deviceId').d = '035658da47183882a695a82c45b8f3e9ae50cef47945ccdc3f31e1ae1fbca9cb';
```

### Python Code
```python
# Set a specific camera for face expression recognition (id is an example)
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

## Recognize Age, Gender, Expression Once
Analyzes the face currently on the screen and displays the predicted age, gender, and expression exactly once.

<img src="https://github.com/user-attachments/assets/ea07615f-1e45-4852-8c94-f7cf6b64d075" width="75%" height="75%" >

### JavaScript Code
```javascript
// Recognize age, gender, and expression once
$('FaceExpression*0:predict.once').d = 1;
```

### Python Code
```python
# Recognize age, gender, and expression once
__('FaceExpression*0:predict.once').d = 1
```

## Recognize Age, Gender, Expression Continuously
Starts or stops continuous age, gender, expression recognition.  
When continuous prediction starts, it continuously follows the face currently on the screen and displays the predicted results on the screen.

<img src="https://github.com/user-attachments/assets/61259767-3c26-4f0a-a4c2-4218b874fd43" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown option|Predict|Start (1), Stop (0)|

### JavaScript Code
```javascript
// Start continuous age, gender, expression recognition
$('FaceExpression*0:predict.continuous').d = 1;

// Stop continuous age, gender, expression recognition
$('FaceExpression*0:predict.continuous').d = 0;
```

### Python Code
```python
# Start continuous age, gender, expression recognition
__('FaceExpression*0:predict.continuous').d = 1

# Stop continuous age, gender, expression recognition
__('FaceExpression*0:predict.continuous').d = 0
```

## Show Age, Gender, Expression Detection Results
Determines whether to display the predicted age, gender, and expression results on the camera screen.

<img src="https://github.com/user-attachments/assets/28ab9b3b-bee4-440d-abec-5779dc75a053" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|toggle|Dropdown option|Prediction results|Show (1), Hide (0)|

### JavaScript Code
```javascript
// Show age, gender, expression recognition results
$('FaceExpression*0:display').d = 1;

// Hide age, gender, expression recognition results
$('FaceExpression*0:display').d = 0;
```

### Python Code
```python
# Show age, gender, expression recognition results
__('FaceExpression*0:display').d = 1

# Hide age, gender, expression recognition results
__('FaceExpression*0:display').d = 0
```

## Age Prediction Data
Returns the age prediction result data.

<img src="https://github.com/user-attachments/assets/0669ebf9-9c6b-4e29-898f-b24f8eb2ba49" width="75%" height="75%" >

### JavaScript Code
```javascript
// Age prediction data
$('FaceExpression*0:age').d;
```

### Python Code
```python
# Age prediction data
__('FaceExpression*0:age').d
```

## Gender Prediction Data
Returns the gender prediction result data.  
The returned data is 'Male', 'Female'.

<img src="https://github.com/user-attachments/assets/b9e9a290-6a71-4a1d-9730-95a58d15f59a" width="75%" height="75%" >

### JavaScript Code
```javascript
// Gender prediction data
$('FaceExpression*0:gender.name').d;
```

### Python Code
```python
# Gender prediction data
__('FaceExpression*0:gender.name').d
```

## Expression Prediction Data
Returns the expression prediction result data.  
The returned data is 'Happy', 'Sad', 'Angry', 'Afraid', 'Disgust', 'Surprise', 'Expressionless'.


<img src="https://github.com/user-attachments/assets/131244d6-48d3-4acc-915b-d35c6b8ecb99" width="75%" height="75%" >

### JavaScript Code
```javascript
// Expression prediction data
$('FaceExpression*0:expression.name').d;
```

### Python Code
```python
# Expression prediction data
__('FaceExpression*0:expression.name').d
```

## Is Gender Recognized?
Returns **True (1) / False (0)** depending on whether gender prediction has been made.


<img src="https://github.com/user-attachments/assets/3c280f5f-f416-414a-a17a-b401ee0acfc4" width="75%" height="75%" >

### JavaScript Code

```javascript
// Is gender recognized?
$('FaceExpression*0:gender.predicted').d;
```

### Python Code
```python
# Is gender recognized?
__('FaceExpression*0:gender.predicted').d
```

## Is Gender ~ ?
Returns **True (1) / False (0)** depending on whether the selected gender matches the predicted gender.

<img src="https://github.com/user-attachments/assets/869012b4-3ad0-44e1-8e2f-c0fc516b4e71" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|gender|Dropdown option|Gender|male, female|

### JavaScript Code
```javascript
// Is the predicted gender male?
$('FaceExpression*0:gender.name').d === 'male';

// Is the predicted gender female?
$('FaceExpression*0:gender.name').d === 'female';
```

### Python Code
```python
# Is the predicted gender male?
__('FaceExpression*0:gender.name').d == 'male'

# Is the predicted gender female?
__('FaceExpression*0:gender.name').d == 'female'
```

## Probability (Confidence) that Gender is ~
Returns the probability (confidence) that the selected gender matches the predicted gender.  
The return value is a real number between 0 and 1.

<img src="https://github.com/user-attachments/assets/a03b2d67-397b-4138-b6f6-de1eee884d4e" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|gender|Dropdown option|Gender|Male(0), Female(1)|

### JavaScript Code
```javascript
// Probability that the predicted gender is male
$('FaceExpression*0:gender.confidence').d[0];

// Probability that the predicted gender is female
$('FaceExpression*0:gender.confidence').d[1];
```

### Python Code
```python
# Probability that the predicted gender is male
__('FaceExpression*0:gender.confidence').d[0]

# Probability that the predicted gender is female
__('FaceExpression*0:gender.confidence').d[1]
```

## Is Expression Recognized?
Returns **True (1) / False (0)** depending on whether expression recognition has been made.

<img src="https://github.com/user-attachments/assets/297a16aa-e7b1-486a-8dc9-8b0744399e2e" width="75%" height="75%" >

### JavaScript Code
```javascript
// Is expression recognized?
$('FaceExpression*0:expression.predicted').d;
```

### Python Code
```python
# Is expression recognized?
__('FaceExpression*0:expression.predicted').d
```

## Is Expression ~ ?
Returns **True (1) / False (0)** depending on whether the selected expression matches the predicted expression.

<img src="https://github.com/user-attachments/assets/07f030c8-870b-4a83-ae9c-c06f80270721" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|expression|Dropdown option|Expression|happy, sad, angry, fearful, disgusted, surprised, natural|

### JavaScript Code
```javascript
// Is the predicted expression happy?
$('FaceExpression*0:expression.name').d === 'happy';

// Is the predicted expression sad?
$('FaceExpression*0:expression.name').d === 'sad';

// Is the predicted expression angry?
$('FaceExpression*0:expression.name').d === 'angry';

// Is the predicted expression fearful?
$('FaceExpression*0:expression.name').d === 'fearful';

// Is the predicted expression disgusted?
$('FaceExpression*0:expression.name').d === 'disgusted';

// Is the predicted expression surprised?
$('FaceExpression*0:expression.name').d === 'surprised';

// Is the predicted expression natural?
$('FaceExpression*0:expression.name').d === 'natural';
```

### Python Code
```python
# Is the predicted expression happy?
__('FaceExpression*0:expression.name').d == 'happy'

# Is the predicted expression sad?
__('FaceExpression*0:expression.name').d == 'sad'

# Is the predicted expression angry?
__('FaceExpression*0:expression.name').d == 'angry'

# Is the predicted expression fearful?
__('FaceExpression*0:expression.name').d == 'fearful'

# Is the predicted expression disgusted?
__('FaceExpression*0:expression.name').d == 'disgusted'

# Is the predicted expression surprised?
__('FaceExpression*0:expression.name').d == 'surprised'

# Is the predicted expression natural?
__('FaceExpression*0:expression.name').d == 'natural'
```

## Probability (Confidence) that Expression is ~
Returns the probability (confidence) that the selected expression matches the predicted expression.  
The return value is a real number between 0 and 1.

<img src="https://github.com/user-attachments/assets/cdf89deb-477e-42ec-a97f-42bb2a1f75b6" width="75%" height="75%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
|expression|Dropdown option|Expression|Happy(0), Sad(1), Angry(2), Afraid(3), Disgust(4), Surprise(5), Expressionless(6)|

### JavaScript Code
```javascript
// Probability that the predicted expression is happy
$('FaceExpression*0:expression.confidence').d[0];

// Probability that the predicted expression is sad
$('FaceExpression*0:expression.confidence').d[1];

// Probability that the predicted expression is angry
$('FaceExpression*0:expression.confidence').d[2];

// Probability that the predicted expression is afraid
$('FaceExpression*0:expression.confidence').d[3];

// Probability that the predicted expression is disgust
$('FaceExpression*0:expression.confidence').d[4];

// Probability that the predicted expression is surprise
$('FaceExpression*0:expression.confidence').d[5];

// Probability that the predicted expression is expressionless
$('FaceExpression*0:expression.confidence').d[6];
```

### Python Code

```python
# Probability that the predicted expression is happy
__('FaceExpression*0:expression.confidence').d[0]

# Probability that the predicted expression is sad
__('FaceExpression*0:expression.confidence').d[1]

# Probability that the predicted expression is angry
__('FaceExpression*0:expression.confidence').d[2]

# Probability that the predicted expression is afraid
__('FaceExpression*0:expression.confidence').d[3]

# Probability that the predicted expression is disgust
__('FaceExpression*0:expression.confidence').d[4]

# Probability that the predicted expression is surprise
__('FaceExpression*0:expression.confidence').d[5]

# Probability that the predicted expression is expressionless
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
