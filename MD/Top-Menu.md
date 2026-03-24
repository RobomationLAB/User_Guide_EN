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
