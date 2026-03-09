# Open Dashboard
**Open Dashboard** is not a block that can be used in block coding,  
but it allows you to open a dashboard where you can check how the model used in the extension module is applied.

## Dashboard Screen
When you click Open Dashboard, you can see the following screen.  

<img src="https://github.com/user-attachments/assets/83835f13-16c2-41c8-a83d-909801387ed3" width="100%" height="100%" >

## Detailed Features

### Power
Turns the selected camera on or off.

### Color Register
Adds the color selected from the dropdown option to the list of colors to detect.

#### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Selected color | black, red, yellow, green, cyan, blue, magenta, white |

### Detect
Starts or stops color detection.  
You can choose whether to run it only once with the Once button, or continuously with the Continuous button.

### Show Result
Displays color detection results on the camera screen.

### Color Data
Displays data values based on the selected color.

#### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Selected color | black, red, yellow, green, cyan, blue, magenta, white |

<br>

# Blocks
## Select Camera
Selects the camera to use for the Color Detection module.

<img src="https://github.com/user-attachments/assets/9ebca667-1880-4f00-8751-f4864ed294ed" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| camera | Dropdown Option | Camera to use | Connected camera list |

### JavaScript Code
```javascript
// Set a specific camera for color detection (id is an example)
$('ColorDetection*0:camera.deviceId').d = 'feed7de06e4339e1a37c0982453051d5a706fa8c06064bfcf215e77b2dcd8818';
```

### Python Code
```python
# Set a specific camera for color detection (id is an example)
__('ColorDetection*0:camera.deviceId').d = 'feed7de06e4339e1a37c0982453051d5a706fa8c06064bfcf215e77b2dcd8818'
```

## Add Recognizable Color
Adds a color to be recognized through color detection.

<img src="https://github.com/user-attachments/assets/59fbfcbb-5ef5-4a09-aa85-7001a749b5d0" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Recognizable color | Black (0), Red (1), Yellow (2), Green (3), Cyan (4), Blue (5), Magenta (6), White (7) |

### JavaScript Code
```javascript
// Add black (0) to target colors
$('ColorDetection*0:color.register').d = 0;
await $('ColorDetection*0:color.!register').w();

// Add green (3) to target colors
$('ColorDetection*0:color.register').d = 3;
await $('ColorDetection*0:color.!register').w();

// Add white (7) to target colors
$('ColorDetection*0:color.register').d = 7;
await $('ColorDetection*0:color.!register').w();
```

### Python Code
```python
# Add black (0) to target colors
__('ColorDetection*0:color.register').d = 0
await __('ColorDetection*0:color.!register').w()

# Add green (3) to target colors
__('ColorDetection*0:color.register').d = 3
await __('ColorDetection*0:color.!register').w()

# Add white (7) to target colors
__('ColorDetection*0:color.register').d = 7
await __('ColorDetection*0:color.!register').w()
```

## Delete Recognizable Color
Deletes a color to be recognized through color detection.

<img src="https://github.com/user-attachments/assets/0ee3560c-b4fd-4629-aecf-d6da62ef9a72" width="100%" height="100%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Recognizable color | Black (0), Red (1), Yellow (2), Green (3), Cyan (4), Blue (5), Magenta (6), White (7) |

### JavaScript Code
```javascript
// Delete black (0) from target colors
$('ColorDetection*0:color.delete').d = 0;
await $('ColorDetection*0:color.!delete').w();

// Delete red (1) from target colors
$('ColorDetection*0:color.delete').d = 1;
await $('ColorDetection*0:color.!delete').w();

// Delete cyan (4) from target colors
$('ColorDetection*0:color.delete').d = 4;
await $('ColorDetection*0:color.!delete').w();
```

### Python Code
```python
# Delete black (0) from target colors
__('ColorDetection*0:color.delete').d = 0
await __('ColorDetection*0:color.!delete').w()

# Delete red (1) from target colors
__('ColorDetection*0:color.delete').d = 1
await __('ColorDetection*0:color.!delete').w()

# Delete cyan (4) from target colors
__('ColorDetection*0:color.delete').d = 4
await __('ColorDetection*0:color.!delete').w()
```

## Set Minimum Area for Color Detection
Sets the minimum area for color detection.  
Only areas whose size is greater than or equal to this value will be displayed on the screen.


<img src="https://github.com/user-attachments/assets/d3f0bb89-4b85-46f4-b4f0-7b46ef9366a1" width="60%" height="60%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| area | Input Value | Minimum area for color detection | Real number ≥ 0 |

### JavaScript Code
```javascript
// Set minimum area condition to 50
$('ColorDetection*0:color.area_condition').d = 50;
```

