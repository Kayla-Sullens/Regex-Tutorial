# Regular Expression Tutorial

The purpose of this tutorial is to explain what a regular expression is and how it can be used. A Regex (regular expression) can be used when a user is trying to match a specific character combination within a string, for example. This can then be used to validate something or to pull out certain information from a body of code. 

## Summary

The regular expression code that I will describe is below, and I will explain the various components and functionality of the code. This code can be used to match emails, such as validating if an email follows the correct format needed. Below is a Table of Contents for the different components that will be explained. 

Matching an Email - /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

Below are all of the components of the Regular Expression (Regex) for matching an email. Since a regex is considered a literal, the search pattern has to be wrapped in / characters.

### Anchors

The anchors of a Regex are what start and end it, which allows us to be able to look for a pattern that starts and ends with specific characters. Both ^ and & are anchors. For our Regex here, the anchors are the ^ and the $. So the beginning anchor is the ^, which means that we are looking for an email that begins with the characters that follow in the brackets in this part of the code ([a-z0-9_\.-]+). The ending anchor of $ signifies a string the ends with the characters that come right before it.

### Quantifiers

In a Regex, quantifiers set the limits of the string that your regex matches, either in part or as a whole. In the scope of our regex, we have a quanitifier {2,6} that comes right before our closing anchor $. Here, our quanitifier means that the regex is going to look for a string between 2-6 characters that will follow the . in the email. Since we are looking for a letter or letters in this part of our code .([a-z\.]{2,6})$, the quanitifier means that we are specifically looking for a string of 2-6 lower-case letters.

### OR Operator

The OR Operator is not present in our code, but it is noted by the | symbol.

### Character Classes

Character classes define a set of characters, where any one can occur in an input string to make a match. Coomon character classes are:

. This matches any character except the newline character (\n). 

\d This matches any Arabic numeral digit and is equivalent to the bracket expresion of [0-9].

\w Matches any alphanumeric character from the basic Latin alphabet, and includes the underscore symbol. We do not have this character class in our Regex.

\s Matches a single whitespace character, which include tabs and line breaks. We do not have this character class in our Regex.

The character class in our code is the \d in our bracket expression of [\da-z\.-]. This means it's looking for a matching any Arabic numeral digit after the @ symbol. 

### Flags

This Regex does not contain a flag, but there are a few flags that are used in other expressions. 

g - Global search. This means that the regex should be tested against all possible matches in a string.

i - Case-insensitive search. This means case should be ignored while searching for a mathc in a string. Regular expressions are typically case-sensitive, so this flag tells it not to be case-sensitive when looking for a match. 

m - Multi-line search. This means that a multi-line input string should be treated as multiple lines when looking for a match. 

### Grouping and Capturing

There are two primary categories of grouping contructs: capturing and non-capturing. In our Match an Email regex, we have three groups of characters that will make up the string. These groups are noted with parenthesis (), and each section in parenthesis are known as subexpressions. This way of grouping just means that we are looking for something different at each part of our expression. So for our code, we have 3 groups/parts:

([a-z0-9_\.-]+) For this section, we are looking for a range of characters that include lower-case letters a-z, numbers 0-9, or the listed symbols.

@([\da-z\.-]+) For this section, we are looking for a specific match in the letter range.

\.([a-z\.]{2,6}) For this section, we are looking for a range of lower-case letters a-z, that is between 2-6 characters long. 

### Bracket Expressions

Anytime we have a set of square brackets, [], it means there is a range of characters that we need to match. Brackets expressions show us the characters that we want to include. For our Matching an Email code, our first bracket expression is [a-z0-9_\.-] and it means we are looking for a string that contains a lower-case letter a-z, a number 0-9, and the symbols listed. These characters can be in any order, so the number could come before the letter and it would still be a match. Bracket expressions tell us what characters need to be included, but this only means the string needs to match any of these requirements and does not have to meet all of them. Based on our code, possible strings for this could be:

hello1
my-4-pets

The next bracket expresion in our code is [\da-z\.-] and this is checking for the characters that come after the @ symbol in an email. This piece of code would be looking for a string that contains a specific letter after the @ symbol, as it was explained in the character classes section above. It's purpose is to match an email so possible ones like:

@gmail

@yahoo

The third and final bracket expresion in our code is [a-z\.] and comes after the . in the email. This piece of code would be looking for lower-case letters that end the email. Examples of this could be:

.com

.net

The last important thing we need to know about bracket expressions is that they can be turned into a negative character group by adding the ^ symbol at the beginning of the expression that's contained in the brackets. What this does is look for strings that do not match the characters noted in the brackets. Our expresion doesn't contain this symbol so we are looking for strings that match what is in the brackets.

### Greedy and Lazy Match

Greedy and lazy matches can occur with quanitifiers. Since quanitifiers are inherently greedy, it means they can match as many occurrances of a particular pattern as it possibly can. Quantifiers include the following:

* This means the string needs to match the pattern zero or more times.

+ This means the string needs to match the pattern at least one time.

? This means the string needs to match the pattern zero or only once.

{} These provide three different wats to set limits for a match: matching a pattern exactly, matching a pattern at least a certain number of times, and matching a pattern for a range of times. 

Quantifiers can be made lazy by adding a ? after it, which means that it will match as few occurrances as possible instead of as many as possible. 

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

This tutorial was created by Kayla Sullens, a Math Educator turned Software Developer. I've been teaching Math in different capacities for 10+ years now, and I wanted to make a career change. I was always interested in coding in college, but never gave it a chance. Here we are and I couldn't be happier, especially since this feels a lot like a math lesson/tutorial. Please see my GitHub profile below.

GitHub Profile
