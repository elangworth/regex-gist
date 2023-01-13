#Learn how to Validate Password Criteria Using Regex

### Introduction

Regular expressions, aka regex, are a series of special characters that define a search pattern. In this tutorial we will see that the regular expression checks to see if a string meets all the criteria set forth below to create a password.

* Minimum of 1 Lowercase Letter <br>
* Minimum of 2 Uppercase Letters<br>
* Minimum of 1 Number<br>
* Minimum of 1 Special Character<br>
* Password must be 8 or more Characters<br>
<div align="center">/^(?=(.*[a-z]){1,})(?=(.*[A-Z]){2,})(?=.*[0-9]{1,})(?=(.*[!@#$%^&*_+=]){1,}).{8,}$/</div>

### Summary

Regular expressions are used to locate certain patterns of characters found in a string. Regular expressions are very useful in validating user input, especially when dealing with passwords. For example, suppose we have a database of logins that are checked against a set of passcode requirements. We’ll need to make sure that we aren’t allowing people who have not met the requirements to attempt to log in with only their usernames as their password.

## Table of Contents

- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Operators](#operators)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Look-ahead](#look-ahead)

## Regex Components

### Quantifiers
Quantifiers set the limits of the string that your regex matches (or an individual section of the string). They often include the minimum and maximum number of characters that your regex is looking for. In our case the password has a minimun length of 8. In our example above, the **{8,}** specifies that the password must be at least 8 characters long. The **{1,}** in the expression checks to make sure there is at least 1 lowercase letter, 1 number, and 1 special character. The **{2,}** checks to see that there are at least 2 uppercase letters. If we wanted to limit how long the password could be we could do so this way **{8,20}**. This would make sure the password was at least 8 characters long but no more than 20 characters long.
### OR Operator
The OR Operator can be used to allow a user to search for alphanumeric characters represented within the bracket expression. The **|** is the OR Operator and allows you to search for **[a-z]|[0-9]**: [a-z] or [0-9]. This could be used in this example if we wanted to limit any of the requirements defined in the criteria.
### Operators
The "\*" operator matches zero or more characters. The "." operator matches any character as a wildcard. In our example **(?=(.*[A-Z]){2,})** the "." and "*" look to see if there are any uppercase letters at any of the positions in the string. 
### Character Classes
Character classes define sets of characters. In the example above, the "**.**" matches any character within the individual grouping constructs. There are other character classes but we are not using them in our example. **/d** Would match numbers 0 to 9 in Javascript. **\w** Matches any alphanumeric character from the basic Latin alphabet, including the underscore **(_)**. This class is equivalent to the bracket expression **[A-Za-z0-9_]. \s** Matches a single whitespace character, including tabs and line breaks. You can change these last three classes to perform an inverse match by capitalizing the letter character. An example would be **\D** matching a non-digit character.
### Grouping and Capturing
In order to segment requirements, grouping constructs are used with parentheses **()** in regex commands. The grouping construct captures that all lowercase, uppercase, numerals and special characters are accounted for at least once. In this grouping and subgrouping, **(?=(.*[a-z]){1,})** we are looking to see if there is at least 1 lowercase letter.
### Bracket Expressions
Bracket expressions allow for the use of complex strings and nested structures.
In the example above, the first bracket expression is the **[a-z]** the hyphen (-) indicates that it can be any lowercase letter in the alphabet from a to z. **[A-Z]** would indicate any uppercase letter in the alphabet from A to Z and **[0-9]** for numbers 0 to 9.
### Greedy and Lazy Match
A Greedy match looks for each position in the string using **+**. A Lazy match is the opposite and repeats the minimal number of times.
**(?=.*\d)** and **(?!.*\s)** are both examples of lazy matches.
### Look-ahead
The **?=** is a postivie look-ahead. The positive lookahead assertion makes sure that the string matches the pattern after the current position. This means that the captured match must be followed by whatever is within the parentheses but that part isn't captured. The example **(?=(.*[a-z]){1,})** means the match needs to be followed by zero or more characters and then a lowercase letter (but again that part isn't captured).
## Author
This tutorial was created by Emily Langworth. I love playing pickleball in my spare time when I am not working on my coding bootcamp or playing with my two young kids. Here is a link to my <a href="https://github.com/elangworth">GitHub</a> profile.
