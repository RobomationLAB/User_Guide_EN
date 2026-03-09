A **list** is a **collection of items arranged in order**, like a “to-do list” or a “shopping list.”  
Items in a list can be of any data type, and the same value can appear multiple times in a list.

<br>

# Creating Lists

## Creating an Empty List
The simplest list is an empty list, which is created using the **create empty list** block:

<img src="https://github.com/user-attachments/assets/76f7ae3e-e87a-4516-aa9b-b9ecc3c69dbf" alt="Block Composer" /><br> 

### JavaScript Code
```javascript
[]; // empty list
```

### Python Code
```python
[]  # empty list
```

## Creating a List

### Basic Usage
Using the **Create List** block, you can specify initial values for a new list.  
For example, you can create a list of words and store it in a variable named **letters**:

<img src="https://github.com/user-attachments/assets/120c93e8-bf40-4534-92de-248b1c66bd55" alt="Block Composer"  /><br>

In this document, this list is represented as `["one", "two", "three"]`.  
The variables defined in this block will be used in later examples.

### JavaScript Code
```javascript
var letters;

letters = ['one', 'two', 'three'];
```

### Python Code
```python
letters = None

letters = ['one', 'two', 'three']
```

The following is an example of creating a list of numeric texts:

<img src="https://github.com/user-attachments/assets/1f19e319-b574-4e7a-a716-094687fc3ba9" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var numbers;

numbers = ['1', '2', '3'];
```

### Python Code
```python
numbers = None

numbers = ['1', '2', '3']
```

The following is an example of creating a color list:

<img src="https://github.com/user-attachments/assets/cac86dd8-4502-4104-88ea-6b5aae5e35a3" alt="Block Composer"  /><br>

### JavaScript Code
```javascript
color = [[255, 0, 0], [0, 0, 255], [0, 255, 0], [255, 255, 0]];
```

### Python Code
```python
color = [[255, 0, 0], [0, 0, 255], [0, 255, 0], [255, 255, 0]]
```

Although less common, you can also create a list that contains values of different types:

<img src="https://github.com/user-attachments/assets/1cf0e576-7bff-4c5e-a39d-d1936c6a437b" alt="Block Composer" /><br>

### JavaScript Code
```javascript
['one', 1, [255, 0, 0]];
```

### Python Code
```python
['one', 1, [255, 0, 0]]
```

### Changing the Number of Input Items
To change the number of input items, click the gear icon.  
A new window will open, where you can drag the **Item** sub-block on the left into the **List** block on the right to add a new input.

<img src="https://github.com/user-attachments/assets/e3b279c2-e2d6-4173-ba50-27d71fbc1924" alt="Block Composer"  /><br>

New items can be added at any desired position. Likewise, you can remove unwanted **Item** sub-blocks by dragging them back to the left.

## Create List with Repeated Item
The **Create List with Repeated Itemm** block allows you to create a list by repeating a specified item a given number of times.  
For example, the block below sets the variable **words** to `["very", "very", "very"]`.

<img src="https://github.com/user-attachments/assets/1e5c0671-306f-431f-a03b-f5dda8bae668" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var words;

function listsRepeat(value, n) { // Function to create a list by repeating the same value
    var array = [];
    for (var i = 0; i < n; i++) {
        array[i] = value;
    }
    return array;
}

words = listsRepeat('very', 3); // words = ['very', 'very', 'very']
```

### Python Code
```python
words = None
words = ['very'] * 3 # words = ['very', 'very', 'very']
```

# List Length

## Is Empty  
The value of the **Is Empty** block is **true** if the input is an empty list, and **false** otherwise (this also applies if the input is not a list).  

In the example below, the value of the block becomes **false** because the **color** variable is not empty and contains three items.

<img src="https://github.com/user-attachments/assets/48d12f05-223e-4fc2-bb58-62672514513c" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var color;

color = [[255, 0, 0], [0, 0, 255], [0, 255, 0]];
!color.length; // Outputs false because it is not empty
```

### Python Code
```python
color = None

