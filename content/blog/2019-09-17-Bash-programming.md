---
title: "Basic Shell Programming"
date: 2019-09-17T00:42:57-04:00
draft: false
tags: ["shell"]
categories: ["Linux"]
---

## Introduction

`Shell` provides users an interface to interact with the operating system. It interprets the shell script and handles the output from the operating system. 

In fact, shell itself is an application. The most common shell in UNIX-like system is `bash`. Another popular shell is `zsh` with enhanced functions. For SSL telnet connection, the `ssh` shell is usually used. 


## Header

The shell script can be run by using

```bash
bash script-name
```

You can replace *bash* with any shell you want. However, usually the shell scrip start with an directive statement, so that it can be run without specifing the shell name again. 

```bash
#!/bin/bash
```

It should be noted that other than the first line, lines start with `#` are comment lines. 


## Variable

Shell variables are created once they are assigned a value. 

* Value assignment is done using the `=` sign. No space permitted when initializing variables.

* Variables are used by `$`. Usually use `${var}` to avoid ambiguity.

## Script argument

Arguments can be passed to the script when it is executed. 

Inside the script, the $1 variable references the first argument in the command line, $2 the second argument and so forth. The variable $0 references to the current script. 

## Statement

* Command

    Variables can be assigned with the value of a command output. `var=$(command)`

* Perform arithmetic operations

    $((expression))

    ans=$(( x + y ))

## Condition control

```bash
if [ condition ]; then
  statement
elif [ condition ]; then
  statement
else
  statement
fi
```

## Loop


```bash
for var in 1 2 3 4 5
do
    echo $var
done
```

Other kinds of for loops

```bash
for output in $(command)
for var in {1..5}
for var in {0..10..2}
for (( c=1; c<=5; c++ ))
```

`break` and `continue` can be used inside the loop

## Function

```
function_name {
  command
}
```

Do not have to specity the number of arguments

## Output Input

printf "%s: %d\n" "a string" 12