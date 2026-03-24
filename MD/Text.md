Examples of texts include:
- "thing #1"
- "March 12, 2010"
- "" (empty text)

Texts can contain uppercase or lowercase letters, numbers, punctuation, other symbols, and spaces between words.

<br>

# Blocks

## Create Text

The following block creates the text "hello" and stores it in a variable named `greeting`.

<img src="https://github.com/user-attachments/assets/58837d48-8efa-4b2d-9637-b024bbe261c7" alt="Block Composer" /><br> 

### Javascript Code
```javascript
var greeting;

greeting = 'hello';
```


### Python Code
```python
greeting = None

greeting = 'hello'
```

The **Join** block concatenates the value of `greeting` with the text "`world`", producing "`helloworld`".
Since neither of the original texts contains a space, the resulting text has no spaces.

<img src="https://github.com/user-attachments/assets/1b22e274-3a89-4e54-b8c6-0580defc2dd9" alt="Block Composer" /><br>

### Javascript Code
```javascript
var greeting;

greeting = 'hello';
String(greeting) + 'world'; // "helloworld"
```

### Python Code
```python
greeting = None

greeting = 'hello'
str(greeting) + 'world'  # "helloworld"
```

To increase the number of input texts, click the gear icon. The view will change as shown below:

<img src="https://github.com/user-attachments/assets/12ab05ac-3886-4bd5-954f-079f904679d7" alt="Block Composer" width="20%" /><br>

To add additional inputs, drag the **Item** block from the gray toolbox on the left and insert it into the **Join** block.

## Modify Text
The **append text** block adds the given text to the specified variable.  
In the example below, the value of the `greeting` variable changes from `"hello"` to `"hello, there!"`.

<img src="https://github.com/user-attachments/assets/d158c5bf-20e7-46f8-9dd0-9c108741bba6" alt="Block Composer" /><br>

### Javascript Code
```javascript
var greeting;

greeting = 'hello';
greeting += ', there!'; // greeting becomes "hello, there!"
```

### Python Code
```python
greeting = None

greeting = 'hello'
greeting = str(greeting) + ', there!'  # greeting becomes "hello, there!"
```

## Text Length
The **Length** block counts the number of characters (letters, numbers, symbols, etc.) in a text and returns the total length.  
For example, the length of "`We're #1!`" is 9, and the length of an empty text is 0.

<img src="https://github.com/user-attachments/assets/c80def78-c818-4c00-850b-12db0fd205df" alt="Block Composer" /><br>

<img src="https://github.com/user-attachments/assets/33235fe0-5b37-475b-bf59-f1e5aaa924fb" alt="Block Composer" /><br>


### Javascript Code
```javascript
'We\'re #1!'.length; // Returns the text length of 'We're #1!' → 9
''.length;           // Returns the text length of an empty text → 0
```

### Python Code
```python
len("We're #1!")  # Returns the text length of "We're #1!" → 9
len('')           # Returns the text length of an empty text → 0
```

## Is Empty
The **Is Empty** block checks whether the given text is empty (that is, whether its length is 0).  
The first example returns **true**, and the second returns **false**.

<img src="https://github.com/user-attachments/assets/6a98a628-be90-438f-a2d2-8921d3a4baee" alt="Block Composer" /><br>

<img src="https://github.com/user-attachments/assets/45af16b6-6001-486d-85d5-29ee46c38277" alt="Block Composer" /><br>


### Javascript Code
```javascript
var greeting;

greeting = 'hello';
!''.length;        // Returns true because the text is empty
!greeting.length;  // Returns false because the text is not empty
```

### Python Code
```python
greeting = None

greeting = 'hello'
not len('')        # Returns true because the text is empty
not len(greeting)  # Returns false because the text is not empty
```

## Finding Text
These blocks check whether a specific text exists within another text and, if it does, return its position.  
For example, the block below requests the position of the first occurrence of "`e`" in "`hello`", and the result is 2.

<img src="https://github.com/user-attachments/assets/6b8c6ba6-08db-45f9-b912-961636527886" alt="Block Composer" /><br>

The block below requests the position of the last occurrence of "`e`" in "`hello`", and the result is also 2.

