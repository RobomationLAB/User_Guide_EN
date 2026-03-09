The **Editor** is an area where you can write code to control a robot using **blocks** or **script code**.  
Below, we introduce how to code in each environment—**Block Coding / Script Coding** (Python, JavaScript)—and the key points to keep in mind.

## Block Coding Editor

### Block Categories

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/block_category.png" alt="Block Composer" /><br> 

This area organizes the blocks provided by RobomationLAB into **categories**.  
When you click a category, you can view the **block palette** corresponding to that category.

The following are the default block categories provided:

- Logic
- Loops
- Math
- Text
- Lists
- Color
- Sound
- Control
- Variables
- Functions
- Others

In addition, when you add a [**Robot**](https://github.com/RobomationLAB/User_Guide_EN/wiki/Top-Menu#Rrobot) or an [**Extension Module**](https://github.com/RobomationLAB/User_Guide_EN/wiki/Top-Menu#extension) to the program,  
you can use dedicated block palettes for them within the program.

<br>

**⚙️ Note**

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/remove_robot.png" alt="Block Composer" /><br>

Among the blocks added to the program, any category that is no longer needed can be removed from the block categories by **Right-click → Remove**.

<br>

### Block Palette

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/block_palette.png" alt="Block Composer" /><br>

This area contains all the blocks for each category.  
Blocks in the block palette can be moved to the coding area using **Drag & Drop**.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/block_manual.png" alt="Block Composer" /><br>

**⚙️ Note**  
If you want to check how to use a block, you can open the help guide for each block by **Right-click → Help**.

<br>

### Coding Area

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/workspace.png" alt="Block Composer"  /><br>

This is the area where you can assemble blocks taken from the block palette.

The assembled blocks are converted into **Python/JavaScript code** in real time.  
When you run the code, it is interpreted to move and control the robot.

<br>

### Basic Block Structure

When coding in the Block Coding Editor, you must follow the basic structure below.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/default_block.png" alt="Block Composer" /><br>

In the Block Coding Editor, the program runs by interpreting the code inside the **function setup** and **function loop** blocks.  
Therefore, you must place blocks inside the **function setup** and **function loop** blocks to write your code.

**function setup**  
Inside the function setup block, define the actions to be performed initially when the code starts running.  
You can use the **wait** block to ensure actions are executed in sequence over time.

**function loop**  
Inside the function loop block, define the actions to be repeatedly executed while the code is running.  
The defined actions are executed repeatedly every 10 ms.

**⚠️ Caution**  
Inside the **function loop** block, you cannot use blocks that include the **wait** function.  
Using them incorrectly may cause errors in your code.

**⚙️ Note**  
(Except for custom functions created through the **Functions** category)  
Blocks placed outside the **function setup** or **function loop** blocks have no effect when the code is executed.

### How to Use Blocks

**Adding Blocks**

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/block_addition_1.png" alt="Block Composer" width="330" height="150" />
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/block_addition_2.png" alt="Block Composer" width="280" height="150" />
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/block_addition_3.png" alt="Block Composer" width="200" height="150" />
<br>

You can add a block by **dragging it from the block palette** and **dropping it into the editor**.  
<br>

**Copy / Paste Blocks**

After selecting a block, press **Ctrl + C** to **copy** the selected block.  
Press **Ctrl + V** to **paste** the most recently copied block into the editor.  
<br>

**Deleting Blocks**

There are three ways to delete blocks in the editor.

1. Select a block and press the **Backspace** key to delete the selected block.<br>

2. **Drag** the block you want to delete **from the editor** and **drop it into the block category** to remove it.  
<br>
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/block_remove_1.png" alt="Block Composer" width="300" height="150" />
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/block_remove_2.png" alt="Block Composer" width="300" height="150" />
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/block_remove_3.png" alt="Block Composer" width="300" height="150" />
<br>

3. You can delete a block by **dragging it from the editor** and **dropping it into the trash bin**.  
Deleted blocks can be reviewed again in the **trash bin**.<br>  
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/block-coding/trashbin.png" alt="Block Composer" /><br>
<br>

**Selecting Multiple Blocks at Once**

While holding down the **Shift** key, drag on the screen or click multiple blocks  
to select multiple blocks at once and move, copy, or delete them together.  
<br>

**Additional Options**

You can also **right-click** a block to access various additional options such as  
**Collapse / Expand Block, Enable / Disable, and Help**.

<br>

## Script Editor

### Code Collection


<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/code_palette.png" alt="Block Composer" /><br>

This area organizes the **basic functions** required for robot coding and the **script code** dedicated to robots and extension modules into **categories**.

The following are the code categories provided in the basic functions (Codes):

- logic
- loops
- math
- text
- lists
- color
- audio
- control

The code provided in the basic functions performs the same roles as the basic blocks in the Block Coding Editor.

<br>

**⚙️ Note**  
You can learn how to use the code collection in the Script Coding Editor in  [**How to Use the Code Collection**](#how-to-use-the-code-collection).

<br>

### Code Editor

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/code_editor.png" alt="Block Composer" /><br>

This is the area where you can write code to control the robot.

Depending on the editor(Python / JavaScript) selected in [**Editor Settings**](https://github.com/RobomationLAB/User_Guide_EN/wiki/Top-Menu#editor-settings),  
you can write code in your preferred programming language.

<br>

### Basic Code Structure

When coding in the Code Editor, you must follow the basic structure below.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/default_python.png" alt="Block Composer" /><br>
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/default_javascript.png" alt="Block Composer" /><br>

In the Code Editor, the program runs by interpreting the code inside the **setup** and **loop** functions.  
Therefore, you must write your code inside the **setup** and **loop** functions.

**setup**  

Inside the setup function, define the actions to be performed initially when the code starts running.  
You can use the **wait** function to ensure actions are executed in sequence over time.

**loop**  
Inside the loop function, define the actions to be repeatedly executed while the code is running.  
The defined actions are executed repeatedly every 10 ms.

**⚠️ Caution**  
Inside the **loop** function, you cannot use functions that require async/await functionality, such as the **wait** function.  
If used incorrectly, this may cause errors in your code.

<br>

### How to Use the Code Collection

Below, we explain **how to use the code collection in your coding** with a simple example.

### Finding the Code You Want

The code collection provides various functions and code needed for robot coding.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/code_palette_1.png" alt="Block Composer" /><br>

When you check the menus under the **Codes** category, you can find menus that have the <img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/main/assets/editor/script-coding/hide_submenu.svg"> icon.


When you click the **logic** menu once, the icon changes to <img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/main/assets/editor/script-coding/show_submenu.svg">, allowing you to expand and view the **submenus** inside.  
Menus that contain submenus in this way are called **categories**.


If a menu in the **logic** category, such as **ternary**, does not have the <img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/main/assets/editor/script-coding/hide_submenu.svg"> icon,  
it means that there are no more **submenus** within that menu.  
Menus that do not have submenus like this are called **codes**.


<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/code_palette_2.png" alt="Block Composer" /><br>

When you click a category with expanded submenus again, the icon changes back to <img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/main/assets/editor/script-coding/hide_submenu.svg"> and the submenus are hidden.


By following categories in this way, you can find the code you want in the code collection.

<br>

### Inserting Code into the Editor

The following explains how to insert code into the editor.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/code_palette_1.png" alt="Block Composer" /><br>

If a menu has the <img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/main/assets/editor/script-coding/code_option_x.svg" width="1%"> icon to the left of its name,  
it means that the menu does not have any selectable **code options**.  
Most menus that fall into this category are **category** menus that contain submenus.


If a menu has the <img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/main/assets/editor/script-coding/code_option_o.svg" width="1%"> icon to the left of its name, it means that the menu allows you to select **code options**.  
Most menus that fall into this category are **code** menus that do not have submenus.


If you **right-click** the code you want to insert into the editor,  
you can view the available options.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/code_palette_3.png" alt="Block Composer" /><br>

Codes in the **Basic Functions** category can have the following options  
(e.g., the **if** code in the **logic** category):

- **Insert Code**  
Inserts a predefined function or code into the editor.

<br>

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/code_palette_4.png" alt="Block Composer" /><br>

Codes in the **Robot Code** category can have the following options  
(e.g., the **wheel.speed.left** code in the **Hamster S** category):

- **Insert Code**  
Inserts a predefined function or code into the editor.  
This option is most commonly seen when inserting code from the **custom functions** (functions) category provided for each robot.

- **Get Value**  
Inserts code into the editor that allows you to check values such as the robot’s wheel speed, LED color (user-settable values), or sensor values.<br>
```python
# Left wheel speed value of Hamster S
__('HamsterS*0:wheel.speed.left').d
```

- **Set Value**  
Inserts code into the editor that is used when you need to write values to control the robot,  
such as setting the wheel speed or specifying a movement distance.<br>
```python
# Set the left wheel speed of Hamster S to 50
__('HamsterS*0:wheel.speed.left').d = 50
```

- **Wait**  
Inserts code into the editor that is used to control the robot’s actions in sequence over time,  
such as waiting until movement is completed after setting a movement distance.  
This option can usually be found in 'Event-type' codes that have a `!` at the beginning of their name.<br>
```python
# Hamster S moves 5 cm and waits until the movement is completed.
__('HamsterS*0:wheel.move').d = __getDistance('HamsterS', 5, 'cm')
await __('HamsterS*0:wheel.!move').w()
```

- **Check Event**  
Inserts code into the editor that allows you to check whether a specific event has occurred,  
such as whether the robot’s movement has been completed or whether a tap event has been detected.  
This option can usually be found in **Event-type** codes that have a `!` at the beginning of their name.<br>
```python
if __('HamsterS*0:wheel.!move').e == True:
    print("Event")
```

<br>

### Codes with Constant Values

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/main/assets/editor/script-coding/code_palette_constants.png" alt="Block Composer" /><br>

Among the code menus, there are menus that both **contain submenus and allow code insertion**, as shown below  
(e.g., the **playSound** code in the **audio** category).  
These codes are referred to as **codes with constant values**,  
and the codes in the submenus of these menus are called **constant values**.

For these codes,  
when you click the menu to expand the **submenus**, you can view the constant values that are predefined as input values.  
You can also **right-click** to select **code options** and insert the code into the editor.

<br>

**⚙️ Note**

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/editor/script-coding/remove_robot.png" alt="Block Composer" /><br>

Among the robot- or extension module–specific code added to the program,  
any code category that is no longer needed can be removed from the code collection by **Right-click → Remove**.
