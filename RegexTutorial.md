# Regex Complex password strength guide/tutorial

This is a tutorial on how the Complex Password Strength regular expression works by explaining each of the concepts.

## Summary

Regex is short for regular expression, which is a way of identifying specific patterns. These patterns could be anything from code to search algorithms. Regular expressions can be used to find patterns in strings or replace characters in a pattern. Regex is also commonly used to validate inputs and each component of regex has a unique responsibility to perform the validation.

- With this walkthrough, we'll cover aspects of the Complex Password Strength regex, including one lowercase letter, one uppercase letter, one number, one special character, and at least 8 characters long.

- As an example a regex could look like either of these 
``` [b-chm-pP]at|ot
``` /(?=(.*[0-9]))(?=.*[\!@#$%^&*()\\[\]{}\-_+=~`|:;"'<>,./?])(?=.*[a-z])(?=(.*[A-Z]))(?=(.*)).{8,}/
```


## Table of Contents

- [Star and Dot](#star-and-dot)
- [Positive Lookahead](#positive-lookahead)
- [Capturing Groups](#capturing-groups)
- [Ranges and Character Classes](#ranges-and-character-classes)
- [Quantifiers](#quantifiers)
- [Character Escapes](#character-escapes)

## Regex Components

### Star and Dot

-A star ( * ) will match zero or more of the preceding token (this is also a quantifier).
-A dot ( . ) matches any character except line breaks
-Combined the dot and star can be repeated any number of times including zero and will prevent any line breaks (this combination is also known as a wildcard). A user will not be able to use "password" since it contains a line break.It is used in the password regex before all character classes. Additionally, it is preceded by a positive lookahead, which looks at the character set ahead of the .*, enabling the password regex to check for all characters within the set.

### Positive Lookahead

-With Lookaheads, conditions can be added to "what follows".This part of an expression will match for a pattern that is followed by another pattern. Any valid regular expression can be used inside the lookahead.The lookbehind is similar, but it looks behind(who could have figured).In other words, it allows matching of patterns only if there is something before the pattern.

### Capturing Groups

-Capturing groups are a way to represent multiple characters as a singular unit. You create captured groups by playing the characters to be grouped inside a set of parentheses. This allows it to get a part of the match as a separate item in the result array. This allows you to apply a quantifier to the whole group.

### Ranges and Character Classes

-By using a hyphen, ranges allows you to specify a range of characters. Regex engines are able to match a single character from a number of choices when using character classes, also called character sets.In our example, it matches characters in the range of numbers 0 through 9, lowercase letters a through z, and uppercase letters A through A. Character classes must be within bracket expressions.If there is a carat (^) inside a class or range it will exclude the characters that follow the carat (does not occure in this regex).

### Quantifiers

-Quantifiers indicate numbers of expressions or characters to match. In our quantifiler we have a ( , ) after the 8 that means it will match at least that many times instead of exactly 8 which would be the case if it was written without a comma. In the regex we used as an example it will match at least 8 occurrences of the preceding character which is a ( . ), so any character except for the line breaks. In the example regex our we have .{8,}

### Character Escapes

-Otherwise known as escaped characters, these can used to insert special, reserved, and unicode characters. Escaped characters begin with \. Also, you escape certain letters that represent common character classes, such as \w for a word character or \s for a space.This regex only uses escapes for special characters.

## Author

Hi thanks for reading. I'm Christian Gleason, a full stack web developer who is nearly done with my coding bootcamp with Upenn. My hope is in the near future to get a job in the field and keep learning.

Any questions, comments or concerns Email me at christian.gleason416@gmail.com
