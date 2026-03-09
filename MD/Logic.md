Logic blocks are generally used to control [condition blocks](https://github.com/RobomationLAB/User_Guide_EN/wiki/conditional-statement) and [loop blocks](https://github.com/RobomationLAB/User_Guide_EN/wiki/loops).

Below is an example:

<img src="https://github.com/user-attachments/assets/34845cdc-c5f1-4338-9874-15293ed9cef5" alt="Block Composer" /><br> 

If the value of variable **x** is greater than 100, the condition becomes **true** and the text "It is a large number." is printed.   
If the value of **x** is not greater than 100, the condition becomes **false** and "It is not a large number." is printed.  

**Boolean** is a simple data type that has only two possible values:
- **True**
- **False**

Boolean values can be stored in variables or passed to functions, and they can be used in the same way as numbers, text, or list values.

# Blocks
When a block requires a Boolean value as input, an empty input is generally interpreted as **false**.

You cannot directly connect a non-Boolean value to an input that expects a Boolean.  
However, it is possible to store that value in a variable first and then pass it as input.

That said, this approach is not recommended, and its behavior may change in future versions.

## Value
You can obtain a Boolean value by using a single block with a dropdown that allows you to select **True** or **False**:

<img src="https://github.com/user-attachments/assets/5f5236fb-db64-4935-a475-90b95df803d7" alt="Block Composer" /><br>

### JavaScript Code

```javascript
true    // true
false   // false
```

### Python Code
```python
True    # true
False   # false
```

## Comparison
There are six comparison operators.  
Each operator takes two inputs (such as numbers or text) and returns true or false depending on how the input values are compared.

<img src="https://github.com/user-attachments/assets/75584fda-28dd-4b7e-ad51-7d740da06235" alt="Block Composer" /><br>

The six comparison operators are as follows:  
- equal to  
- not equal to  
- less than  
- greater than  
- less than or equal to  
- greater than or equal to  

### JavaScript Code
```javascript
x == 42    // equal to
x != 42    // not equal to
x < 42     // less than
x > 42     // greater than
x <= 42    // less than or equal to
x >= 42    // greater than or equal to
```

### Python Code
```python
x == 42    # equal to
x != 42    # not equal to
x < 42     # less than
x > 42     # greater than
x <= 42    # less than or equal to
x >= 42    # greater than or equal to
```

## Logical Operations
The **AND** block returns true only when both inputs are true.

<img src="https://github.com/user-attachments/assets/77387cdf-c1b3-4d96-afc5-4f7d9b7d4bcf" alt="Block Composer" /><br>

The **OR** block returns true if at least one of the two inputs is true.

<img src="https://github.com/user-attachments/assets/904e819a-1c15-4dcd-bbf0-41fed04e4964" alt="Block Composer" /><br>

### JavaScript Code

```javascript
x >= 0 && x < 360   // AND
x == 1 || x == 2   // OR
```

### Python Code
```python
x >= 0 and x < 360  # AND
x == 1 or x == 2    # OR
```

## NOT  
The **NOT** block inverts a boolean input.  
That is, it converts a boolean value to its opposite.

For example, the following results are produced:

<img src="https://github.com/user-attachments/assets/56995371-e00b-4d45-a0ac-c78866144007" alt="Block Composer" /><br>

**False** is returned.

As mentioned above, if no input is provided, the default value is considered **true**,  
so the block below returns **false**.

<img src="https://github.com/user-attachments/assets/b1deec6f-2089-4f94-ab13-cea93514d17e" alt="Block Composer" /><br>

Leaving the input empty is not recommended.

### JavaScript Code
```javascript
!true        // or false
```

### Python Code
```python
not True     # or False
```

## Ternary Operator  
The ternary block works like a simple if statement.  
It takes three inputs.  

The first input is a boolean condition to test.  
The second input is the value to return when the condition is **true**.  
The third input is the value to return when the condition is **false**.  

In the example below, if the variable **x** is less than 10, the variable **color** is set to red;  
otherwise, the variable **color** is set to green.

<img src="https://github.com/user-attachments/assets/39591d8d-9c46-4558-9d1d-8137bb2efc3b" alt="Block Composer" /><br>

The ternary block can always be replaced with a conditional (if) block.  
The two examples below behave the same way.  

<img src="https://github.com/user-attachments/assets/ea803634-2d92-43e9-a838-8c37dfb80781" alt="Block Composer" /><br>

### JavaScript
```javascript
x == 0 ? 'Game Over!' : 'Keep Playing'
```

### Python Code
```python
'Game Over!' if x == 0 else 'Keep Playing'
```