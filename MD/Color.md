Colors are used in a wide range of graphic programs.

# Blocks

## Selecting a Color from the Palette
The simplest way to obtain a color is by using the **Color Picker**.  
This block is displayed as a white rounded rectangle.  

When you click it, a color palette appears, allowing you to select the desired color.

<img src="https://github.com/user-attachments/assets/650abf0e-a78f-45e7-93e7-4ac11efd1aa4" alt="Block Composer" /><br> 

### JavaScript Code
```javascript
[0, 0, 0]; // Default color: Black
[255, 0, 0]; // Default color: Red
[255, 255, 0]; // Default color: Yellow
[0, 255, 0]; // Default color: Green
[0, 255, 255]; // Default color: Cyan
[0, 0, 255]; // Default color: Blue
[255, 0, 255]; // Default color: Magenta
[255, 255, 255]; // Default color: White
```

### Python Code
```python
[0, 0, 0] # Default color: Black
[255, 0, 0] # Default color: Red
[255, 255, 0] # Default color: Yellow
[0, 255, 0] # Default color: Green
[0, 255, 255] # Default color: Cyan
[0, 0, 255] # Default color: Blue
[255, 0, 255] # Default color: Magenta
[255, 255, 255] # Default color: White
```

## Creating a Color Using Red, Green, and Blue (RGB) Values
By using the **Color Settings** block, you can specify the desired proportions of red, green, and blue.  
In the example below, red and blue are set to their maximum values and green is set to 0, creating a purple color.

<img src="https://github.com/user-attachments/assets/e60d0a47-1a20-4605-be4c-f89b73d39507" alt="Block Composer" /><br>

Each color component ranges from 0 to 255 (inclusive).

### JavaScript Code
```javascript
[255, 0, 255]; // R : 255, G : 0, B : 255
```

### Python Code
```python
[255, 0, 255] # R : 255, G : 0, B : 255
```

## Creating Colors Using Sliders
 
This block provides a feature for selecting colors using **sliders**.  
Users can adjust the sliders to manually combine their desired **color**.  
Each slider controls the Red (R), Green (G), and Blue (B) values, and the button on the right can be used to adjust the **brightness** (lightness).

<img src="https://github.com/user-attachments/assets/4fd6aace-48ea-4769-9fe7-d53f2bf297e2" alt="Block Composer" /><br>

When the slider values are changed, the result is applied immediately, and the selected color is displayed in real time in the R, G, and B fields.

### JavaScript Code
```javascript
[90, 85, 224]; // R : 90, G : 85, B : 224 
```

### Python Code
```python
[90, 85, 224] # R : 90, G : 85, B : 224 
```

## Generating Random Colors  
The **Random Color** block generates a random color each time it is called.

<img src="https://github.com/user-attachments/assets/4e4283e9-d0fb-4210-9731-4b32a6fd6d04" alt="Block Composer" /><br>

This block assigns random values between 0 and 255 (inclusive) to the red, green, and blue components.

### JavaScript Code
```javascript
__randomColor(); // Generate a random color
```

### Python Code
```python
__randomColor() # Generate a random color
```

# Technical Details  
In Block Composer, colors are represented as text in the format `"rr,gg,bb"`.  
Here, `"rr"`, `"gg"`, and `"bb"` represent the red, green, and blue values (0–255), respectively.  
Normally, users do not see this format directly, but it can be observed by running the program below.

<img src="https://github.com/user-attachments/assets/80b39164-cf9f-41df-9cdc-fc010a8d1754" alt="Block Composer" /><br>

The program above outputs `"255,255,255"`.

### JavaScript Code
```javascript
window.alert([255, 255, 255]); // Outputs "255,255,255"
```

### Python Code
```python
print([255, 255, 255]) # Outputs "255,255,255"
```

As a side note, mixing light is different from mixing paint.  
When red, green, and blue light are mixed in equal proportions, the result is white,  
but mixing paints produces a dull, muddy color.
