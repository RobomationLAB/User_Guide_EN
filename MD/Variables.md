We use the term **variable** with the same meaning as in mathematics and other programming languages.  
That is, a variable is a **named element that can store a value and whose value can be changed**.

Variables can be created in several different ways:

- Some blocks, such as **[Count with](https://github.com/RobomationLAB/User_Guide_EN/wiki/Loops#count-with)** and **[For Each Item](https://github.com/RobomationLAB/User_Guide_EN/wiki/Loops#for-each-item)**, use variables and define their values.  
These variables are traditionally called **loop variables** in computer science.
- **User-defined functions** can define input values, which create variables (parameters or arguments) that are only available inside the function.
- Users can create variables at any time using the **set** block. These are traditionally called **global variables**.
- The Block Composer does **not** support **local variables**.

## Dropdown Menu
When you click the dropdown arrow (triangle) next to a variable, the following menu appears.

<img src="https://github.com/user-attachments/assets/690b2dbb-e04b-4953-9d0b-3fed7ff92f33" alt="Block Composer" /><br>  

From this menu, you can select the following options:

- All existing variable names defined in the program are displayed.
- **"Rename variable"**: Renames the selected variable throughout the entire program.  
  When this option is selected, a dialog appears where you can enter a new name.
- **"Delete variable"**: Deletes all blocks in the program that reference this variable.

<br>

# Blocks

## Set
The **Set** block assigns a value to a variable.  
If the variable does not already exist, a new variable is created.  
For example, the block below creates a variable named `"age"` and assigns it the value `12`.

<img src="https://github.com/user-attachments/assets/471ed4a4-8cf4-4e6c-8d45-6d3be51130ba" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var age;
age = 12; // Assigns the value 12 to the variable age
```

### Python Code
```python
age = None
age = 12 # Assigns the value 12 to the variable age
```

## Get Value  
The block below retrieves the value stored in a variable, but does not modify that value.

<img src="https://github.com/user-attachments/assets/f1efacfc-911f-4c4b-8704-75cedf1d64ea" alt="Block Composer" /><br>

It is possible to use a variable without a **Set** block, but this is **not considered good programming practice**.

### JavaScript Code
```javascript
age; // Get the value of the variable
```

### Python Code
```python
age # Get the value of the variable
```

## Change  
The **Change** block adds a number to the current value of a variable.

<img src="https://github.com/user-attachments/assets/cffb360a-a26d-48a0-8ace-40a2c7e4611c" alt="Block Composer" /><br>

The block above is a shorthand expression that performs the same operation as the following code.

<img src="https://github.com/user-attachments/assets/8f1e9c42-e829-4ee7-aa48-8db5b1684ac0" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var age;
age = (typeof age === 'number' ? age : 0) + 1; // Increase the value of age by 1
```

### Python Code
```python
from numbers import Number

age = None
age = (age if isinstance(age, Number) else 0) + 1 # Increase the value of age by 1
```

# Example  
The following is an example demonstrating how variables are used.

<img src="https://github.com/user-attachments/assets/00f0f161-d052-4eb0-8cd1-699fe0a2a536" alt="Block Composer" /><br>

The first block on the first line creates a variable named `"age"` and sets its initial value to the number `12`.  
The second block retrieves the value `12`, adds `1` to it, and then stores the result (`13`) back into the variable.  
The final line displays the following message: "13 years old — happy birthday!"

### JavaScript Code
```javascript
var age;

age = 12;
age = (typeof age === 'number' ? age : 0) + 1; // Add 1 to age
window.alert(String(age) + ' years old — happy birthday!');
```

### Python Code
```python
from numbers import Number

age = None

age = 12
age = (age if isinstance(age, Number) else 0) + 1 # Add 1 to age
print(str(age) + ' years old — happy birthday!')
```