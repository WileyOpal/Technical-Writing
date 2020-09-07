# Simple Strings in Python

What are strings and how do we manipulate them? Those questions are the focus of this tutorial. The target audience for this tutorial is people who are new to programming and are fairly new to Python. We assume that you already know at least a little about functions in Python. 

## What is a String?

A **string** is a group of one or more characters. A string can contain any combination of numbers, letters, words, symbols, or white spaces. For example, the following are all valid strings in Python:

- `"Welcome to my portfolio."`
- `'123 Fake Street: I like what you've done with the place!'`
- `"   "`
- `' %^*#% '`
- `"2 + 3 = five"`
- `'9293847'`
- `"I can't remember whether we need 8 or 9 cups of sugar."`


Strings do not have to be in English. Any character may be stored inside a Python string.

## How to Assign Strings to Variables

One equal sign (`=`) is the assignment operator. You assign a string to a variable using the assignment operator. For example:
```python
	favorite_game = "Settlers of Catan"
```

When you specify a string, the quotation marks can be double or single but must be consistent; a string must start and end with the same type of quotation mark. The first quotation mark tells Python, "start the string," and the second quotation mark tells Python, "end the string." Just as in English, quotation marks must come in pairs. 

If there's another quotation mark of the same type in the middle of the string, Python will think that is where you want the string to stop. This is a very common mistake, and one of the first things you should look for if your code isn't performing correctly. 

Notice that there's an apostrophe in the following sample string:
```python
	"You can't always get what you want."
```
Because you started that string with a double quotation mark, you can use single quotation marks inside your string without ending the string. Only a double quotation mark can end a string that starts with a double quotation mark. This allows you to use apostrophes, accent marks, and quotes inside a string. For example:

- `"I don't know what you mean."`
- `"J'ai découvert une pièce secrète dans ma maison."`
- `"'Well I never!' she exclaimed."`

### A Quick Note on Debugging

The Python interpreter can help you detect errors. When you type your code into an interpreter, you will notice that strings get their own color. If a string is not the color it is supposed to be in your interpreter, check for an error in quotation mark consistency or placement.

## Strings and Integers

Numbers inside a string are part of that string and are treated like any other character. Numbers are not treated as integers (whole numbers) unless you instruct Python to treat them as integers. For example, consider the following problematic code:
```python
	apples = "5"
	apple_halves = apples * 2
```
The `apples` variable is set to the string "`5`." You cannot multiply a string by a number. Therefore, Python generates an error message. Imagine you have five pictures of apples; you can cut all of those pictures in half but you'll never get edible apple halves.

By contrast, the following code sets `apples` to the integer 5 rather than the string “`5`”:
```python
	apples = 5
	apple_halves = apples * 2
```
Now the variable `apples` is set to the integer 5. You can, therefore, perform any mathematical operation with the variable `apples` that you can perform with the number 5.


## Outputting Strings

Call the `print` function to output a string. For example:
```python	
	print("Hello!") #output a string
```
or:
```python
	simple_greeting = "Hello!"
	print(simple_greeting) #output the value of the variable
```

The output of both examples is:
```python
        Hello!
```
## String Functions

Python provides a standard set of functions to manipulate strings. For example, `capitalize()` puts the first letter of your string into uppercase, and `lower()` will return your string with every letter lower case. Let's look at a few more examples and their outputs:
```python
	message = "I want a sandwich." #a random string

	print(message.upper()) #output every character in message in uppercase
```
The output for `print(message.upper())`is:
```python
	I WANT A SANDWICH.
```

The `len()` function finds the length of a string:
```python
	message = "I want a sandwich." #a random string

	length_of_message = len(message) #finds the length of the string
```
The value of `length_of_message` is `18`, because there are 18 characters in the string, including white spaces and punctuation.

You can find the full list of Python string functions [here](https://www.w3schools.com/python/python_ref_string.asp).

###  Null Strings: an advanced topic

A string can also be **null**; that is, the string could have zero characters. For example, the following assigns a null string to the variable `zilch`: 
```python
	zilch = ""
```
A null string shows Python that the string still exists, but just happens to be empty right now. 


Thanks for reading.
