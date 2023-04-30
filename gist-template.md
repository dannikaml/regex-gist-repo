# **HexPert**

In this tutorial, we will learn about a commonly used regular expression called the Hex Value Regex and how it is used to match hexadecimal color values. 

## **Summary**

For this tutorial we will use `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` to breakdown how to match color code. Color code starts with the hashtag or pound symbol: `#`, followed by six or three-digit code using the numbers and letters of the Hexadecimal system. For starters Hex Values refer to Hexadecimal. Hexadecimal is described as "a base-16 number system". When utilized in code it represents large numbers by using fewer digits - these numbers are: **0, 1, 2, 3, 4, 5, 6, 7, 8, 9** and six letters: **a, b, c, d, e, f**. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Back-references](#back-references)

## Regex Components

### **Anchors**
***
For starters, we know that anchors are the special characters in regex's that help match a pattern but only when used at the beginning or end of a string or line of characters. 

Where Hex values are concerned these symbols are: `^` and `$` 
The `^` is called a caret, is the symbol that appear at the beginning of a string. 
While the dollar sign `$` the anchor that matches the end. 

When the two symbols are used together, in their respective positions, the beginning and end, they can be used to match and entire string of random numbers and symbols, thereby validating that whatever is being searched for or compared to is the exact same. 

### **Quantifiers**
***
Regex Quantifiers use curly braces, `{}`, to define or specify that the preceding characters or group of characters need to match. When referring back to our sample code /^#?([a-f0-9] **{6}** |[a-f0-9] **{3}** )$/ we can see that the curly braces are surrounding the `{6}` and the `{3}`. This means that the quantifier specifies that the hexadecimal value should be 6 or 3 characters long. 



A few common quantifiers can also be as follows: 
`*`, `?`, and `+` which all match the preceding characters zero or more times. 

It should also be noted that quantifiers can be useful for identifying/matching patterns that have multiple occurrences within a string or a character set and helps us avoid having to specify each instance individually. Having said that, it is important when using quantifiers to be careful so as to avoid excessive matching, or the adverse, not matching enough in a pattern. 

### **OR Operator**
***
In the instance of our example string /^#?([a-f0-9]{6} **|** [a-f0-9]{3})$ the OR Operator would be the `|` value. 

Where regex is concerned, a developer can utilize this to match one set of patterns to another. So our string `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` is comparing the 6 digit value to the 3 digit value. 

### **Character Classes**
Character classes - Here is where we will see our first color code! Color code is a string of the random numbers or symbols in the Hexadecimal value system. In this case we will use `#a71e2c` for our example. 

Character classes allows the developer to match any character that belongs to a specific set; and since we are using the Hexadecimal system of 16 numbers or symbols we know all the character classes of "[a-f0-9]" will match any character that is either a lowercase letter from "a" to "f", or a digit from "0" to "9". 

So when referring back to our example color code `#a71e2c`; we can deduce that the character class will match `a` and `7`, `1`, `e`, `5` and `c`


### **Grouping and Capturing**
***
Utilizing a Capturing Group essentially has two effects; the first is that it allows for a part of the pattern to match as a separate item in the array or string. And the second when or if a developer puts a quantifier after the parentheses it then applies to the contents of the parenthesis as a whole. 

Developers can use the parenthesis `(...)` or round brackets by placing them around parts of the hex value and by doing so allows the developer to then apply a quantifier or restrict alteration of that part of the regex.

In our example code `^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, **([a-f0-9]{6}|[a-f0-9]{3})** is the capturing group. When a color code string specifically is checked against the regular expression or regex, the part of the code that matches the pattern inside the `(...)` or paranthesis is saved for later use. 

A simpler example of this is if as a developer you use the color code `#aaa000` and then that is checked against the regex, the hex value is `(aaa000)` and it is then captured and saved. 

### **Back-references**
***
Back-references can use parts of matched string again in a regex. This is usually most helpful, in regards to color code, when you need to match hex values that have repeating characters. 

To explore an example of how this looks in regards to color code, we'll have to take a peek back at our example string: `^#?([a-f0-9]{6}|[a-f0-9]{3})$/`. In this instance, the repeating characters might look something like this `#00ff00 or #aabbcc`. However, if we wanted to modify the regular expression (regex) to also capture some of the repeat characters, we could use a back-reference. 

If we changed our original example string to this instead `^#?([a-f0-9])\1{2}([a-f0-9])\2{2}([a-f0-9])\3{2}$` then we would be able to capture color codes like #00ff00 or #aabbcc, but not #f00 or #abc. The back-reference in this case is `\1` and refers to the first captured group, and the `\2` refers to the second captured group, and so on.


## **Author**
***
Hi, I'm newer to the world of web development! My name is Dannika Long, and this is my first gist! As I continue to explore new technologies, I'm constantly learning and working on new projects to enhance my skills.

One of the important technologies that I'm currently exploring is regex. I'm creating this gist as a way to document and explore regex in more detail (and also as a homework assignment ((=  ). I hope that this will be helpful for any other new developers who are also looking for more info and/or knowledge as we continue on our learning journey's. 

As I continue to learn and explore new technologies, you can expect to see more projects and resources from me in the future! You can check those out here: [GitHub Profile: https://github.com/dannikaml](https://github.com/dannikaml)