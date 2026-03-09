# Components and Instructions

# Top-Menu

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/menu.png" alt="Block Composer"  /><br> 

**The RobomationLAB Top Menu** provides quick access to frequently used features such as connecting dongles and robots, saving and loading files, and running code.  
Below is a detailed explanation of each menu item in order.

## Logo
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/logo/BlockComposer.png" alt="Block Composer" /><br>


This is the RobomationLAB logo.  
Clicking the logo takes you to the RobomationLAB main homepage.

When the **Block Coding Editor** is active, the logo text is displayed as **Block Composer**.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/logo/ScriptComposer.png" alt="Block Composer" /><br>

When the **Python / JavaScript Editor** is active, the logo text is displayed as **Script Composer**.

<br>

## Dongle  

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/dongle/menu.png" alt="Block Composer" /><br>

You can **search for and connect a dongle used to communicate with robots and connect it to the program**.

To control a robot in the program, the dongle used to communicate with the robot must first be connected to the program.  
This process is called **pairing**.


<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/dongle/pairing.png" alt="Block Composer" /><br>

When you click the Dongle button, a list of dongles available on the current PC is displayed.

Select the desired dongle from the list and click the **Connect** button to connect the dongle to the program.

### Checking Dongle Connection Status

Once a dongle has been connected to the program, it will be automatically reconnected the next time the program is used.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/dongle/icon.png" alt="Block Composer" /><br>

When the dongle is successfully connected to the program, the icon changes to **light blue**.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/dongle/tab.png" alt="Block Composer" /><br>

If the browser tab displays an icon like the one shown below, you can confirm that the dongle is connected.

<br>

**⚠️ Notice**

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/dongle/failure.png" alt="Block Composer" /><br>

If the dongle is already connected to another program or another browser page, it cannot be connected to this program.  
In this case, disconnect the dongle from the other program or page, then return to this page and try connecting again.

<br>

## Robot

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/robot/menu.png" alt="Block Composer" /><br>

You can **select the robot to use** and register the robot’s **information and dedicated blocks/scripts** in the program.

To control a robot in the program, the robot’s information and blocks must first be added to the program.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/robot/popup.png" alt="Block Composer" /><br>

When you click the **Robot Selection** button, a popup window displays a list of robots available in the program.

- Hamster S  
- Hamster  
- PiBot  
- Turtle  
- Beagle  
- RaccoonBot  

After selecting the desired robot, click the **Add** button to register the robot’s information and its dedicated blocks/scripts in the program.


<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/robot/block.png" alt="Block Composer" width="37%" />
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/robot/script.png" alt="Block Composer" /><br>

When a robot is added, the following items are created:

- **Block Composer**: Dedicated **blocks** for the selected robot are added to the left **Block Palette**
- **Script Composer**: Dedicated **script code** for the selected robot is added to the left **Code List**

This allows you to freely control real robot hardware such as sensors, motors, and LEDs.

<br>

**⚙️ Reference**

In RobomationLAB, you can connect and use as many robots as you want, regardless of the robot type or quantity.

However, if you want to connect and use multiple robots simultaneously:
- The same number of dongles as the number of robots must be connected to the program
- The same number of robots must be added to the program

<br>

## Extension

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/extension/menu.png" alt="Block Composer" /><br>

Extension modules provide **AI-based extended features** such as voice recognition, computer vision, and image analysis.  
You can **select the extension modules to use** and register the selected modules’ **information and dedicated blocks/scripts** in the program.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/extension/screen.png" alt="Block Composer" /><br>

When you click the **Extension** button, a popup window appears showing the list of extension modules available in the program.

- Speech to Text  
- Face Detection  
- Detailed Face Detection  
- Face Expression  
- Hand Detection  
- Body Detection  
- Object Detection  
- Color Detection  

