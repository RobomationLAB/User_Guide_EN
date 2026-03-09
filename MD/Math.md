This document explains the functions and usage of various calculation blocks.  
It introduces blocks that perform a wide range of mathematical operations, including numeric calculations, list processing, probability, and angle operations.

<br>

# Blocks

## Number Value
This block returns the entered **numeric value** as it is.  
By using this block, you can store a specific number in a variable or use it in other calculations.

<img src="https://github.com/user-attachments/assets/b0b53973-903a-4241-8bd8-a9315d47f747" alt="Block Composer" /><br> 

### JavaScript Code
```javascript
10; // Numeric value 10
```

### Python Code
```python
10 # Numeric value 10
```

## Creating and Operating on Arrays
This block creates an **array**.  
It returns an array whose elements are the values entered inside `[]`.  
You can create a list by entering the desired values inside `[]`, and strings must be enclosed in quotation marks `" "`.

<img src="https://github.com/user-attachments/assets/4897294b-ad31-4b2b-b43d-2ccb1382769a" alt="Block Composer" /><br>

The block above creates `["one", "two", 3]` and outputs `one`, `two`, and `3` in order.

### JavaScript Code
```javascript
var item;

var item_list = ["one", "two", 3 ]; // Create array
for (var item_index in item_list) {
    item = item_list[item_index];
    window.alert(item);
}
```

### Python Code
```python
item = None

for item in ["one", "two", 3 ]: # Create array
    print(item)
```

## Basic Arithmetic Operations
This block performs **arithmetic operations** (addition, subtraction, multiplication, division, and exponentiation) using two numeric values.

<img src="https://github.com/user-attachments/assets/ec4f9583-6557-405d-a6d7-009cf3abc3b4" alt="Block Composer" /><br>

The block above calculates `1 + 1` and returns `2`.

### JavaScript Code
```javascript
1 + 1; // 1 + 1 operation
1 - 1; // 1 - 1 operation
1 * 1; // 1 * 1 operation
1 / 1; // 1 / 1 operation
Math.pow(1, 1); // 1^1 operation
```

### Python Code
```python
1 + 1 # 1 + 1 operation
1 - 1 # 1 - 1 operation
1 * 1 # 1 * 1 operation
1 / 1 # 1 / 1 operation
1 ** 1 # 1^1 operation
```

## Advanced Operations

### Square Root
Returns the **square root** of the given number.

<img src="https://github.com/user-attachments/assets/ebc3d4ef-210a-4c36-ba53-1f56378825b9"alt="Block Composer"  /><br>

The block above calculates the square root of `9` and returns `3`.

### JavaScript Code
```javascript
Math.sqrt(9); // Square root of 9
```

### Python Code
```python
import math

math.sqrt(9) # Square root of 9
```

### Absolute Value
Returns the **absolute value** of the given number.

<img src="https://github.com/user-attachments/assets/3144ec30-59df-41cd-812f-793979d6fa81" alt="Block Composer" /><br>

The value of the following block is `10`.

### Javascript Code
```javascript
Math.abs(-10); // Absolute value of -10
```

### Python Code
```python
import math

math.fabs(-10) # Absolute value of -10
```

### Sign
Reverses the **sign** of the input number.

<img src="https://github.com/user-attachments/assets/7f3ca837-00c1-45f7-8e31-3103821f04af" alt="Block Composer" /><br>

The value of the following block is `-10`.

### Javascript Code
```javascript
-10; // Opposite sign of 10
```

### Python Code
```python
import math

-10 # Opposite sign of 10
```

### Exponential and Logarithmic Functions
This block calculates **exponential and logarithmic** values.  
It is used to compute powers or logarithms with a specific base.

<img src="https://github.com/user-attachments/assets/4147d1e4-1ce7-4b78-96dd-f9a250297466" alt="Block Composer" /><br>

### Javascript Code
```javascript
Math.log(10); // Natural logarithm of 10  
Math.log(10)/ Math.log(10); // log base 10 of 10   
Math.exp(2); // e squared  
Math.pow(10,2); // 10 squared  
```

### Python Code
```python
import math

math.log(10) # Natural logarithm of 10  
math.log10(10) # Logarithm with base 10 and argument 10  
math.exp(2) # e squared  
math.pow(10,2) # 10 squared  
```

