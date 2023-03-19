# Regular Expressions

Regular expressions are a powerful tool for text processing. They are used in many programming languages, including Python. In this tutorial, we will learn how to use regular expressions in Python.

## What are regular expressions?

Regular expressions are a sequence of characters that define a search pattern. They are used to check if a string contains the specified search pattern.

## Why do we need regular expressions?

Regular expressions are extremely useful in extracting information from text such as code, log files, spreadsheets, or even documents. They can help us find specific strings or matches in a text.

## How do regular expressions work?

Regular expressions use special characters to define a search pattern. For example, the search pattern `"[a-z]"` will match any lowercase letter from `a` to `z`. The search pattern `"[0-9]"` will match any digit from `0` to `9`.

## How to use regular expressions in Python?

In Python, regular expressions are a part of the `re` module. We can use the `re` module to search, match, and replace text.

### The `re.search()` function

The `re.search()` function searches a string for a match, and returns a `Match` object if there is a match. If there is more than one match, only the first occurrence of the match will be returned.

```python
import re

txt = "The rain in Spain"
x = re.search("^The.*Spain$", txt)

if x:
  print("YES! We have a match!")
else:
  print("No match")
```

The output of the above code is:

```bash
YES! We have a match!
```

### The `re.findall()` function

The `re.findall()` function returns a list containing all matches.

```python
import re

txt = "The rain in Spain"

# Find all lower case characters alphabetically between "a" and "m":

x = re.findall("[a-m]", txt)
print(x)
```

The output of the above code is:

```bash
['h', 'e', 'a', 'i', 'i', 'a', 'i']
```

### The `re.split()` function

The `re.split()` function splits the string where there is a match and returns a list of strings where the splits have occurred.

```python
import re

txt = "The rain in Spain"

# Split at each white-space character:

x = re.split("\s", txt)
print(x)
```

The output of the above code is:

```bash
['The', 'rain', 'in', 'Spain']
```

### The `re.sub()` function

The `re.sub()` function replaces the matches with the text of your choice.

```python
import re

txt = "The rain in Spain"

# Replace every white-space character with the number 9:

x = re.sub("\s", "9", txt)
print(x)
```

The output of the above code is:

```bash
The9rain9in9Spain
```

### Match object

A Match Object is an object containing information about the search and the result.

```python
import re

txt = "The rain in Spain"

# Search for a sequence that starts with "The" and ends with "Spain":

x = re.search("^The.*Spain$", txt)

if x:
  print("YES! We have a match!")
else:
  print("No match")
```

The output of the above code is:

```bash
YES! We have a match!
```

Regular expressions are difficult to understand at first. But once you get the hang of it, you will find them very useful. In the next tutorial, we will learn about the `re` module in Python.

To learn more about regular expressions, visit the [Regular Expression HOWTO](https://docs.python.org/3/howto/regex.html) page.

In this tutorial, we learned how to use regular expressions in Python. We learned about the `re` module and its functions. We also learned about the `Match` object.
