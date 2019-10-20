---
title: "Command: grep cut awk"
date: 2019-10-16T00:42:57-04:00
draft: false
tags: ["software"]
categories: ["Linux"]
---


The three commands can be used to process the text/message. 
Usually, `grep` is used to filter lines containing the keyword. 
`cut` is used to output part of the line. 
`awk` is used to modify the lines. 


## grep

The common usage of `grep` to find `keyword` is as follows. 

```bash
fool@bar:~$ grep "keyword" ./file.txt
```

* `-n`: print the line number
* `-i`: ignore case distinctions
* `-w`: match whole the words
* `-o`: output only the matching segment, rather than the full line
* `-E`: use extended regular expression syntax
* `-C2`: show 2 context lines in addition to the matched line

## cut

The common usage of `cut` to split a line by spaces and select the first field is as follows. 

```bash
fool@bar:~$ cut -d " " -f 1 ./file.txt
```

* `-d " " -f 1, 2 ----output-delimiter='%'`: use space as delimiter and select the first and the second fields of each line and output with delimiter %. 
* `-b 1-5`: select the first to the fifth byte of each line
* `-c 1, 2`: select the first and the second character of each line


## awk

The common usage of `awk` to split a line containing the keyword by spaces and select the first field is as follows. 

```bash
fool@bar:~$ awk '/keyword/ {print $1}' ./file.txt
```


```bash
fool@bar:~$ awk '{print "newstring " $1,$4}' employee.txt 
```