## Remainder
This block calculates the **remainder** from the division of two numbers.

<img src="https://github.com/user-attachments/assets/d0af96ba-bf5e-4393-9d91-51f8ba8535b3" alt="Block Composer" /><br>

### Javascript Code
```javascript
64 % 10; // Remainder of 64 ÷ 10
```

### Python Code
```python
64 % 10 # Remainder of 64 ÷ 10
```

## Trigonometric Functions
This block calculates **trigonometric functions** such as sine, cosine, and tangent.


<img src="https://github.com/user-attachments/assets/4ee22488-23e7-4811-9085-6131f253293b" alt="Block Composer" /><br>

### Javascript Code
```javascript
Math.sin(45 / 180 * Math.PI); // sin 45° value  
Math.cos(45 / 180 * Math.PI); // cos 45° value  
Math.tan(45 / 180 * Math.PI); // tan 45° value  
Math.asin(45) / Math.PI * 180; // asin 45° value  
Math.acos(45) / Math.PI * 180; // acos 45° value  
Math.atan(45) / Math.PI * 180; // atan 45° value  
```

### Python Code
```python
import math  
math.sin(45 / 180.0 * math.pi) # sin 45° value  
math.cos(45 / 180.0 * math.pi) # cos 45° value  
math.tan(45 / 180.0 * math.pi) # tan 45° value  
math.asin(45) / math.pi * 180 # asin 45° value  
math.acos(45) / math.pi * 180 # acos 45° value  
math.atan(45) / math.pi * 180 # atan 45° value  
```

## round, round down, round up
This block returns a value by performing round, round down, or round up on the input number.

<img src="https://github.com/user-attachments/assets/75efb5bc-2917-4a4f-b29f-b9ec77cbfd17" alt="Block Composer" /><br>

### Javascript Code
```javascript
Math.round(3.1); // Rounded value of 3.1 is 3  
Math.ceil(3.1); // Rounded up value of 3.1 is 4  
Math.floor(3.1); // Rounded down value of 3.1 is 3  
```

### Python Code
```python
import math

round(3.1) # Rounded value of 3.1 is 3  
math.ceil(3.1) # Rounded up value of 3.1 is 4  
math.floor(3.1) # Rounded down value of 3.1 is 3  
```

## Special Numeric Values
This block provides special **mathematical constants** (such as π and e) and symbols required for calculations.

<img src="https://github.com/user-attachments/assets/5a94f61b-7429-4cd3-addc-657368442ab7" alt="Block Composer" /><br>

### Javascript Code
```javascript
Math.PI; // π (pi) value  
Math.E; // e (Euler’s number) value  
(1 + Math.sqrt(5)) / 2; // Golden ratio value  
Math.SQRT2; // Square root of 2  
Math.SQRT1_2; // Square root of 1/2  
Infinity; // Infinity  
```

### Python Code
```python
import math

math.pi # π (pi) value  
math.e # e (Euler’s number) value  
(1 + math.sqrt(5)) / 2 # Golden ratio value  
math.sqrt(2) # Square root of 2  
math.sqrt(1.0 / 2) # Square root of 1/2  
float('inf') # Infinity  
```

## Number Conditions
This block checks whether the input number satisfies specific conditions.  
It can determine whether a number is even, odd, prime, and more.  
If the condition is satisfied, it returns **true**; otherwise, it returns **false**.


<img src="https://github.com/user-attachments/assets/1f17454f-5c53-485a-9a28-88c38919c26d" alt="Block Composer" /><br>

### Javascript Code
```javascript
var item;

function mathIsPrime(n) { // Prime number check function
    if (n == 2 || n == 3) {
        return true;
    }
    if (isNaN(n) || n <= 1 || n % 1 !== 0 || n % 2 === 0 || n % 3 === 0) {
        return false;
    }
    for (var x = 6; x <= Math.sqrt(n) + 1; x += 6) {
        if (n % (x - 1) === 0 || n % (x + 1) === 0) {
            return false;
        }
    }
    return true;
}

item % 2 === 0; // Condition check: item is even  
item % 2 === 1; // Condition check: item is odd  
mathIsPrime(item); // Condition check: item is prime  
item % 1 === 0; // Condition check: item is an integer  
item > 0; // Condition check: item is positive  
item < 0; // Condition check: item is negative  
item % 0 === 0 // Condition check: item is divisible by 0  
```

