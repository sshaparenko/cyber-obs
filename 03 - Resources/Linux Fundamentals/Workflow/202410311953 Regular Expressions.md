---
date: 2024-10-31T19:53
tags:
  - "#cybersecurity"
  - "#linux"
cssclasses:
  - pen-purple
  - page-grid
---
A Regex is a sequence of letters and symbols that form a search pattern. In addition, regular expressions can be created with patterns called meta characters.

Meta characters are symbols that define the search pattern but have no literal meaning.

We can use it in tools like `grep` or `sed` or others. Often regex is implemented in web applications for the validation of user input

#### Grouping
***
Among other things, regex offers us the possibility to group the desired search patterns. Basically, regex follows three different concepts which are distinguished by three different brackets:

| Operations | Descriptions                                                                                                                                                               |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `(a)`      | The round brackets are used to group parts of a regex. Within the brackets, you can define further patterns which should be processed together                             |
| `[a-z]`    | The square brackets are used to define character classes. Inside the brackets, you can specify a list of characters to search for.                                         |
| `{1, 10}`  | The curly brackets are used to define quantifiers. Inside the brackets, you can specify a number or a range that indicates how often a previous pattern should be repeated |
| \|         | Also called OR operator and shows the results when one of the two expressions matches                                                                                      |
| `.*`       | Also called the AND operator and displayed results only if both expressions match                                                                                          |
