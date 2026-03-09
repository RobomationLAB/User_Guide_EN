This document explains the coding rules that must be followed when programming robots in RobomationLAB.

<br>

### 1. Basic Block Code Structure
Whenever block code is presented, it must always include the top-level function blocks that serve as the program’s core top-level structure: Start and Repeat Forever, as the basic structure.  
By applying this rule, all block code will follow the basic structure shown below.

| Block Structure (Block Composer) | Presentation Method (Text Format) |
| --- | --- |
| Start | Start |
| (Inner blocks) | (Inner blocks) |
| Repeat Forever | Repeat Forever |
| (Inner blocks) | (Inner blocks) |

<br>

### 2. Block Code Format (Line Break and Indentation Rules)
- Top-level blocks (such as Start, Repeat Forever, etc.) must be left-aligned.
- Each command block must be separated using a line break, and only one block should be displayed per line.
- For blocks that contain an internal execution area (such as if, loop blocks, function definitions, etc.), child blocks inside them must be indented to clearly represent the hierarchical structure.

<br>

### 3. Rules for Inner Blocks and Condition Representation
The selected values from dropdown menus or user input values correspond to the functional arguments of a block.  
These values must be inserted directly into the block text using square brackets `[]` at the position where the value appears.

This serves to visually integrate the block’s fixed wording with the values selected or entered by the user.

All block code must include the block’s original name, dropdown selection values, and user-entered values, all expressed using square brackets `[]`.  
The block code should be presented in a way that reproduces the actual appearance of Block Composer blocks in text form as closely as possible.

| Block Structure (Block Composer) | Presentation Method (Text Format) |
| --- | --- |
| If [condition] then [command] else [command] | If [condition] then [command] else [command] |
| RaccoonBot: set to [speed] control mode | RaccoonBot: set to [speed] control mode |
| RaccoonBot: set joint [1] speed to [100] | RaccoonBot: set joint [1] speed to [100] |

<br>

### 4. Basic Script Code Structure
Whenever script code (Python / JavaScript) is presented, the functions setup() and loop(), which serve as the program’s entry points, must always be included as the basic structure.  
By applying this rule, all future script code (Python / JavaScript) will follow the basic structure shown below.

```javascript
// JavaScript basic code structure
async function setup() {
    // inner code
}

function loop() {
    // inner code
}
```

```python
# Python basic code structure
import asyncio

async def setup():
    # inner code
    return

def loop():
    # inner code
    return
```

<br>

### 5. Script Code Format (Line Break and Indentation Rules)
- Top-level functions (such as setup, loop, etc.) must be left-aligned.
- Indentation created by line breaks (`\t`) must always be based on three spaces.

<br>

### 6. Rules for Presenting Block Code and Script Code
Only the functions and objects specified in the provided documents (such as “Coding Guide”, “Basic Blocks”, “HamsterS”, etc.) may be created and used.  
When controlling robots, creating or using new robot control functions or custom functions that are not defined in the documents is strictly prohibited.

However, if a user explicitly requests the creation of a function, it may be created under the following rules:
1) Function names must be written in English.  
2) Any function that performs asynchronous operations must include the `async` keyword before the function name when it is defined.

The declaration of Declaring variables such as `const`, `let`, or `var` is strictly prohibited unless explicitly shown in the document’s conversion examples specified in the documents is strictly prohibited, and variables may only be created when explicitly requested by the user.  
In addition, robot IDs and parameter values must always be written as literals.

```javascript
// Correct example
__getSpeed('HamsterS*0', 100)

// Incorrect example
const ROBOT_ID = 'HamsterS*0'; 
__getSpeed(ROBOT_ID, 100)
```

<br>

### 7. Rules for Calling Robot Device Objects
When calling robot Device objects in script code (Python / JavaScript), the following rules must be followed.

Python Device objects:  
You must use **two underscores (`__`)** and write them in the format `__('{Device object urn}')`.
```python
__('HamsterS*0:wheel.speed.left').d = 50
```

JavaScript Device objects:  
You must use the dollar sign (`$`) and write them in the format `$('{Device object urn}')`.

```javascript
$('HamsterS*0:wheel.speed.left').d = 50;
```

Prohibited usage:  
Do not use `_('...')` (single underscore) notation, and do not use `$$('...')` (double dollar signs) in JavaScript.

<br>

### 8. Rules for Calling Custom / Utility Functions
When calling custom or utility functions in script code, the following common rules apply regardless of whether you are using Python or JavaScript.

- Function names must always start with `__` (double underscore).
- Creating or calling any function whose name starts with `_` (single underscore) is strictly prohibited.

```javascript
// Correct example
__getSpeed('HamsterS', 50)

// Incorrect example
_getSpeed('HamsterS', 50)
```

<br>

### 9. Priority Rules for Robot-Specific Blocks and Code
When controlling robot hardware (such as wheel speed, LEDs, sound, etc.),  
you must prioritize using Device objects and functions defined in the robot-specific documentation (e.g., *“HamsterS”*) over utility functions defined in the “Basic-Block” document.

For example, when playing sound using a robot,  
you should use the `sound.clip` Device object specified in the *“HamsterS”* documentation instead of the utility function `__playSound()`.

### 10. Mandatory Prerequisite for Robot Movement Control
When writing any code that sets or changes the wheel speed of a robot  
(Hamster S, Hamster, Pio, Turtle, Beagle), it is mandatory to reset the state of the `wheel.move` object immediately before executing the speed-setting command.

Before controlling continuous movement speed using `wheel.speed`,  
any remaining values from other movement commands (`wheel.move`) must be reset to `0`.  
This ensures that the new speed setting is applied accurately without interference.

| Programming Language | Required Initialization Logic Before Setting Wheel Speed |
| --- | --- |
| Python | if __('{Device}:wheel.move').d != 0:<br>&nbsp;&nbsp; __('{Device}:wheel.move').d = 0 |
| JavaScript | if(\$('{Device}:wheel.move').d != 0) {<br>&nbsp;&nbsp; \$('{Device}:wheel.move').d = 0;<br>} |

### 11. Import Minimization Rule

When writing Python code, only modules that are essential for code execution must be imported.  
- Any code that uses the `await` keyword must include only `import asyncio` as a default import.

When writing JavaScript code, no import statements are allowed at all.