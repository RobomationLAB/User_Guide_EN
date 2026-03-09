A **Function** is a **collection of blocks (commands)** that performs a specific task.  
By defining frequently used actions as a single function, you can manage code in a **concise and efficient** way.

Functions have the following characteristics:  
- **Reusability**: Once defined, a function can be called and used multiple times.  
- **Input and Output**: A function can receive parameters (input values), process them, and can return a result (output value).  
- **Improved Readability**: Functions help structure the program flow in a logical and organized manner.

<br>

# Function Blocks
In block-based coding, users can define custom functionality using **function blocks**.

### Function Definition Block  
By using a function definition block, you can create a **new function**.  
The example below shows how to define a function named `func`.

<img src="https://github.com/user-attachments/assets/ab462ed2-0a79-4ccc-adfd-b88295ee3f17" alt="Block Composer" /><br> 

### JavaScript Code
```javascript
function func() { // define the function func
}
```

### Python Code
```python
def func():  # define the function func
    pass
```

### Functions with Parameters
The function block has a gear button, which you can click to **add parameters (input values)**.

- **Parameters** are **input values that are passed to a function**.

<img src="https://github.com/user-attachments/assets/d2630130-a1b3-488a-9d60-ea6a833b6889" alt="Block Composer" /><br>

**How to Set Parameters**  
1. Add the required variables (such as x, y, etc.) in the parameter block.  
2. When they are connected to the parameter list on the right, a function with parameters is created.

<img src="https://github.com/user-attachments/assets/a59b8c66-14d8-4f70-807e-e9aaf4bbdfb3" alt="Block Composer" /><br>

You can define a function `xyFunction` that has parameters x and y, and use those parameters inside the function.

### JavaScript Code
```javascript
var x, y;

function xyFunction(x, y) { // Define xyFunction with parameters x and y
}
```

### Python Code
```python
x = None
y = None

def xyFunction(x, y):  # Define xyFunction with parameters x and y
    pass
```

### Calling a Function (User-Defined Function Block)
When a function is defined, a **user-defined function block** is automatically created.  
Using this block, you can **call and execute the predefined function**.

Below is an example of a block that calls the previously created xyFunction **function**.

<img src="https://github.com/user-attachments/assets/a1fb9e25-bf70-4810-86db-9cb22d215ace" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var x, y;

function xyFunction(x, y) {
}

xyFunction(null, null); // function call
```

### Python Code
```python
x = None
y = None

def xyFunction(x, y):
    pass

xyFunction(None, None)  # function call
```

In addition, by clicking the `?` icon, you can add a a description (comment) to the function, making it easier to explain and understand what the function does.

The image below shows an example of adding a **comment** to a function.

<img src="https://github.com/user-attachments/assets/cb9b1721-8e69-4b92-a8df-c320117d2c65" alt="Block Composer" /><br>

### JavaScript Code
```javascript
// Describe this function...
function func() {
}
```

### Python Code
```python
# Describe this function...
def func():
    pass
```

## Functions Without a Return Value

A function without a return value performs a specific action but **does not return any value**.

The following example shows a function that prints `"hello"`.  
This function only outputs `"hello"` and does not return any specific value.

<img src="https://github.com/user-attachments/assets/b55156b5-201f-4d30-b0b7-18c014ac6594" alt="Block Composer" /><br>

### JavaScript Code
```javascript
function func() { // Define a function without a return value
    window.alert('hello');
}
```

### Python Code
```python
def func():  # Define a function without a return value
    print('hello')
```

When you run the block below, `"hello"` is displayed on the screen.

<img src="https://github.com/user-attachments/assets/3ddc61cc-fef2-48e4-a34b-4b3d2d21b025" alt="Block Composer" /><br>

### JavaScript Code
```javascript
function func() {
    window.alert('hello');
}
func(); // Call a function with no return value
```

### Python Code
```python
def func():
    print('hello')  # Call a function with no return value
func()
```

## Functions with a Return Value  
A function with a return value performs a specific task and then **returns a result value** that can be used by other blocks or code.

The function below returns the sum of two numbers.  
It **takes parameters x and y and returns the result of x + y**.

<img src="https://github.com/user-attachments/assets/de44c6e3-2d3b-4d5c-84df-a1f8571d7b60" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var x, y, sum;

function xyFunction(x, y) { // Define a function with a return value
    sum = x + y;
    return sum;
}
```

### Python Code
```python
x = None
y = None
sum2 = None  # Use sum2 because 'sum' is a reserved keyword in Python

def xyFunction(x, y):  # Define a function with a return value
    global sum2
    sum2 = x + y
    return sum2
```

You can call the function below and store the returned result in the variable `result` for later use.

<img src="https://github.com/user-attachments/assets/3392a8e2-f3d5-45f4-8719-6539882a64fd" alt="Block Composer" /><br>

### Function Execution Example (Returns 10 + 20 = 30)

`30` is printed as the output.

### JavaScript Code
```javascript
var x, y, result, sum;

function xyFunction(x, y) {
    sum = x + y;
    return sum;
}

result = xyFunction(10, 20); // Call a function with a return value
window.alert(result);
```

### Python Code
```python
x = None
y = None
result = None
sum2 = None  # Use sum2 because sum is a reserved keyword

def xyFunction(x, y):  # Function with a return value
    global result, sum2
    sum2 = x + y
    return sum2

result = xyFunction(10, 20)
print(result)
```

## Block That Returns a Value Under a Specific Condition (If Return Block)

This block performs the function of **immediately returning a value and terminating the function when a specific condition is satisfied** within a function.

This block **can only be used inside a function**, and it is disabled in all other contexts.

<img src="https://github.com/user-attachments/assets/0c8625a3-eb7f-4045-b3a2-735df49b76f8" alt="Block Composer" /><br>

This function returns the sum of x and y, but if the sum is less than 0, it returns -1 instead.

<img src="https://github.com/user-attachments/assets/97f31049-e9e1-4552-94cb-31fa60480ffb"  alt="Block Composer" /><br>

### JavaScript Code
```javascript
var x, y, sum;

function xyFunction(x, y) {
    sum = x + y;
    if (sum < 0) { // If sum < 0, return -1
        return -1;
    }
    return sum;
}
```

### Python Code
```python
x = None
y = None
sum2 = None  # Use sum2 because sum is a reserved keyword

def xyFunction(x, y):
    global sum2
    sum2 = x + y
    if sum2 < 0:  # If sum < 0, return -1
        return -1
    return sum2
```

<img src="https://github.com/user-attachments/assets/3392a8e2-f3d5-45f4-8719-6539882a64fd" alt="Block Composer"  /><br>

-1 is printed.

### JavaScript Code
```javascript
var x, y, result, sum;

function xyFunction(x, y) {
    sum = x + y;
    if (sum < 0) {
        return -1;
    }
    return sum;
}

result = xyFunction(-10, -20); // (-10) + (-20) < 0, so return -1
window.alert(result);
```

### Python Code
```python
x = None
y = None
result = None
sum2 = None  # Use sum2 because sum is a reserved keyword

def xyFunction(x, y):
    global result, sum2
    sum2 = x + y
    if sum2 < 0:
        return -1
    return sum2

result = xyFunction(-10, -20)  # (-10) + (-20) < 0, so return -1
print(result)
```