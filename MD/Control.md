In block coding, **control blocks** are used to manipulate the flow of a program.  
They can perform functions such as waiting for a certain amount of time, detecting keyboard input, and outputting logs.

<br>

# Blocks

## Wait
The **Wait** block executes the previous command and then **waits for a specified amount of time** before executing the next command.  
By using this block, you can execute specific actions at fixed intervals or introduce a time delay between actions.

<img src="https://github.com/user-attachments/assets/a327b01d-603b-48cf-b3f7-d2589df466ed" alt="Block Composer"  /><br> 

When this block is executed, it pauses for **x** seconds and then executes the next command.

### Javascript Code
```javascript
await __wait(x * 1000);
```

### Python Code
```python
import asyncio

await asyncio.sleep(x)
```

## Wait 1 Frame
The **Wait 1 Frame** block pauses the program execution for one frame (approximately 0.001 seconds) and then executes the next command.  
It is useful when controlling a program on a frame-by-frame basis.

<img src="https://github.com/user-attachments/assets/8e6f03ce-55f5-4171-90d6-d1b3d3dee4ed" alt="Block Composer" /><br>

When this block is executed, it pauses for one frame (approximately 0.001 seconds) and then executes the next command.

### Javascript Code
```javascript
await __wait(1);
```

### Python Code
```python
import asyncio

await asyncio.sleep(0.001)
```

## Key Down / Key Up
- **Key Down**: Executes an action **when a specific key is pressed**
- **Key Up**: Executes an action **when a specific key is released**

<img src="https://github.com/user-attachments/assets/9c600f41-1d2f-4e47-8b2d-dbb4157e7fa7" alt="Block Composer" /><br>

The **Key Down** and **Key Up** code is shown below.

### Javascript Code
```javascript
__keydown(32); // Spacebar key down  
__keyup(32); // Spacebar key up  
```

### Python Code
```python
__keydown(32) # Spacebar key down  
__keyup(32) # Spacebar key up  
```

This block prints "`stop`" when the spacebar is pressed.

<img src="https://github.com/user-attachments/assets/c7da04ac-5c54-411a-a71f-6529ba9f7b24" alt="Block Composer" /><br>

### Javascript Code
```javascript
if (__keydown(32)) {
    window.alert('stop!');
}
```

### Python Code
```python
if __keydown(32):
    print('stop!')
```

## Key Input
The **Key Input** block can be configured to perform an action **when multiple keys are pressed simultaneously**.  
Using this block, you can detect up to five keys at the same time, including combination keys such as `shift`, `ctrl`, and `alt`.

<img src="https://github.com/user-attachments/assets/a87b7044-a7dc-4bb2-a620-21e206586c6b" alt="Block Composer" /><br>

### Javascript Code
```javascript
__keypressed([32, 38, 0, 0, 0]) // When 32 (spacebar) and 38 (up arrow key) are pressed simultaneously
```

### Python Code
```python
__keypressed([32, 38, 0, 0, 0]) # When 32 (spacebar) and 38 (up arrow key) are pressed simultaneously

```

This block prints "`Keypress event`" when the Shift + Space keys are pressed.

<img src="https://github.com/user-attachments/assets/1ec9879c-8e9f-4182-8022-63828aa8e37d" alt="Block Composer" /><br>

### Javascript Code
```javascript
if (__keypressed([32, 0, 16, 0, 0])) { // When Shift + Space keys are pressed
    window.alert('Keypress event');
}
```

### Python Code
```python
if __keypressed([32, 0, 16, 0, 0]): # When Shift + Space keys are pressed
    print('Keypress event')
```

## Log Output
The **Log Output** block displays specific variable or property values in real time in the **console**, allowing you to analyze program behavior.  
It is useful for checking values or tracking data changes during the debugging process.

<img src="https://github.com/user-attachments/assets/56a39683-a534-4445-82e9-a502406b039b" alt="Block Composer" /><br>

### Javascript Code
```javascript
__log(1, 'A', 'K') // Log output of value 1 with unit K for tag 'A'
```

### Python Code
```python
__log(1, 'A', 'K') # Log output of value 1 with unit K for tag 'A'
```

This is an example of checking a random integer in the console.

<img src="https://github.com/user-attachments/assets/8f7bf8c4-a1f3-43ab-8ede-f4f031bdeed9" alt="Block Composer" /><br>

The result is as follows.

<img src="https://github.com/user-attachments/assets/9b0e22f8-fe23-45c5-b549-6b17f3f9763b" alt="Block Composer" /><br>

### Javascript Code
```javascript
var random;

function mathRandomInt(a, b) { // Random number generation function
    if (a > b) {
        var c = a;
        a = b;
        b = c;
    }
    return Math.floor(Math.random() * (b - a + 1) + a);
}
    
random = mathRandomInt(1, 100);
__log(random, 'A', 'K'); // Log a random integer between 1 and 100 with tag 'A' and unit 'K'
```

### Python Code
```python
import random

random2 = None
random2 = random.randint(1, 100)
__log(random2, 'A', 'K') # Log a random integer between 1 and 100 with tag 'A' and unit 'K'
```

## Scope Output
The **Scope Output** block displays changes in specific values as a real-time graph in the **scope** window, allowing intuitive data analysis.  
You can configure the graph’s color, minimum/maximum values, and range, making it useful for **data visualization** from sensors or for tracking variable changes.

<img src="https://github.com/user-attachments/assets/e919732e-0d26-4ef5-bdb9-573c564a11cd" alt="Block Composer" /><br>

### Javascript Code
```javascript
__scope('_', 0, 1, '#000000', 0); // Display a black scope for value 0 within the range 0 ~ 1
```

### Python Code
```python
__scope('_', 0, 1, '#000000', 0) # Display a black scope for value 0 within the range 0 ~ 1
```

This is an example of checking a random variable value using a red graph.

<img src="https://github.com/user-attachments/assets/7009f92d-4e91-4dc6-a828-8991936d28d2" alt="Block Composer" /><br>

The result is as follows.

<img src="https://github.com/user-attachments/assets/eb3680ac-0236-45b0-b071-7bc32ff506b9" alt="Block Composer" /><br>

### Javascript Code
```javascript
var random;

function mathRandomInt(a, b) { // Random number generation function
    if (a > b) {
        var c = a;
        a = b;
        b = c;
    }
    return Math.floor(Math.random() * (b - a + 1) + a);
}

random = mathRandomInt(1, 100);
__scope('A', 0, 100, '#ff0000', random); // Display a red scope with tag 'A' for a random integer between 1 and 100 within the range 0 ~ 100
```

### Python Code
```python
import random

random2 = None
random2 = random.randint(1, 100)
__scope('A', 0, 100, '#ff0000', 0) # Display a red scope with tag 'A' for a random2 integer between 1 and 100 within the range 0 ~ 100
```