### Python Code
```python
import math
from numbers import Number

item = None

def math_isPrime(n): # Prime number check function
    if not isinstance(n, Number):
        try:
            n = float(n)
        except:
            return False
    if n == 2 or n == 3:
        return True
    if n <= 1 or n % 1 != 0 or n % 2 == 0 or n % 3 == 0:
        return False
    for x in range(6, int(math.sqrt(n)) + 2, 6):
        if n % (x - 1) == 0 or n % (x + 1) == 0:
            return False
    return True

item % 2 == 0 # Condition check: item is even  
item % 2 == 1 # Condition check: item is odd  
math_isPrime(item) # Condition check: item is prime  
item % 1 == 0 # Condition check: item is an integer  
item > 0 # Condition check: item is positive  
item < 0 # Condition check: item is negative  
item % 0 == 0  # Condition check: item is divisible by 0  

```

The example below prints the message "`It is even.`" because `item` is even.

<img src="https://github.com/user-attachments/assets/331a8baf-1b4b-431e-b561-7f766cf42b27" alt="Block Composer" /><br>

### Javascript Code
```javascript
var item;

item = 2;
if (item % 2 === 0) {
    window.alert('It is even.');
} else {
    window.alert('It is odd.');
}
```

### Python Code
```python
item = None

item = 2
if item % 2 == 0:
    print('It is even.')
else:
    print('It is odd.')
```

## List Operations
This block performs various operations on a **list**.  
It can calculate the sum, minimum value, maximum value, average, median, mode, standard deviation, and select a random item.


<img src="https://github.com/user-attachments/assets/53638f76-e09f-47a6-9ddc-0d7a23cedce4" alt="Block Composer" /><br>

### Javascript Code
```javascript
function mathMean(myList) { // Mean calculation function
    return myList.reduce(function(x, y) {return x + y;}, 0) / myList.length;
}

function mathMedian(myList) { // Median calculation function
    var localList = myList.filter(function (x) {return typeof x === 'number';});
    if (!localList.length) return null;
    localList.sort(function(a, b) {return b - a;});
    if (localList.length % 2 === 0) {
        return (localList[localList.length / 2 - 1] + localList[localList.length / 2]) / 2;
    } else {
        return localList[(localList.length - 1) / 2];
    }
}

function mathModes(values) { // Mode calculation function
    var modes = [];
    var counts = [];
    var maxCount = 0;
    for (var i = 0; i < values.length; i++) {
        var value = values[i];
        var found = false;
        var thisCount;
        for (var j = 0; j < counts.length; j++) {
            if (counts[j][0] === value) {
                thisCount = ++counts[j][1];
                found = true;
                break;
            }
        }
        if (!found) {
            counts.push([value, 1]);
            thisCount = 1;
        }
        maxCount = Math.max(thisCount, maxCount);
    }
    for (var j = 0; j < counts.length; j++) {
        if (counts[j][1] === maxCount) {
            modes.push(counts[j][0]);
        }
    }
    return modes;
}

function mathStandardDeviation(numbers) { // Standard deviation calculation function
    var n = numbers.length;
    if (!n) return null;
    var mean = numbers.reduce(function(x, y) {return x + y;}) / n;
    var variance = 0;
    for (var j = 0; j < n; j++) {
        variance += Math.pow(numbers[j] - mean, 2);
    }
    variance /= n;
    return Math.sqrt(variance);
}

function mathRandomList(list) { // Random item selection function
    var x = Math.floor(Math.random() * list.length);
    return list[x];
}


[].reduce(function(x, y) {return x + y;}, 0); // List sum
Math.min.apply(null, []); // List minimum value
Math.max.apply(null, []); // List maximum value
mathMean([]); // List average value
mathMedian([]); // List median value
mathModes([]); // List mode value
mathStandardDeviation([]); // List standard deviation value
mathRandomList([]); // Random item from list

```

