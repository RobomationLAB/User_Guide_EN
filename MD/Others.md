In block coding, **Other Blocks** consist of blocks that do not affect program execution or robot behavior.    
They are used to add comments or force the termination of program execution.

# Blocks

## Comments
The **Comment** block allows you to add explanations without affecting code execution. without affecting code execution.  
Using comments improves code readability and makes maintenance easier.

<img src="https://github.com/user-attachments/assets/f40a9c04-1d7b-42cf-8dd5-4405907794e9" alt="Block Composer" /><br> 

<img src="https://github.com/user-attachments/assets/c6fb339e-18c0-4195-8e53-93a2d5c9a8b8" alt="Block Composer"/><br>

### JavaScript Code
```javascript
// Single-line comment

// Multi-line comment
// Continued input
```

### Python Code
```python
# Single-line comment

# Multi-line comment
# Continued input
```

## Link
Using the **Link** block, you can add a **page URL** you want to open by leveraging the **comment** feature.  
When you click the **Open** button, it navigates to the page at the entered link.

<img src="https://github.com/user-attachments/assets/8e915ce4-a878-40e6-870f-1b3a4bcb26f1" alt="Block Composer"/><br>

### JavaScript Code
```javascript
// https://google.com
```

### Python Code
```python
# https://google.com
```

## Exit
The **Exit** block immediately stops program execution and refreshes the page and resets the program to its initial state.  
It is useful when you need to add a forced termination feature under specific conditions.

<img src="https://github.com/user-attachments/assets/f0ae357b-2cc0-40cb-aea7-177fb516d2c0" alt="Block Composer" /><br>

### Javascript Code
```javascript
__exit(); // Exit
```

### Python Code
```python
__exit() # Exit
```