### Python Code
```python
# Set minimum area condition to 50
__('ColorDetection*0:color.area_condition').d = 50
```

## Detect Colors Once
Among recognizable colors, detects the colors currently on the screen and displays areas only once.

<img src="https://github.com/user-attachments/assets/f54e01f3-151b-48e8-b189-9b13e3796792" width="70%" height="70%" >

### JavaScript Code
```javascript
// Detect colors once
$('ColorDetection*0:detect.once').d = 1;
```

### Python Code
```python
# Detect colors once
__('ColorDetection*0:detect.once').d = 1
```

## Detect Colors Continuously
Starts or stops continuous color detection.  
When continuous detection starts, it keeps tracking and displaying areas of recognizable colors currently on the screen.


<img src="https://github.com/user-attachments/assets/c1a21f34-a54d-46a3-90e3-a6bf955dce98" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Color detection | Start (1), Stop (0) |

### JavaScript Code
```javascript
// Start continuous color detection
$('ColorDetection*0:detect.continuous').d = 1;

// Stop continuous color detection
$('ColorDetection*0:detect.continuous').d = 0;
```

### Python Code
```python
# Start continuous color detection
__('ColorDetection*0:detect.continuous').d = 1

# Stop continuous color detection
__('ColorDetection*0:detect.continuous').d = 0
```

## Show Color Detection Result
Decides whether to display color detection results on the camera screen.

<img src="https://github.com/user-attachments/assets/91d8f239-3253-43de-9831-725c87d1556e" width="70%" height="70%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Show results | Show (1), Hide (0) |

### JavaScript Code
```javascript
// Show color detection results
$('ColorDetection*0:display').d = 1;

// Hide color detection results
$('ColorDetection*0:display').d = 0;
```

### Python Code
```python
# Show color detection results
__('ColorDetection*0:display').d = 1

# Hide color detection results
__('ColorDetection*0:display').d = 0
```

## Color-Related Data
Returns data of the selected color region.


<img src="https://github.com/user-attachments/assets/86fea662-95a5-4ee2-af91-e7dd11131975" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Recognizable color | Black (0), Red (1), Yellow (2), Green (3), Cyan (4), Blue (5), Magenta (6), White (7) |
| axis | Dropdown Option | Coordinate / data type | min_x, max_x, min_y, max_y, width, height, area |

### JavaScript Code
```javascript
// Red (1) region x coordinate
$('ColorDetection*0:color.x').d[1];

// Red (1) region y coordinate
$('ColorDetection*0:color.y').d[1];

// Red (1) region min x
$('ColorDetection*0:color.min_x').d[1];

// Red (1) region max x
$('ColorDetection*0:color.max_x').d[1];

// Red (1) region min y
$('ColorDetection*0:color.min_y').d[1];

// Red (1) region max y
$('ColorDetection*0:color.max_y').d[1];

// Red (1) region width
$('ColorDetection*0:color.width').d[1];

// Red (1) region height
$('ColorDetection*0:color.height').d[1];

// Red (1) region area
$('ColorDetection*0:color.area').d[1];
```

### Python Code
```python
# Red (1) region x coordinate
__('ColorDetection*0:color.x').d[1]

# Red (1) region y coordinate
__('ColorDetection*0:color.y').d[1]

# Red (1) region min x
__('ColorDetection*0:color.min_x').d[1]

# Red (1) region max x
__('ColorDetection*0:color.max_x').d[1]

# Red (1) region min y
__('ColorDetection*0:color.min_y').d[1]

# Red (1) region max y
__('ColorDetection*0:color.max_y').d[1]

# Red (1) region width
__('ColorDetection*0:color.width').d[1]

# Red (1) region height
__('ColorDetection*0:color.height').d[1]

# Red (1) region area
__('ColorDetection*0:color.area').d[1]
```

## Was the ~ Color Detected?
Returns whether the selected color was detected as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/6fc7ccf9-43bd-4d4f-be6b-f53b73b4b0a4" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| color | Dropdown Option | Recognizable color | Black (0), Red (1), Yellow (2), Green (3), Cyan (4), Blue (5), Magenta (6), White (7) |

### JavaScript Code
```javascript
// Was red (1) detected?
$('ColorDetection*0:color.area').d[1] >= $('ColorDetection*0:color.area_condition').d;

// Was blue (5) detected?
$('ColorDetection*0:color.area').d[5] >= $('ColorDetection*0:color.area_condition').d;
```

### Python Code
```python
# Was red (1) detected?
__('ColorDetection*0:color.area').d[1] >= __('ColorDetection*0:color.area_condition').d

# Was blue (5) detected?
__('ColorDetection*0:color.area').d[5] >= __('ColorDetection*0:color.area_condition').d
```