### Python Code
```python
from numbers import Number
import math
import random

item = None

def math_mean(myList): # Mean calculation function
    localList = [e for e in myList if isinstance(e, Number)]
    if not localList: return
    return float(sum(localList)) / len(localList)

def math_median(myList): # Median calculation function
    localList = sorted([e for e in myList if isinstance(e, Number)])
    if not localList: return
    if len(localList) % 2 == 0:
        return (localList[len(localList) // 2 - 1] + localList[len(localList) // 2]) / 2.0
    else:
        return localList[(len(localList) - 1) // 2]

def math_modes(some_list): # Mode calculation function
    modes = []
    counts = []
    maxCount = 1
    for item in some_list:
        found = False
        for count in counts:
            if count[0] == item:
                count[1] += 1
                maxCount = max(maxCount, count[1])
                found = True
        if not found:
            counts.append([item, 1])
    for counted_item, item_count in counts:
        if item_count == maxCount:
            modes.append(counted_item)
    return modes

def math_standard_deviation(numbers): # Standard deviation calculation function
    n = len(numbers)
    if n == 0: return
    mean = float(sum(numbers)) / n
    variance = sum((x - mean) ** 2 for x in numbers) / n
    return math.sqrt(variance)

sum([]) # List sum
min([]) # List minimum value
max([]) # List maximum value
math_mean([]) # List average value
math_median([]) # List median value
math_modes([]) # List mode value
math_standard_deviation([]) # List standard deviation value
random.choice([]) # Random item from list
```

The block below calculates the sum of the list [10, 20, 30], so 10 + 20 + 30 = 60.

<img src="https://github.com/user-attachments/assets/0352850f-fc79-4bef-9765-e4c2dff974cf" alt="Block Composer" /><br>

### Javascript Code
```javascript
[10, 20, 30].reduce(function(x, y) {return x + y;}, 0); // Result of the sum of [10, 20, 30] is 60
```

### Python Code
```python
sum([10, 20, 30]) # Result of the sum of [10, 20, 30] is 60
```

## Value Range Limiting
This block restricts the input value so that it does not exceed a specific range.
- If the value is smaller than the minimum, it is adjusted to the minimum.
- If the value is larger than the maximum, it is adjusted to the maximum.

<img src="https://github.com/user-attachments/assets/4641600d-abf1-442b-aebf-2be1132d030c" alt="Block Composer" /><br>

If the value of `item` is less than 1, it returns 1; if it is greater than 100, it returns 100.  
Values between 1 and 100 return the same value.

### Javascript Code
```javascript
var item;

Math.min(Math.max(item, 1), 100); // Clamp item to the range 1 ~ 100
```

### Python Code
```python
item = None

min(max(item, 1), 100) # Clamp item to the range 1 ~ 100
```

## Random Integer
This block generates a **random integer** within a specified range.

<img src="https://github.com/user-attachments/assets/e5abc2c4-c4d1-4b2e-be7e-4948e0535927" alt="Block Composer" /><br>

Generates an integer between 1 and 100 (inclusive).

### Javascript Code
```javascript
function mathRandomInt(a, b) { // Random integer generation function
    if (a > b) {
        var c = a;
        a = b;
        b = c;
    }
    return Math.floor(Math.random() * (b - a + 1) + a);
}

mathRandomInt(1, 100); // Generate a random integer between 1 and 100
```

### Python Code
```python
import random

random.randint(1, 100) # Generate a random integer between 1 and 100
```

## Random Fraction
This block generates a **random fractional value** between 0 and 1.

<img src="https://github.com/user-attachments/assets/7873933c-62b6-4e1f-9d9a-0985f23bb21b" alt="Block Composer" /><br>

### Javascript Code
```javascript
Math.random(); // Random fractional value
```

### Python Code
```python
import random

random.random() # Random fractional value
```

## Angle
This block calculates the angle formed by the given (x, y) coordinate with the origin (0, 0).  
It can be used to determine direction based on the position.

<img src="https://github.com/user-attachments/assets/6f047efb-30ba-4a44-a9cc-41213d899dfb" alt="Block Composer" /><br>

### Javascript Code
```javascript
Math.atan2(1, 1) / Math.PI * 180; // Calculated angle value
```

### Python Code
```python
import math

math.atan2(1, 1) / math.pi * 180 # Calculated angle value
```