<img src="https://github.com/user-attachments/assets/2ae5f73f-7ec5-4f74-9d3b-d1e4d1df0838" alt="Block Composer"  /><br>

Even if the **First** or **Last** option is selected, since "`hello`" does not contain "`z`", the result is 0.

<img src="https://github.com/user-attachments/assets/26894bae-896a-4776-a157-1a0d65fc2873" alt="Block Composer" /><br>

### Javascript Code

```javascript
'hello'.indexOf('e') + 1;      // Returns 2: the position where 'e' first appears in the text "hello"
'hello'.lastIndexOf('e') + 1; // Returns 2: the position where 'e' last appears in the text "hello"
'hello'.indexOf('z') + 1;     // Returns 0: 'z' does not exist in the text "hello"
```

### Python Code

```python
'hello'.find('e') + 1   # Returns 2: the position where 'e' first appears in the text "hello"
'hello'.rfind('e') + 1  # Returns 2: the position where 'e' last appears in the text "hello"
'hello'.find('z') + 1   # Returns 0: 'z' does not exist in the text "hello"
```

## Text Extraction

### Extracting a Single Character
This block retrieves the second character "`b`" from the text "`abcde`".

<img src="https://github.com/user-attachments/assets/3cd6a8fd-3bff-4283-bc13-13563d2a4ec0" alt="Block Composer"  /><br>

### Javascript Code
```javascript
'abcde'.charAt(1); // Returns the second character 'b' from the text "abcde"
```

### Python Code
```python
'abcde'[1]  # Returns the second character 'b' from the text "abcde"
```

<img src="https://github.com/user-attachments/assets/820f5aa4-a7bb-40d6-80e5-443d922e0152" alt="Block Composer" /><br>

### Javascript Code
```javascript
function textRandomLetter(text) { // Function that returns a random character
   var x = Math.floor(Math.random() * text.length);
   return text[x];
}

'abcde'.charAt(1);            // Get the second character from the front: 'b'
'abcde'.slice(-2).charAt(0);  // Get the second character from the end: 'd'
'abcde'.charAt(0);            // Get the first character: 'a'
'abcde'.slice(-1);            // Get the last character: 'e'
textRandomLetter('abcde');    // Get one random character
```

### Python Code
```python
import random

def text_random_letter(text):  # Function that returns a random character
    x = int(random.random() * len(text))
    return text[x]

'abcde'[1]    # Get the second character from the front: 'b'
'abcde'[-2]   # Get the second character from the end: 'd'
'abcde'[0]    # Get the first character: 'a'
'abcde'[-1]   # Get the last character: 'e'
text_random_letter('abcde')  # Get one random character
```

### Extracting a Subtext
The **Get substring from text** block allows you to extract a specific range of characters from a text.

<img src="https://github.com/user-attachments/assets/aa98dbfe-154e-4526-9041-d7c9c6950bd4" alt="Block Composer" /><br>

The block above extracts the text **"abc"**.

### Javascript Code
```javascript
'abcde'.slice(0, 3); // Returns the substring "abc" from "abcde" (from the first to the third character)
```

### Python Code
```python
'abcde'[:3]  # Returns the substring "abc" from "abcde" (from the first to the third character)
```

<img src="https://github.com/user-attachments/assets/61a87253-af29-4fa4-96bc-97873f62ab60" alt="Block Composer" /><br>

<img src="https://github.com/user-attachments/assets/648049b8-1d15-46bd-8999-274b3ab9387e" alt="Block Composer" /><br>


### Javascript Code

```javascript
'abcde'.slice(1, 4); 
// Extracts the substring "bcd" from "abcde" (from the 2nd character to the 4th character)
'abcde'.slice(1, 'abcde'.length - 1); 
// Extracts the substring "bcd" from "abcde" (from the 2nd character to the 2nd character from the end)
'abcde'.slice(1, 'abcde'.length); 
// Extracts the substring "bcde" from "abcde" (from the 2nd character to the last character)
'abcde'.slice('abcde'.length - 4, 4); 
// Extracts the substring "bcd" from "abcde" (from the 4th character from the end to the 4th character)
'abcde'.slice('abcde'.length - 4, 'abcde'.length - 1); 
// Extracts the substring "bcd" from "abcde" (from the 4th character from the end to the 2nd character from the end)
'abcde'.slice('abcde'.length - 4, 'abcde'.length); 
// Extracts the substring "bcde" from "abcde" (from the 4th character from the end to the last character)
'abcde'.slice(0, 4); 
// Extracts the substring "abcd" from "abcde" (from the 1st character to the 4th character)
'abcde'.slice(0, 'abcde'.length - 1); 
// Extracts the substring "abcd" from "abcde" (from the 1st character to the 2nd character from the end)
'abcde'; 
// Represents the full text "abcde" (from the first to the last character)
```