color = [[255, 0, 0], [0, 0, 255], [0, 255, 0]]
not len(color)  # Outputs False because it is not empty
```

This is similar to the [“Is Empty” block](https://github.com/RobomationLAB/User_Guide_EN/wiki/문자열#빈-문자열-확인) in Text category.  

## Length
The value of the **Length** block is the number of items in the list.  
For example, in the block below, **color** contains 3 items, so it returns 3.

<img src="https://github.com/user-attachments/assets/9e0fe6db-8aea-4004-9e6d-69e24cbc096c" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var color;

color = [[255, 0, 0], [0, 0, 255], [0, 255, 0]];
color.length; // Returns 3 because the list contains three items
```

### Python Code
```python
color = None

color = [[255, 0, 0], [0, 0, 255], [0, 255, 0]]
len(color)  # Returns 3 because the list contains three items
```

The **Length** block tells you how many items are in a list.  
It counts the number of elements in the list itself, not how many different values it contains.  
For example, the **words** list below contains the text "very" repeated three times (["very", "very", "very"]).  
In this case, the block returns 3.

<img src="https://github.com/user-attachments/assets/bafc03b1-bba6-43e4-b1ad-31df377fe4eb" alt="Block Composer"  /><br>

This is similar to the [“Text Length” block](https://github.com/RobomationLAB/User_Guide_EN/wiki/문자열#문자열-길이) in Text category.  

### JavaScript Code
```javascript
var words;

function listsRepeat(value, n) { // Function to create a list by repeating the same value
    var array = [];
    for (var i = 0; i < n; i++) {
        array[i] = value;
    }
    return array;
}

words = listsRepeat('very', 3);
words.length; // Returns 3 because there are 3 items
```

### Python Code
```python
words = None

words = ['very'] * 3
len(words)  # Returns 3 because there are 3 items
``` 


# Item Position in a List  
These blocks find the position of an item within a list.  
For example, the value of the block below is 1 because the first occurrence of the item "very" appears at the first position in the **words** list (["very", "very", "very"]).

<img src="https://github.com/user-attachments/assets/d988cf67-f681-4e7d-8609-4504bc32d64c" alt="Block Composer" /><br>

The following result is 3 because the item "very" appears at the last position in the **words** list.

<img src="https://github.com/user-attachments/assets/023dba58-8290-4db1-b427-e3daeafd94ca" alt="Block Composer" /><br>

If the item does not exist in the list, the result is 0.

<img src="https://github.com/user-attachments/assets/0089373b-1157-42bc-b32f-f429c371fb0c" alt="Block Composer" /><br>

These blocks are similar to the [“Find Text” block](https://github.com/RobomationLAB/User_Guide_EN/wiki/문자열#문자열-찾기) in Text category.  

### JavaScript Code
```javascript
var words;

function listsRepeat(value, n) { // Function to repeat the same value in a list
    var array = [];
    for (var i = 0; i < n; i++) {
        array[i] = value;
    }
    return array;
}

words = listsRepeat('very', 3);
words.indexOf('very') + 1      // Returns 1: the first position where "very" appears
words.lastIndexOf('very') + 1 // Returns 3: the last position where "very" appears
words.indexOf('unicorn') + 1  // Returns 0: "unicorn" does not appear in the list
```

### Python Code
```python
words = None

def first_index(my_list, elem):  # Function to find the first occurrence
    try:
        index = my_list.index(elem) + 1
    except:
        index = 0
    return index

def last_index(my_list, elem):  # Function to find the last occurrence
    try:
        index = len(my_list) - my_list[::-1].index(elem)
    except:
        index = 0
    return index

words = ['very'] * 3
first_index(words, 'very')    # Returns 1: the first position where "very" appears
last_index(words, 'very')     # Returns 3: the last position where "very" appears
first_index(words, 'unicorn') # Returns 0: "unicorn" does not appear in the list
```

# Get Items from a List

## Get a Single Item

Remember the definition of the **color** list:

<img src="https://github.com/user-attachments/assets/cac86dd8-4502-4104-88ea-6b5aae5e35a3" alt="Block Composer" /><br>

The following block retrieves the color `blue`.  
This is because `blue` is the second item in the list (counting from the left):

<img src="https://github.com/user-attachments/assets/5c4c8507-6da8-4814-a4ea-874aa536d913" alt="Block Composer" /><br>

The next block retrieves `green`.  
This is because `green` is the second item from the right end of the list:

<img src="https://github.com/user-attachments/assets/6eafaf18-d924-41d8-9ee8-64370ec3e4a2" alt="Block Composer"  /><br>

This block retrieves the first item, `red`:

<img src="https://github.com/user-attachments/assets/dade032c-a3c1-4927-a84c-a41b06adb253" alt="Block Composer" /><br>

This block retrieves the last item, `yellow`:

<img src="https://github.com/user-attachments/assets/737a1d50-3aae-40e3-81cd-692f2b49cb24" alt="Block Composer" /><br>

This block selects one item from the list at random.  
It chooses one of `red`, `blue`, `green`, or `yellow` with equal probability.

<img src="https://github.com/user-attachments/assets/48006fb3-cd5c-481e-b52a-33366b721556" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var color;

function listsGetRandomItem(list, remove) { // Function to select a random item from a list
    var x = Math.floor(Math.random() * list.length);
    if (remove) {
        return list.splice(x, 1)[0];
    } else {
        return list[x];
    }
}

color = [[255, 0, 0], [0, 0, 255], [0, 255, 0], [255, 255, 0]];
color[1]; // Get the second item (blue) from color
color.slice(-2)[0]; // Get the second item from the end (green) from color
color[0]; // Get the first item (red) from color
color.slice(-1)[0]; // Get the last item (yellow) from color
listsGetRandomItem(color, false); // Get a random item from color
```

### Python Code
```python
import random

color = None

color = [[255, 0, 0], [0, 0, 255], [0, 255, 0], [255, 255, 0]]
color[1]        # Get the second item (blue) from color
color[-2]       # Get the second item from the end (green) from color
color[0]        # Get the first item (red) from color
color[-1]       # Get the last item (yellow) from color
random.choice(color)  # Get a random item from color
```

### Get and Remove Item
When you select an option from the dropdown menu in the **Get item from list** block, it changes to **Get and remove item from list**,  
which not only retrieves the item but also modifies the original list by removing that item.

<img src="https://github.com/user-attachments/assets/8b135116-8814-4581-8834-97502df0769a" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var list;

function listsGetRandomItem(list, remove) { // Function to get a random item from a list
   var x = Math.floor(Math.random() * list.length);
   if (remove) {
      return list.splice(x, 1)[0];
   } else {
      return list[x];
   }
}

list[0]; // Get the first item from the list
list.slice(-1)[0]; // Get the last item from the list
listsGetRandomItem(list, false); // Get a random item from the list
list.splice(0, 1)[0]; // Remove and return the first item from the list
list.shift(); // Remove the first item from the list (returns the removed item)
list.pop(); // Remove and return the last item from the list
listsGetRandomItem(list, true); // Remove and return a random item from the list
```

### Python Code
```python
list2 = None  # Use list2 to avoid shadowing Python’s built-in type name list.

def lists_remove_random_item(myList):  # Function to remove a random item from the list
    x = int(random.random() * len(myList))
    return myList.pop(x)

list2[0]        # Get the first item in the list
list2[-1]       # Get the last item in the list
random.choice(list2)  # Get a random item from the list
list2.pop(0)    # Remove the first item from the list
list2.pop(0)    # Remove an item from the front of the list (returns the first item)
list2.pop()     # Remove the last item from the list
lists_remove_random_item(list2)  # Remove a random item from the list
```

This example assigns ["one"] to the variable **first_letter**, and leaves **letters** as ["two", "three"].

<img src="https://github.com/user-attachments/assets/48bff36f-69ea-4439-a762-b8d92c37d80f" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var letters, first_letter;

letters = ['one', 'two', 'three'];
first_letter = letters.splice(0, 1)[0]; 
// Remove the first item from the letters list
// first_letter = ["one"], letters = ["two", "three"]
```

### Python Code
```python
letters = None
first_letter = None

letters = ['one', 'two', 'three']
first_letter = letters.pop(0)
# Remove the first item from the letters list
# first_letter = ["one"], letters = ["two", "three"]
```

### Remove Item
When you select "delete" from the dropdown menu, the plug on the left side of the block disappears:

<img src="https://github.com/user-attachments/assets/6a74dee7-25b5-41cf-8ad0-a2ef53c8a3b0" alt="Block Composer" /><br>

This removes the first item from **letters**.

### JavaScript Code
```javascript
var letters;

letters = ['one', 'two', 'three'];
letters.splice(0, 1); // Remove the first item from the letters list, letters = ['two', 'three']
```

### Python Code
```python
letters = None

letters = ['one', 'two', 'three']
letters.pop(0)  # Remove the first item from the letters list, letters = ['two', 'three']
```

## Extracting a Sublist  
The **extract sublist from list** block is similar to the **get item from list** block,  
but instead of extracting a single item, it extracts a sublist.  

There are several ways to specify the start and end positions of the sublist:

<img src="https://github.com/user-attachments/assets/6dc03c2c-1cd6-4fea-a2cb-84f9c6f15dfa" alt="Block Composer"  /><br>

<img src="https://github.com/user-attachments/assets/09ce9d85-45d3-4824-b2e7-828af9c058e9" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var list;

list.slice(0, 1); // Extract a sublist from the first position to the first item
list.slice(0, list.length - 0); // Extract a sublist from the first position to the last item
list.slice(0, list.length); // Extract a sublist from the first position to the last item
list.slice(list.length - 1, 1); // Extract a sublist from the last position to the last item
list.slice(list.length - 1, list.length - 0); // Extract a sublist from the last position to the last item
list.slice(list.length - 1, list.length); // Extract a sublist from the last position to the last item
list.slice(0, 1); // Extract a sublist from the first position to the first item
list.slice(0, list.length - 0); // Extract a sublist from the first position to the end
list.slice(0); // Extract a sublist from the first position to the last item
```

### Python Code
```python
list2 = None  # Use list2 because 'list' is a reserved word

list2[:1]    # Extract a sublist from the first position to the first item
list2[:]     # Extract a sublist from the first position to the end
list2[:]     # Extract a sublist from the first position to the last item
list2[-1:1]  # Extract a sublist from the last position to the end
list2[-1:]   # Extract a sublist from the last position to the end
list2[-1:]   # Extract a sublist from the last position to the last item
list2[:1]    # Extract a sublist from the first position to the first item
list2[:]     # Extract a sublist from the first position to the end
list2[:]     # Extract a sublist from the first position to the last item
```

In this example, a new list called **first letters** is created.  
This list contains two items: ["one", "two"].

<img src="https://github.com/user-attachments/assets/c4e453ae-4c01-476c-adba-d3db5677412c" alt="Block Composer" /><br>

This block does not modify the original list.

### JavaScript Code
```javascript
var letters, first_letter, list;

letters = ['one', 'two', 'three'];
first_letter = list.slice(0, 2); // Extract from the first position to the second item → first_letter = ["one", "two"]
```

### Python Code
```python
letters = None
first_letter = None
list2 = None  # list is a reserved word in Python, so list2 is used

letters = ['one', 'two', 'three']
first_letter = letters[:2]  # Extract from the first position to the second item → first_letter = ["one", "two"]
```  

# Adding Items to a List
  
## Set item in list  
The **Set item in list** block replaces the item at a specified position in a list with another item.

<img src="https://github.com/user-attachments/assets/30c48ac7-6b48-4d1a-89b4-718748962c79" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var letters, list;

list[0] = 'hello'; // Set "hello" at the first position in the list
list[list.length - 1] = 'hello'; // Set "hello" at the last position in the list
list[0] = 'hello'; // Set "hello" as the first item in the list
list[list.length - 1] = 'hello'; // Set "hello" as the last item in the list
var tmpX = Math.floor(Math.random() * list.length); // Calculate a random index
list[tmpX] = 'hello'; // Set "hello" at a random position in the list
```

### Python Code
```python
import random

letters = None
list2 = None  # Use list2 to avoid shadowing Python’s built-in type name list.

list2[0] = 'hello'        # Set the text "hello" at the first position in the list
list2[-1] = 'hello'       # Set the text "hello" at the last position in the list
list2[0] = 'hello'        # Set "hello" as the first item in the list
list2[-1] = 'hello'       # Set "hello" as the last item in the list
tmp_x = int(random.random() * len(list2))  # Calculate a random index
list2[tmp_x] = 'hello'    # Set "hello" at a random position in the list
```

The meaning of the dropdown options can be found in the [previous section](#get-items-from-a-list).

The following example does two things:
1. It creates the **words** list as ["very", "very", "very"].
2. It replaces the third item in the list with "good".  
   The new value of **words** becomes ["very", "very", "good"].

<img src="https://github.com/user-attachments/assets/6edc376a-5d14-4683-b5f6-53846df36eb5" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var words;

function listsRepeat(value, n) { // Function to create a list by repeating the same value
    var array = [];
    for (var i = 0; i < n; i++) {
        array[i] = value;
    }
    return array;
}

words = listsRepeat('very', 3); // words = ["very", "very", "very"]
words[2] = 'good';              // words = ["very", "very", "good"]
```

### Python Code
```python
words = None

words = ['very'] * 3 # words = ['very','very','very']
words[2] = 'good'# words = ['very','very','good']
```

## Insert item at a specific position in a list  
The **Insert item at a specific position in a list** block can be obtained by selecting the appropriate option from the dropdown menu of the **Set item in list** block.

<img src="https://github.com/user-attachments/assets/7c378992-055b-49d6-a3b6-1d82f50a8b6a" alt="Block Composer"  /><br>

### JavaScript Code
```javascript
var words;

words.splice(2, 0, 'good'); // Insert the text "good" before the third position
words.splice(words.length - 3, 0, 'good'); // Insert the text "good" before the third position from the end
words.unshift('good'); // Insert the text "good" at the beginning
words.push('good'); // Insert the text "good" at the last position
var tmpX = Math.floor(Math.random() * words.length); // Calculate a random position
words.splice(tmpX, 0, 'good'); // Insert the text "good" at a random position
```

### Python Code
```python
import random

words = None

words.insert(2, 'good')  # Insert the text "good" before the third position
words.insert(-3, 'good') # Insert the text "good" before the third position from the end
words.insert(0, 'good')  # Insert the text "good" at the beginning
words.append('good')     # Insert the text "good" at the last position
tmp_x = int(random.random() * len(words))  # Calculate a random position
words.insert(tmp_x, 'good')  # Insert the text "good" at a random position
```

This block inserts a new item into a specified position in a list.  
For example, in the example below, three things happen:

1. The **words** list is created as ["very", "very", "very"].
2. The third item in the list is replaced with "good". The new value becomes ["very", "very", "good"].
3. The word "You're" is inserted at the beginning of the list. The final value becomes ["You're", "very", "very", "good"].

<img src="https://github.com/user-attachments/assets/3b81cd55-e390-4a06-8b14-49972430c1c0" alt="Block Composer" /><br>

### JavaScript Code
```javascript
var words;

function listsRepeat(value, n) { // Function to create a list with repeated values
   var array = [];
   for (var i = 0; i < n; i++) {
      array[i] = value;
   }
   return array;
}

words = listsRepeat('very', 3);
words[2] = 'good'; // words = ["very", "very", "good"]
words.splice(0, 0, "You're"); // words = ["You're", "very", "very", "good"]
```

### Python Code
```python
words = None

words = ['very'] * 3
words[2] = 'good'  # words = ['very', 'very', 'good']
words.insert(0, "You're")  # words = ["You're", 'very', 'very', 'good']
```

# Replace List Values and Return List

The **“extract a list with item … replaced by …”** block replaces the item at a specified position with another item and then returns the entire list.

<img src="https://github.com/user-attachments/assets/347921b9-683f-4c47-b69a-b23e99a41b8e" alt="Block Composer"   /><br>

### JavaScript Code
```javascript
var words;

words.map((data, idx) => (idx === 0 ? 'good' : data)); 
// Extract a new list where the first item of the words list is replaced with "good"

words.map((data, idx) => (idx === words.length - 1 ? 'good' : data)); 
// Extract a new list where the last item of the words list is replaced with "good"

words.map((data, idx) => (idx === 0 ? 'good' : data)); 
// Extract a new list where the first item of the words list is replaced with "good"

words.map((data, idx) => (idx === words.length - 1 ? 'good' : data)); 
// Extract a new list where the last item of the words list is replaced with "good"
```

### Python Code
```python
words = None

['good' if i == 0 else data for i, data in enumerate(words)]
# Extract a new list where the first item of the words list is replaced with "good"

['good' if i == len(words) - 1 else data for i, data in enumerate(words)]
# Extract a new list where the last item of the words list is replaced with "good"

['good' if i == 0 else data for i, data in enumerate(words)]
# Extract a new list where the first item of the words list is replaced with "good"

['good' if i == len(words) - 1 else data for i, data in enumerate(words)]
# Extract a new list where the last item of the words list is replaced with "good"
```

Refer to the [previous section](#getting-items-from-a-list) for the meaning of the dropdown options.

The following example performs three actions:
1. Creates the **words** list as ["very", "very", "very"].
2. Returns a new list in which the third item is replaced with "good", and assigns this list to a new variable **list**.
3. The **list** list becomes ["very", "very", "good"]. The value of the **words** list remains unchanged.

<img src="https://github.com/user-attachments/assets/29a28339-9dff-45eb-a3b3-603fd5481245" alt="Block Composer" /><br>  

<img src="https://github.com/user-attachments/assets/dd4d7589-2aef-4aeb-a50c-8bd5544af149" alt="Block Composer"   /><br>

### JavaScript Code
```javascript
var words, list;

function listsRepeat(value, n) { // Function to create a list by repeating the same value
    var array = [];
    for (var i = 0; i < n; i++) {
        array[i] = value;
    }
    return array;
}

words = listsRepeat('very', 3); // words = ["very", "very", "very"]
list = (list.map((data, idx) => (idx === 2 ? 'good' : data))); // list = ["very", "very", "good"]
```

### Python Code
```python
words = None
list2 = None  # Use list2 to avoid shadowing Python’s built-in type name list.

words = ['very'] * 3  # words = ['very', 'very', 'very']
list2 = ['good' if i == 2 else data for i, data in enumerate(words)]
# list2 = ['very', 'very', 'good']
```

# Splitting Texts and Combining Lists

## Create a List from Text

The **Create List from Text** block splits the given text into pieces using a specified delimiter:

<img src="https://github.com/user-attachments/assets/29460ece-3171-4310-988e-391282fb0459" alt="Block Composer"  /><br>

### JavaScript Code
```javascript
'311-555-2368'.split('-'); // Split using '-' as the delimiter, returns ["311", "555", "2368"]
```

### Python Code
```python
'311-555-2368'.split('-')  # Split using '-' as the delimiter, returns ["311", "555", "2368"]
```

In the example above, the new list is split into "311", "555", and "2368".

## Make Text from List
The **Make Text from List** block joins the items of a list into a single text text using a specified delimiter:

<img src="https://github.com/user-attachments/assets/1744495d-0af8-4de0-bb8d-86642f22cf43" alt="Block Composer" /><br>  

### JavaScript Code
```javascript
['311', '555', '2368'].join('-'); // Join the list into a single text using '-' as the delimiter: "311-555-2368"
```

### Python Code
```python
'-'.join(['311', '555', '2368'])  # Join the list into a single text using '-' as the delimiter: "311-555-2368"
```

The new text returned in the example above is **"311-555-2368"**.

# Related Blocks

## Print List  
The [Text “Print” block](https://github.com/RobomationLAB/User_Guide_EN/wiki/문자열#문자열-출력) can be used to print a list.  
The result of the program below is displayed in an alert dialog:

<img src="https://github.com/user-attachments/assets/c2a80f23-e16d-495e-beb6-9cbc3f30d111" alt="Block Composer" /><br>  

### JavaScript Code
```javascript
var letters;

letters = ['one', 'two', 'three'];
window.alert(letters); // Print the list
```

### Python Code
```python
letters = None

letters = ['one', 'two', 'three']
print(letters)  # Print the list
```

`one, two, three` is printed.

## For Each Item in a List
The “for each item” block in [Loops](https://github.com/RobomationLAB/User_Guide_EN/wiki/반복#각-항목에-대해) performs an operation on each item in a list.  
For example, the blocks below print each item in the list individually:

<img src="https://github.com/user-attachments/assets/04e7656b-e8c1-4b2c-872d-e207a11fbf54" alt="Block Composer" /><br>  

### JavaScript Code
```javascript
var letter;

var letters_list = ['one', 'two', 'three'];
for (var letters_index in letters_list) { // Print each item in the list
    letter = letters_list[letters_index];
    window.alert(letter);
}

```

### Python Code
```python
letter = None
for letter in ['one', 'two', 'three']:  # Print each item in the list
    print(letter)
```

`one`, `two`, and `three` are printed sequentially.  
This operation does not remove items from the original list.

You can also refer to examples of the  
[Loop Termination Block](https://github.com/RobomationLAB/User_Guide_EN/wiki/반복#반복문-종료-블록).

# List Order  
These blocks allow you to change the order of items in a list.

## Sort  
This block **sorts a list** based on the selected criteria.  
You can sort by numbers or alphabetic order, and choose either ascending or descending order.  
Additionally, when sorting alphabetically, you can choose to ignore case sensitivity.

<img src="https://github.com/user-attachments/assets/0f78cf8c-672f-4897-9c93-b5524dfd4daa" alt="Block Composer" /><br>  

<img src="https://github.com/user-attachments/assets/67a0f1dc-24d7-4ab0-86b3-0992d4f5b34b" alt="Block Composer" /><br>  

### JavaScript Code
```javascript
function listsGetSortCompare(type, direction) { // Text comparison function
    var compareFuncs = {
        'NUMERIC': function(a, b) {
                return Number(a) - Number(b); },
        'TEXT': function(a, b) {
                return String(a) > String(b) ? 1 : -1; },
        'IGNORE_CASE': function(a, b) {
                return String(a).toLowerCase() > String(b).toLowerCase() ? 1 : -1; },
    };
    var compare = compareFuncs[type];
    return function(a, b) { return compare(a, b) * direction; };
}

[].slice().sort(listsGetSortCompare("NUMERIC", 1));   // Numeric, ascending order
[].slice().sort(listsGetSortCompare("NUMERIC", -1));  // Numeric, descending order
[].slice().sort(listsGetSortCompare("TEXT", 1));      // Text, ascending order
[].slice().sort(listsGetSortCompare("TEXT", -1));     // Text, descending order
[].slice().sort(listsGetSortCompare("IGNORE_CASE", 1));  // Alphabetical (case-insensitive), ascending
[].slice().sort(listsGetSortCompare("IGNORE_CASE", -1)); // Alphabetical (case-insensitive), descending
```

### Python Code
```python
def lists_sort(my_list, type, reverse):  # Sorting function
    def try_float(s):
        try:
            return float(s)
        except:
            return 0

    key_funcs = {
        "NUMERIC": try_float,                 # Numeric sorting
        "TEXT": str,                          # Text sorting
        "IGNORE_CASE": lambda s: str(s).lower()  # Case-insensitive alphabetical sorting
    }

    key_func = key_funcs[type]
    list_cpy = list(my_list)
    return sorted(list_cpy, key=key_func, reverse=reverse)

lists_sort([], "NUMERIC", False)      # Numeric, ascending order
lists_sort([], "NUMERIC", True)       # Numeric, descending order
lists_sort([], "TEXT", False)         # Text, ascending order
lists_sort([], "TEXT", True)          # Text, descending order
lists_sort([], "IGNORE_CASE", False)  # Alphabetical (case-insensitive), ascending order
lists_sort([], "IGNORE_CASE", True)   # Alphabetical (case-insensitive), descending order
```

In the example below, the list `[gamma, beta, alpha]` is sorted in **ascending alphabetical order** to create a new list called `sortLetters`.

<img src="https://github.com/user-attachments/assets/41feb57c-7bc0-408f-933d-ee49e5cf5605" alt="Block Composer" /><br>  

The output result is: `[alpha, beta, gamma]`

### JavaScript Code
```javascript
var letters, sortLetters;

function listsGetSortCompare(type, direction) { // character comparison function
    var compareFuncs = {
        'NUMERIC': function(a, b) {
                return Number(a) - Number(b); },
        'TEXT': function(a, b) {
                return String(a) > String(b) ? 1 : -1; },
        'IGNORE_CASE': function(a, b) {
                return String(a).toLowerCase() > String(b).toLowerCase() ? 1 : -1; },
    };
    var compare = compareFuncs[type];
    return function(a, b) { return compare(a, b) * direction; };
}

letters = ['gamma', 'beta', 'alpha'];
sortLetters = letters.slice().sort(listsGetSortCompare("TEXT", 1)); // sort in ascending alphabetical order
window.alert(sortLetters); // ['alpha', 'beta', 'gamma']
```

### Python Code
```python
letters = None
sortLetters = None

def lists_sort(my_list, type, reverse):  # text sorting function
    def try_float(s):
        try:
            return float(s)
        except:
            return 0
    key_funcs = {
        "NUMERIC": try_float,
        "TEXT": str,
        "IGNORE_CASE": lambda s: str(s).lower()
    }
    key_func = key_funcs[type]
    list_cpy = list(my_list)
    return sorted(list_cpy, key=key_func, reverse=reverse)

letters = ['gamma', 'beta', 'alpha']
sortLetters = lists_sort(letters, "TEXT", False)  # sort in ascending alphabetical order
print(sortLetters)  # ['alpha', 'beta', 'gamma']
```

## Reverse  
This block **reverses the order of elements** in a list.

<img src="https://github.com/user-attachments/assets/89cf621c-6861-4305-bb94-e8c5b30fa193" alt="Block Composer" /><br>. 

### JavaScript Code
```javascript
[].slice().reverse(); // Reverse the list order
```

### Python Code
```python
list(reversed([]))  # Reverse the list order
```

In the example below, the sorted `sortLetters` list is reversed to create the list `[gamma, beta, alpha]`.

<img src="https://github.com/user-attachments/assets/d5580873-6cfd-4918-be53-705b0904c4f6" alt="Block Composer" /><br>

### JavaScript Code

```javascript
var letters, sortLetters;

function listsGetSortCompare(type, direction) { // Text comparison function
    var compareFuncs = {
        'NUMERIC': function(a, b) {
            return Number(a) - Number(b);
        },
        'TEXT': function(a, b) {
            return String(a) > String(b) ? 1 : -1;
        },
        'IGNORE_CASE': function(a, b) {
            return String(a).toLowerCase() > String(b).toLowerCase() ? 1 : -1;
        },
    };
    var compare = compareFuncs[type];
    return function(a, b) { return compare(a, b) * direction; };
}

letters = ['gamma', 'beta', 'alpha'];
sortLetters = letters.slice().sort(listsGetSortCompare("TEXT", 1)); 
// Sort in ascending alphabetical order → ['alpha', 'beta', 'gamma']

sortLetters.slice().reverse(); 
// Reverse the list → ['gamma', 'beta', 'alpha']
```

### Python Code

```python
letters = None
sortLetters = None

def lists_sort(my_list, type, reverse):  # Text sorting function
    def try_float(s):
        try:
            return float(s)
        except:
            return 0

    key_funcs = {
        "NUMERIC": try_float,
        "TEXT": str,
        "IGNORE_CASE": lambda s: str(s).lower()
    }

    key_func = key_funcs[type]
    list_cpy = list(my_list)
    return sorted(list_cpy, key=key_func, reverse=reverse)

letters = ['gamma', 'beta', 'alpha']
sortLetters = lists_sort(letters, "TEXT", False)
# Sort in ascending alphabetical order → ['alpha', 'beta', 'gamma']

list(reversed(sortLetters))
# Reverse the list → ['gamma', 'beta', 'alpha']
```