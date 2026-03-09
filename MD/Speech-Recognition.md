# Blocks
## Set Language
Sets the speech recognition language.  
Even if you do not set the language, it will be set automatically.


<img src="https://github.com/user-attachments/assets/93818cdc-fb13-48e4-a0e6-c7f1e48f6d85" width="100%" height="100%" >


### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| language | Dropdown Option | Recognition language | en-US (English), ko-KR (Korean) | 

### JavaScript Code
```javascript
// Set speech recognition language to English
$('ASR*0:lang').d = 'en-US';

// Set speech recognition language to Korean
$('ASR*0:lang').d = 'ko-KR';
```

### Python Code
```python
# Set speech recognition language to English
__('ASR*0:lang').d = 'en-US'

# Set speech recognition language to Korean
__('ASR*0:lang').d = 'ko-KR'
```

## Start / Stop Speech Recognition
Starts or stops speech recognition.

<img src="https://github.com/user-attachments/assets/a4a4c547-bc2e-4480-8c1a-44a92da5d86e" width="80%" height="80%" >

### Dropdown Options and Input Values
| Name | Type | Description | Range / Type |  
| ------ | ------ | ------ | ------ |
| toggle | Dropdown Option | Speech recognition on/off | Start (1), Stop (0) |

### JavaScript Code
```javascript
// Start speech recognition
$('ASR*0:listen').d = 1;

// Stop speech recognition
$('ASR*0:listen').d = 0;
```

### Python Code
```python
# Start speech recognition
__('ASR*0:listen').d = 1

# Stop speech recognition
__('ASR*0:listen').d = 0
```

## Speech Recognition Result
Returns the speech recognition result.


<img src="https://github.com/user-attachments/assets/fa4c0fd2-6f86-4ca2-9224-de6579533e6f" width="50%" height="50%" >

### JavaScript Code
```javascript
// Speech recognition result
$('ASR*0:result').d;
```

### Python Code
```python
# Speech recognition result
__('ASR*0:result').d
```

## Is Speech Recognition Active?
Returns whether speech recognition is active as **True (1) / False (0)**.

<img src="https://github.com/user-attachments/assets/f22a231d-0eef-45be-accd-2e28529f1fa1" width="60%" height="60%" >

### JavaScript Code
```javascript
// Is speech recognition active?
$('ASR*0:state').d;
```

### Python Code
```python
# Is speech recognition active?
__('ASR*0:state').d
```