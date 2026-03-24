By using sound blocks, you can play various sound effects and voice audio.

<br>

# Blocks

## Playing Sounds
The **Play Sound** block plays a selected sound at a specified **volume**.
- **Volume Control:** Allows you to adjust the sound volume.
- **Loop Playback:** When the loop checkbox is enabled, the selected sound will repeat continuously.

<img src="https://github.com/user-attachments/assets/6cb8b4ff-ae38-4641-84b9-67a133b41951" alt="Block Composer" /><br> 

### Javascript Code
```javascript
__playSound('', 100, false);
```

### Python Code
```python
__playSound('', 100, False)
```
### Adding Sounds
You can select the desired sound from the **Sound Menu** at the top.

<img src="https://github.com/user-attachments/assets/82ba756e-6841-4973-b82a-89c6ffc00173" alt="Block Composer" /><br>

Before selecting a sound from the list, you can preview it by listening directly.

<img src="https://github.com/user-attachments/assets/51260cb8-0274-4b86-9ea5-668101c7e8b2" alt="Block Composer" /><br>


By using the sound adding feature, you can directly add the sound effects you want to your project.
- Added sounds can be found in the list on the left.
- You can preview a selected sound from the list, and delete any sounds you no longer need.

### Selecting a Sound
Click the arrow below the block to view and select from the added sounds.

<img src="https://github.com/user-attachments/assets/858ce60e-4d1b-4463-ae2a-5945413cda6e" alt="Block Composer" /><br>

### Javascript Code
```javascript
__playSound('Notes/A Elec Bass', 100, false); // Select the Notes/A Elec Bass sound
```

### Python Code
```python
__playSound('Notes/A Elec Bass', 100, False) # Select the Notes/A Elec Bass sound
```

## Setting Language and Voice
This block allows you to set the **language** and **voice** used for sound playback.  
You can choose from a variety of languages and voices to produce more natural-sounding speech.

<img src="https://github.com/user-attachments/assets/67730a47-165d-41a4-813d-148e0f380927" alt="Block Composer" /><br>

### JavaScript Code
```javascript
__setTTSOption('en-US', 'Microsoft Mark - English (United States)'); // Use English, Microsoft Mark voice
```

### Python Code
```python
__setTTSOption('en-US', 'Microsoft Mark - English (United States)') # Use English, Microsoft Mark voice
```

- Language Selection: You can choose the desired language.
- Voice Selection: You can choose the desired voice from a variety of options.

<img src="https://github.com/user-attachments/assets/79393109-ef92-4a1c-882e-b338fb044b0e" alt="Block Composer" /><br>

<img src="https://github.com/user-attachments/assets/c1c8e7d4-9abd-4c54-b97e-c55b04b4287b" alt="Block Composer" /><br>

### JavaScript Code
```javascript
__setTTSOption('ko-KR', 'Microsoft Heami - Korean (Korean)'); // Use Korean, Heami voice
```

### Python Code
```python
__setTTSOption('ko-KR', 'Microsoft Heami - Korean (Korean)') # Use Korean, Heami voice
```

## Speaking Text
This block converts the input text into speech and plays it aloud.  
By using this block, you can output any desired **sentence as speech** in your project.

<img src="https://github.com/user-attachments/assets/2c651b92-d32f-4d2d-939d-8da36b0f460e" alt="Block Composer" /><br>

- Text Input: Enter the desired sentence to convert it into speech and play it.

### JavaScript Code
```javascript
__speak(''); // Output the sentence as speech
```

### Python Code
```python
__speak('') # Output the sentence as speech
```