### Python Code

```python
'abcde'[1:4]  
# Extracts the substring "bcd" from "abcde" (from the 2nd character to the 4th character)
'abcde'[1:-1]  
# Extracts the substring "bcd" from "abcde" (from the 2nd character to the 2nd character from the end)
'abcde'[1:]  
# Extracts the substring "bcde" from "abcde" (from the 2nd character to the last character)
'abcde'[-4:4]  
# Extracts the substring "bcd" from "abcde" (from the 4th character from the end to the 4th character)
'abcde'[-4:-1]  
# Extracts the substring "bcd" from "abcde" (from the 4th character from the end to the 2nd character from the end)
'abcde'[-4:]  
# Extracts the substring "bcde" from "abcde" (from the 4th character from the end to the last character)
'abcde'[:4]  
# Extracts the substring "abcd" from "abcde" (from the 1st character to the 4th character)
'abcde'[:-1]  
# Extracts the substring "abcd" from "abcde" (from the 1st character to the 2nd character from the end)
'abcde'[:]  
# Extracts the full text "abcde" (from the first to the last character)
```

## Change Text Case

This block converts the input text into one of the following formats:

- **Uppercase** (converts all characters to uppercase)
- **Lowercase** (converts all characters to lowercase)
- **Capitalize First Letter** (capitalizes the first letter of each word and lowercases the remaining letters)

The result of the block below is `"HELLO"`.

<img src="https://github.com/user-attachments/assets/ba123727-afbe-4679-a69f-e0f1023a9d41" alt="Block Composer" /><br>

### Javascript Code
```javascript
function textToTitleCase(str) { // Function that converts only the first letter of each word to uppercase
    return str.replace(/\S+/g,
        function(txt) {
            return txt[0].toUpperCase() + txt.substring(1).toLowerCase();
        });
}

'hello'.toUpperCase();   // Converts all characters in the text to uppercase, returns 'HELLO'
'hello'.toLowerCase();   // Converts all characters in the text to lowercase, returns 'hello'
textToTitleCase('hello'); // Converts each word to start with an uppercase letter and the rest to lowercase, returns 'Hello'
```

### Python Code
```python
'hello'.upper()  # Converts all characters in the text to uppercase, returns 'HELLO'
'hello'.lower()  # Converts all characters in the text to lowercase, returns 'hello'
'hello'.title()  # Converts each word to start with an uppercase letter and the rest to lowercase, returns 'Hello'
```

## Trim Whitespace
This block removes whitespace from specific positions in a text:
- The beginning of the text
- The end of the text
- Both the beginning and the end

The result of the block below is `"hi   there"`.
(The spaces in the middle of the text are preserved.)

<img src="https://github.com/user-attachments/assets/b0c2a8bb-bef9-42b2-8adc-d14338a69c4c" alt="Block Composer" /><br>


### Javascript Code
```javascript
' hi there '.trim(); 
// Removes whitespace from both sides, returns 'hi there'
' hi there '.replace(/^[\s\xa0]+/, ''); 
// Removes whitespace from the left side, returns 'hi there '
' hi there '.replace(/[\s\xa0]+$/, ''); 
// Removes whitespace from the right side, returns ' hi there'
```

### Python Code
```python
' hi there '.strip()  
# Removes whitespace from both sides, returns 'hi there'
' hi there '.lstrip()  
# Removes whitespace from the left side, returns 'hi there '
' hi there '.rstrip()  
# Removes whitespace from the right side, returns ' hi there'
```

## Count Occurrences of a Substring in a Text
This feature counts how many times a specific word (substring) appears in a given text and returns the count.