When you click a module, the module’s information and its dedicated blocks/scripts are registered in the program, just like in [**Robot**](#robot).

When you add camera-based extension modules such as **Face Detection** or **Hand Detection**,  
a camera module is created in the [**Preview – Camera**](https://github.com/RobomationLAB/User_Guide_EN/wiki/Preview#camera) tab, allowing you to connect and use a camera in the program.

If an extension module is no longer needed, you can remove it from the list by **right-clicking → Remove**.

<br>

## File

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/file/menu.png" alt="Block Composer" /><br>

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/file/dropdown.png" alt="Block Composer" /><br>

You can manage files such as creating new code, saving your work, and opening existing files.

- **New**: Clears the code in the active editor and creates a new file.
- **Save**: Saves the current code file. The file is saved in the user’s **Downloads** folder with the `.block` file extension.
- **Save As**: Saves the code file under a new name. The file is saved in the user’s **Downloads** folder with the `.block` file extension.
- **Open**: Opens a `.block` file from the user’s computer.
- **Reset**: Resets all data registered in the program, including robot information, blocks/scripts, and settings. (robot information, blocks/scripts, settings, etc.).

<br>

## Edit

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/edit/menu.png" alt="Block Composer" /><br>

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/edit/dropdown.png" alt="Block Composer"  /><br>

This menu allows you to undo or redo actions.

- **Undo (Ctrl+Z)**: Cancels the most recent action.
- **Redo (Ctrl+Y)**: Reapplies the action that was undone.

<br>

## Sound

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/sound/menu.png" alt="Block Composer" /><br>

You can select sounds to use in coding or add your own offline sound files to the program.

### Selecting Sounds

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/sound/screen.png" alt="Block Composer" /><br>

When you click the **Sound** button, a screen appears where you can choose from various sounds provided by the program.  
You can use the following features:

- Search sounds
- ▶ Preview sounds
- Add sounds to the sound list (left panel)

### Extended Features

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/sound/extension.png" alt="Block Composer" /><br>

When you click the **Extension** button (red box) at the bottom-left, or hover over it, three extended feature options appear.  
You can use the following features:

- **Add Local File**: Add an audio file from the user’s computer  
- **Record Sound**: Record and add your own sound  
- **Add Random Sound**: Add a randomly selected sound from the entire sound list

### Using Sounds in Coding
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/sound/list.png" alt="Block Composer" /><br>

Sounds added to the sound list (left panel) can be used in coding.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/sound/block.png" alt="Block Composer" /><br>

In **Block Coding**, you can select a desired sound from the dropdown menu of the **Play Sound** block.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/sound/script.png" alt="Block Composer" /><br>

In **Script Coding**, you can select a desired sound from the sub-options of the **playSound** function in the **Codes – audio** category.

When the code is executed, the selected sound is played through the user’s computer speakers.

<br>

## Example

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/example/menu.png" alt="Block Composer" /><br>

When a robot is added to the program, you can load and try simple examples for each robot.

### Selecting an Example

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/example/screen.png" alt="Block Composer" /><br>

When you click the **Examples** button, the **Select Example** screen appears as shown above.  
You can quickly find the desired example using the **category filter** and **search** functions.

### Loading an Example
1. Click the **Examples** menu to open the **Select Example** screen, and choose the desired example.  
2. The screen refreshes and the example appears in the coding area.  
3. After loading the example, click the **Run (▶)** button to check how it works without any additional setup.

<br>

## Run / Stop Code

### Run (▶)
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/code-run/run.png" alt="Block Composer" /><br>

Interprets and executes the block code or script code written in the currently active editor.

Based on the written code, you can control the robots connected to the program.  
While the code is running, the code being written cannot be modified.

### Stop (■)
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/code-run/stop.png" alt="Block Composer" /><br>

Stops code execution.

<br>

## Editor Settings
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/editor/menu.png" alt="Block Composer" /><br> 

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/editor/dropdown.png" alt="Block Composer" /><br>

You can choose one of the **Block Coding, Python, or JavaScript** editors to write your code.

Even if you switch editors, any previously written code is preserved, allowing you to continue coding at any time.

**※ Each editor operates independently.**

### Block Coding Editor
When Block Coding is selected, the logo changes to **Block Composer**.  
In the Block Coding Editor, you can view real-time conversion of the block code into Python and JavaScript through the **Preview – Code** tab.  
However, these converted codes are **not automatically applied** to the **Python** or **JavaScript** editors.

### Python / JavaScript Editor
When Python or JavaScript is selected, the logo changes to **Script Composer**.  
As with the Block Coding Editor, code written in the **Python** or **JavaScript** editor is not automatically reflected in the **Block Coding Editor** and is managed separately.

<br>

## AI Coding
<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/ai-coding/menu.png" alt="Block Composer" /><br> 

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/ai-coding/dropdown.png" alt="Block Composer" /><br>

You can create your own **AI coding assistant** using **Gem**, an AI assistant powered by **Google Gemini**, and write code together with AI.

### Vibe Coding

**Vibe Coding** is a new development approach that allows you to turn ideas or desired features into code using AI, even without advanced programming knowledge.  
Through **collaboration with AI**, you can learn coding more easily.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/ai-coding/vibe-coding.png" alt="Block Composer" /><br> 

### Code Review

In **Code Review**, you can receive reviews and evaluations of your code from the AI coding assistant.  
Even when errors occur during code execution, you can ask the AI for the cause of the error and how to fix it to quickly resolve the issue.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/ai-coding/code-review.png" alt="Block Composer" /><br> 

### AI Coding – Getting Started Guide

This is a guide page for users who are new to the AI Coding feature.  
It provides step-by-step instructions on **how to create and use an AI coding assistant**, as well as **how to utilize Vibe Coding and Code Review**.

<br>

## Code Copy

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/code-copy/menu.png" alt="Block Composer" /><br> 

You can copy the code written in the currently active editor to the clipboard.

### Block Composer (Block Coding)

The copied result depends on the language selected in the **[Preview – Code](https://github.com/RobomationLAB/User_Guide_EN/wiki/Preview#code)** tab.
- Python selected → Python code is copied  
- JavaScript selected → JavaScript code is copied  

### Script Composer (Python / JavaScript)

The code written in the editor is copied as-is.

You can paste the copied code wherever you want using **Ctrl+V**.

<br>

## Settings

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/settings/menu.png" alt="Block Composer" /><br> 

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/settings/dropdown.png" alt="Block Composer" /><br> 

You can configure the basic settings of the program.

### Language
Changes the display language of the program.  
The available languages are Korean and English.

### Dongle
- **Disconnect**: Disconnects all dongles currently connected to the program.
- **Reconnect**: Reconnects the dongles to the program.

<br>

## Help

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/help/menu.png" alt="Block Composer" /><br> 

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/top-menu/help/dropdown.png" alt="Block Composer" /><br> 

You can access guides and external resources needed to use the program.

- **Tutorial**: Provides tutorials for users who are new to the program.
- **User Guide**: Provides detailed explanations of each component of the program, how to use them, and the functions and syntax of each block/script code provided by RobomationLAB.
- **RobomationLAB**: Takes you to the RobomationLAB main page.
- **Homepage**: Takes you to the official Robomation company website.
- **YouTube**: Takes you to the Robomation YouTube channel.
- **Shop**: Takes you to the Robomation online store.
- **Info**: Allows you to check the program version, update history, terms of use, and privacy policy.
- **Contact**: Allows you to submit inquiries about questions or bugs encountered while using the program.


# Editor

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


# Preview

**Preview** is an area that helps with robot coding by allowing you to check the **robot connection status** and by providing tools such as the code console and camera console.  
Below, the functions available in each tab are described.

## Robot Connection Status Tab

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/connections/sensor.png" alt="Block Composer" width="70%" /><br> 

In the Robot Connection Status tab, you can check information about the robots that are currently connected.  
By clicking **Hide Real-Time Sensor Values**, you can monitor the robot’s sensor data in real time, displayed as graphs or numerical values.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/connections/screen.png" alt="Block Composer" width="70%" /><br>

1. You can select which sensor to view, and the types of sensors supported vary by robot.  
   Depending on the selected sensor, the graph and data display format automatically adjust to match that sensor’s values.
2. You can choose the time interval (in seconds) at which sensor values are checked or recorded.  
   Based on the selected interval, the maximum duration for which data can be recorded and displayed on the graph will vary.
3. When you place the mouse cursor over the sensor graph, you can view the sensor value at that specific point in time in real time.
4. Start / Stop Recording: Records sensor data.
5. Export: Saves the recorded sensor data as a `.csv` file and the graph view as a `.png` file.  
   This feature is only available after data has been recorded.
6. Capture: Saves the current graph view as a `.png` file in real time.  
   You can record changes in sensor values and save both the recorded data files and the graph images as files.

<br>

## Code Tab

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/code/screen.png" alt="Block Composer" width="70%" /><br>

In the Code tab, you can see how adding or removing blocks is reflected in **Python** and **JavaScript** code in real time.  
By observing how blocks are converted into code, you can more easily learn and understand coding syntax.

※ The Code tab is available **only in the Block Coding Editor**.  
In the Python / JavaScript editors, users write code directly, so a separate Code tab is not provided.

<br>

## Camera Tab

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/camera/select.png" alt="Block Composer" width="70%" /><br>

In the Camera tab, you can view the live video feed from a camera connected to your PC in real time.

This feature is enabled **only when a camera-based extension module is added to the program**, and a corresponding camera module will appear in the Camera tab.  
Each camera module provides the following functions:

- Select one of the cameras available on the current PC and display its video feed.
- Use the **On / Off** button to show or stop the camera view.

<br>

## Console Tab

In the Console tab, you can monitor log messages (Log) and scope graphs (Scope) in real time while the program is running.  
This tab is useful for debugging, sensor value monitoring, and graph-based analysis.

### Log
By using the **Log Output** block, you can print text or numeric values to the console log area together with a specified tag.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/console/log_block.png" alt="Block Composer" width="30%" /><br>

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/console/log.png" alt="Block Composer" width="70%" /><br>

### Scope

By using the **Scope Output** block, you can visualize numeric values as **real-time graphs** for each tag.  
You can configure the minimum value, maximum value, and graph color to visually monitor changes in the desired data.

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/console/scope_block.png" alt="Block Composer" width="40%" /><br>

<img src="https://raw.githubusercontent.com/RobomationLAB/User_Guide_EN/master/assets/preview/console/scope.png" alt="Block Composer" width="70%" /><br>


