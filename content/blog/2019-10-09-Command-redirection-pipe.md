---
title: "Command: redirection and pipe"
date: 2019-10-09T00:42:57-04:00
draft: false
tags: ["software"]
categories: ["Linux"]
---



Every program running on the command line has three data streams connected to it.

* STDIN (0) - Standard input (keyboard for example)
* STDOUT (1) - Standard output (defaults to the terminal)
* STDERR (2) - Standard error (for error messages, defaults to the terminal)

The program usually gets its arguments from STDIN and outputs messages to STDOUT. The error messages will be output to STDERR. Redirection and pipe can be used to change the source of the argument or the destination of the output message. 


## STDOUT Redirection 

STDOUT redirection can be used to save the output of a program to a file instead of STDOUT (printing it on the terminal). The basic usage is 

```bash
fool@bar:~$ command > result.txt
```

The output message of `command` will be save to `result.txt`. It should be noted `result.txt` will be created if it doesn't exist and its content will be erased if it is not empty. `>>` can be used if the content of `result.txt` needs to be kept. 

## STDERR Redirection 

STDERR redirection can be used to save the error message of a program to a file instead of STDERR. The basic usage is 

```bash
fool@bar:~$ command 2> error.log
```

The error message of `command` will be save to `error.log`.

## STDIN Redirection


STDIN redirection can be used to send the program some arguments. The basic usage is 

```bash
fool@bar:~$ command < parameter.txt
```

The content of `command` will be sent to `command`. 



## Pipe

`pipe` takes the `STDOUT` of a command and pass it to the `STDIN` of the next command. The basic usuage is 

```bash
fool@bar:~$ command 1 | command 2
```

Here are some useful case of pipe. 


* count number of files

```bash
fool@bar:~$ ls | wc -l
```

* obtain the 5th and 6th file. 

```bash
fool@bar:~$ ls | head -n6 | tail -n2
```

* find the keyword

```bash
fool@bar:~$ cat file | grep "keyword"
```

* sort and find the unique value

```bash
fool@bar:~$ cat file | sort | uniq
```