<img src="https://github.com/user-attachments/assets/8c952aed-280d-4351-9bb3-ef84ea343cba" alt="Block Composer" /><br>

### Javascript Code
```javascript
function textCount(haystack, needle) { // Function to count occurrences of a specific substring
    if (needle.length === 0) {
        return haystack.length + 1;
    } else {
        return haystack.split(needle).length - 1;
    }
}

textCount('abc, abc, ab', 'abc'); 
// Returns 2: the number of times "abc" appears in the text "abc, abc, ab"
```

### Python Code
```python
'abc, abc, ab'.count('abc')  
# Returns 2: the number of times "abc" appears in the text "abc, abc, ab"
```

Returns 2 because the substring `"abc"` appears twice in the text `"abc, abc, ab"`.

## Replace Specific Characters in a Text

This feature replaces a specific character (or substring) in a text with another character of your choice.  
You can select the target character and substitute it with a new one.

<img src="https://github.com/user-attachments/assets/e62e8906-f431-4e5a-a6bf-60fd5d6b17b8" alt="Block Composer" /><br>

In the text `"abc, abc, ab"`, the substring `"abc"` is replaced with `"ABC"`.  
The result of executing this block is `"ABC, ABC, ab"`.

### Javascript Code
```javascript
function textReplace(haystack, needle, replacement) { // Function to replace a specific substring in a text
    needle = needle.replace(/([-()\[\]{}+?*.$\^|,:#<!\\])/g, '\\$1').replace(/\x08/g, '\\x08');
    return haystack.replace(new RegExp(needle, 'g'), replacement);
}

textReplace('abc, abc, ab', 'abc', 'ABC'); 
// Replaces "abc" with "ABC" in the text "abc, abc, ab", Returns "ABC, ABC, ab"
```

### Python Code
```python
'abc, abc, ab'.replace('abc', 'ABC')
# Replaces "abc" with "ABC" in the text "abc, abc, ab"
# Returns "ABC, ABC, ab"
```

## Reverse Text
This function returns a new text with the characters in reverse order.

<img src="https://github.com/user-attachments/assets/d9a4be7c-69a9-4d77-aac5-07d9cea2eb5e" alt="Block Composer" /><br>

The result of reversing `"hello"` is `"olleh"`.

### Javascript Code
```javascript
'hello'.split('').reverse().join(''); // Returns "olleh", which is the reversed text of "hello"
```

### Python Code
```python
'hello'[::-1]  # Returns "olleh", which is the reversed text of "hello"
```

## Print Text
The **Print** block displays the input value in a pop-up window.

<img src="https://github.com/user-attachments/assets/80857f88-db55-441b-83de-741ed7d6443c" alt="Block Composer" /><br>

<img src="https://github.com/user-attachments/assets/e5cac838-5ceb-4d7f-9dcd-bceb2ba0c6a0" alt="Block Composer" /><br>


### Javascript Code
```javascript
window.alert('Hello!'); // Displays "Hello!" in a pop-up window
```

### Python Code
```python
print('Hello!') # Displays "Hello!" in a pop-up window
```

## Receive User Input
The following block displays a popup window that asks the user to enter their name,  
and the entered value is stored in the **`name`** variable.

<img src="https://github.com/user-attachments/assets/dd225a30-f82e-41f3-b0e5-7925d5ee17ad" alt="Block Composer" /><br>


### Javascript Code
```javascript
var name2;

name2 = window.prompt('Please enter your name:');
```

### Python Code
```python
name = None

def text_prompt(msg):  # input function
    try:
        return raw_input(msg)
    except NameError:
        return input(msg)

name = text_prompt('Please enter your name:')
```

There is also a version that receives numeric input from the user.

<img src="https://github.com/user-attachments/assets/e0276912-a0d0-4741-85eb-990de07b0415" alt="Block Composer" /><br>

### Javascript Code
```javascript
var age;

age = Number(window.prompt('Enter your age:'));
```

### Python Code
```python
age = None

def text_prompt(msg):  # function to receive user input
    try:
        return raw_input(msg)
    except NameError:
        return input(msg)

age = float(text_prompt('Enter your age:'))
```