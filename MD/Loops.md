There are two types of control blocks:  
[**Conditions**](https://github.com/RobomationLAB/User_Guide_EN/wiki/Conditional-Statement) and **Loops** (which control how many times a block’s body is executed, based on variable values)

<br>

# Loop Blocks

## Repeat
The simplest **Repeat** block executes the code inside it a specified number of times.  
For example, the block below prints "`Hello!`" ten times.

<img src="https://github.com/user-attachments/assets/43682d0a-7716-4ba5-940e-de4853a635f1" alt="Block Composer" /><br> 

### JavaScript Code
```javascript
for (var count = 0; count < 10; count++) { // repeat 10 times
    window.alert('Hello');
}
```

### Python Code
```python       
for count in range(10): # repeat 10 times
    print('Hello')
```

## Repeat While
Consider a game where a player rolls a die and keeps adding the values until the total is less than 30.  
The blocks below implement that game:

1. A variable called **total** is initialized to 0.
2. The loop starts by checking whether **total** is less than 30. If it is, the blocks inside the loop are executed.
3. A random number from 1 to 6 is generated (rolling the die) and stored in a variable called **roll**.
4. The rolled number is displayed.
5. The **total** variable is increased by the value of **roll**.
6. When the loop finishes one iteration, control returns to step 2.

<img src="https://github.com/user-attachments/assets/f5fa5209-829f-48f3-8e85-e2c6e8c8ec94" alt="Block Composer" /><br>


When the loop finishes, the blocks that follow it are executed (omitted here).  
In this example, random numbers from 1 to 6 are printed several times, and then the loop ends.  
The sum of those numbers is stored in the **total** variable.  
This sum will be at least 30.

### JavaScript Code
```javascript
var roll, total;

function mathRandomInt(a, b) { // random integer function
    if (a > b) {
        var c = a;
        a = b;
        b = c;
    }
    return Math.floor(Math.random() * (b - a + 1) + a);
}

total = 0;
while (total < 30) { // repeat while total is less than 30
    roll = mathRandomInt(1, 6);
    window.alert(roll);
    total = (typeof total === 'number' ? total : 0) + roll;
    await __wait(10);
}
```

### Python Code
```python
import asyncio
import random
from numbers import Number

roll = None
total = None

total = 0
while total < 30:  # repeat while total is less than 30
    roll = random.randint(1, 6)
    print(roll)
    total = (total if isinstance(total, Number) else 0) + roll
    await asyncio.sleep(0.01)
```

## Repeat Until
The **Repeat Until** loop executes the body while the condition is false, and exits the loop as soon as the condition becomes true.  
The blocks below produce the same result as the previous example.  
The loop continues repeating until **total** becomes 30 or greater.

<img src="https://github.com/user-attachments/assets/b9ed1423-6729-4dfa-b6e4-a1d96b70ac59" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var total, roll;

function mathRandomInt(a, b) {
    if (a > b) { // random number helper function
        var c = a;
        a = b;
        b = c;
    }
    return Math.floor(Math.random() * (b - a + 1) + a);
}

total = 0;
while (!(total >= 30)) { // repeat until total becomes 30 or greater
    roll = mathRandomInt(1, 6); 
    window.alert(roll);         
    total = (typeof total === 'number' ? total : 0) + roll; 
    await __wait(10);         
}
```

### Python Code
```python
import asyncio
import random
from numbers import Number

total = None
roll = None

total = 0
while not (total >= 30):  # repeat until total becomes 30 or greater
    roll = random.randint(1, 6)  
    print(roll)                  
    total = (total if isinstance(total, Number) else 0) + roll  
    await asyncio.sleep(0.01)    
```

## Count with

The **Count with** block (commonly called a **for loop**) runs the code inside its body once for each value of a variable,  
starting from the first value and increasing by the specified step until it reaches the final value.
For example, the program below outputs 1, 3, 5.

<img src="https://github.com/user-attachments/assets/8830dfbb-515c-4a4a-b3ac-12311d1de392" alt="Block Composer" /><br>


### JavaScript Code

```javascript
var index;

for (index = 1; index <= 5; index += 2) {
    window.alert(index);
}
```

### Python Code

```python
index = None

for index in range(1, 6, 2):
    print(index)
```

The following two loop blocks work even when the first value is greater than the second value.  
They behave the same way regardless of whether the third value (the step/increment) is positive or negative.

<img src="https://github.com/user-attachments/assets/0e577588-f827-4c5d-8eff-6c5fa2ebeb4a" alt="Block Composer" /><br>

### JavaScript Code

```javascript
var index;

for (index = 5; index >= 1; index -= 2) {
    window.alert(index);
}
```

### Python Code
```python
index = None

for index in range(5, 0, -2):
    print(index)
```

## For Each Item
The **for each item** block works similarly to a loop, but instead of using a numeric counter, it iterates through the values of a list in order.

The program below outputs each item in the list:
“first”, “second”, “third”.

<img src="https://github.com/user-attachments/assets/c65eec10-9645-4f07-8759-cc7a89bb7bc6" alt="Block Composer" /><br>


### JavaScript Code
```javascript
var letter;

var letter_list = ['First', 'Second', 'Third'];
for (var letter_index in letter_list) { // for each item
    letter = letter_list[letter_index];
    window.alert(letter);
}
```

### Python Code
```python
letter = None

for letter in ['First', 'Second', 'Third']: # for each item
    print(letter)
```

<br>

# Loop Termination Blocks
Most loops run **until a termination condition is met** (as in conditional loops) or **until all values of the loop variable have been processed** (as in **count with** and **for each item** loops).  
Although they are used less frequently, there are two useful blocks that provide additional ways to control loop behavior.  
The examples below use a **for each item** loop, but these blocks can be used with all types of loops.

## Continue (Next Iteration)
The **continue** block (called **continue** in most programming languages) skips the remaining code in the current loop body and immediately starts the next iteration (pass).

In the following program:
During the first iteration, `"First"` is printed.
During the second iteration, the **continue** block is executed, so printing `"Second"` is skipped.
During the final iteration, `"Third"` is printed.

<img src="https://github.com/user-attachments/assets/8c873815-d355-490a-90e7-1bea95d37021" alt="Block Composer" /><br>


### JavaScript Code
```javascript
var letter;

var letter_list = ['First', 'Second', 'Third'];
for (var letter_index in letter_list) {
    letter = letter_list[letter_index];
    if (letter == 'Second') {
        continue; // skip to the next iteration
    }
    window.alert(letter);
}
```

### Python Code
```python
letter = None

for letter in ['First', 'Second', 'Third']:
    if letter == 'Second':
        continue  # skip to the next iteration
    print(letter)
```

## Break
The **Break** block allows you to **exit a loop early**.

In the program below:
During the first iteration, `"First"` is printed.   
During the second iteration, when the variable value is `"Second"`, the **break loop** block is executed and the loop exits immediately.  
As a result, the `"Third"` item in the list is not printed.  

<img src="https://github.com/user-attachments/assets/a82d005f-08e0-4b16-a34d-92a5006ea477" alt="Block Composer"  /><br>


### JavaScript Code
```javascript
var letter;

var letter_list = ['First', 'Second', 'Third'];
for (var letter_index in letter_list) {
    letter = letter_list[letter_index];
    if (letter == 'Second') {
        break; // break loop
    }
    window.alert(letter);
}
```

### Python Code
```python
letter = None

for letter in ['First', 'Second', 'Third']:
    if letter == 'Second':
        break  # break loop
    print(letter)
```
