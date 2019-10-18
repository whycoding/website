---
title: "Regular Expression"
date: 2019-10-01T00:42:57-04:00
draft: false
tags: ["software"]
categories: ["Linux"]
---



## Regular Expression 

* Character Classes`[0123456789]`. It matches any single character in that list. 
    * `[^0123]` any character not in the list.  
    * `[a-d]` equivalent to `[abcd]`.  
    * Predefined expressions, `[:alnum:]`, `[:alpha:]`, `[:digit:]`, `[:lower:]`, `[:punct:]`, `[:space:]`, `[:upper:]`


* Special Expressions
    * `.` any single character
    * `\s` any white space (spaces, tab and new line), `\S` any non white space
    * `\d` any digits, `\D` any non-digits
    * `\w` any word characters (letters, digits and underscore), any non-word

* Anchoring
    * `^exp` a line begin with exp. 
    * `exp$` a line end with exp.
    * `\<exp` a word begin with exp.
    * `exp\>` a word end with exp. `\<c...h\>`

* Repetition
    * `a?`      The preceding item is optional and matched at most once.
    * `a*`      The preceding item will be matched zero or more times.
    * `a+`      The preceding item will be matched one or more times.
    * `a{n}`    The preceding item is matched exactly n times.
    * `a{n,m}`   The preceding item is matched at least n and at most m times.

       

* Back References and Sub-expressions
    * `(exp)` enclosed in parentheses may be referred to later in the expression.
    * `\1` the substring previously matched by the 1st parenthesized sub-expression


* Alternation
    * `(a|b)` a or b


## Example

* find two lines with the same precedent and different suffixes. 

    ([\w-]*).cc[│\s]*\1.h

## Useful site

https://regexr.com/
