Conditional statements play a crucial role in computer programming.  
By using conditional statements, you can express sentences such as the following:

- If there is a path on the left, turn left.
- If the score is 100, print "Well done!"

<br>

# Blocks

## If
The simplest conditional statement is the **If** block.  
It can be represented as shown below:

<img src="https://github.com/user-attachments/assets/9056ecc8-6aa6-41f7-8720-6738ec2f01ee" alt="Block Composer" /><br> 

When this block is executed, it compares the value of variable **x** with 100.   
If the value is greater than 100, "It is a large number." is printed.   
Otherwise, no code inside the block is executed.  

### Javascript Code
```javascript
if (x > 100) {
    window.alert("It is a large number.");
}
```

### Python Code
```python
if x > 100:
    print("It is a large number.")
```
</details>


## If–Else
You can also specify what to do when the condition is not true.  
An example is shown below:

<img src="https://github.com/user-attachments/assets/1d34565f-f9e4-4e97-9689-b7be8f82de5d" alt="Block Composer" /><br>

As in the previous block, if **x** is greater than 100, "It is a large number." is printed.  
Otherwise, "It is not a large number." is printed.

The **If** block can have only one **Else** section, and no more than one is allowed.

### Javascript Code
```javascript
if (x > 100) {
    window.alert('It is a large number.');
} else {
    window.alert('It is not a large number.');
}
```

### Python Code
```python
if x > 100:
    print('It is a large number.')
else:
    print('It is not a large number.')
```
</details>

## If–Else If
You can test multiple conditions within a single **If** block.  
This is made possible by adding **Else If** sections:

<img src="https://github.com/user-attachments/assets/27645936-fecd-46bb-af83-3464b5d25c4c" alt="Block Composer" /><br>

This block first checks whether **x** is greater than 100, and if so, prints "It is a large number."  
Otherwise, it checks whether **x** is equal to 42, and if so, prints "It is a lucky number."  
If neither condition is met, nothing happens.

An **If** block can have multiple **Else If** sections.  
Conditions are evaluated from top to bottom, and execution stops when one condition is satisfied or no conditions remain.

### Javascript Code
```javascript
if (x > 100) {
    window.alert('It is a large number.');
} else if (x === 42) {
    window.alert('It is a lucky number.');
}
```

### Python Code
```python
if x > 100:
    print('It is a large number.')
elif x == 42:
    print('It is a lucky number.')
```
</details>

## If–Else If–Else
As shown below, an **If** block can have both **Else If** and **Else** sections:

<img src="https://github.com/user-attachments/assets/5aed514e-3334-4143-a30b-3f53cf9f3e2d" alt="Block Composer" /><br>

The **Else** section ensures that some action is performed even if all preceding conditions are not true.

The **Else** section can come after any number of **Else If** sections, including zero.

### Javascript Code
```javascript
if (x > 100) {
    window.alert('It is a large number.');
} else if (x === 42) {
    window.alert('It is a lucky number.');
} else {
    window.alert('It is not a large number.');
}
```

### Python Code
```python
if x > 100:
    print('It is a large number.')
elif x == 42:
    print('It is a lucky number.')
else:
    print('It is not a large number.')
```
</details>  
<br>

# How to Modify Blocks
Only a simple **If** block appears in the toolbox:

<img src="https://github.com/user-attachments/assets/45e1acac-d036-448d-bc85-7acfa6207e85" alt="Block Composer" /><br>

To add **Else If** and **Else** clauses, click the gear icon to open a new window:


<img src="https://github.com/user-attachments/assets/975931b1-78b4-4e3c-be04-5351880e5192" alt="Block Composer" /><br>


Drag the **Else If** and **Else** clauses under the **If** block, where you can reorder or remove them.  
When finished, click the gear icon again to close the window:


<img src="https://github.com/user-attachments/assets/9539b5c3-2b33-4a1f-b688-1795a929561d" alt="Block Composer" /><br>


You can add as many **Else If** sub-blocks as you want, but note that only **one Else** block can be added.
