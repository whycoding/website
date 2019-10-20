---
title: "Command: diff"
date: 2019-09-23T00:42:57-04:00
draft: false
tags: ["software"]
categories: ["Linux"]
---


`diff` command can be used to analyze two files and output the lines that are different. It also can output a patch file which can be used to make one file be identical to the other. 

## Basic Usage

```bash
fool@bar:~$ diff file1 file2
```

Here are some very useful options. 

* `-b`: ignore changes in the amount of white space
* `-B`: ignore changes whose lines are all blank
* `-w`: ignore all spaces


## Output Format

The basic usage only outputs the different lines. The context of the different lines can also be output by using `-c` or `-u`.

* `-c`: context mode, output 3 lines context for both files
* `-u`: unified mode, output 3 lines context only once

The result can be output side by side by `-y` option. There are two additional options in side by side mode. 

* `--left-column` option prints only the left column of two common lines.
* `--suppress-common-lines` option suppresses common lines entirely.

## Create Editing Scripts

The output of `diff` can be used by the editing program `patch` to modify the contents of file1, so that it matches the contents of file2. 

```bash
fool@bar:~$ diff file1 file2 > patchfile.patch
fool@bar:~$ patch file1 -i patchfile.patch -o updatedfile
```

The patch file can also be used to reverse the change. 

```bash
fool@bar:~$ patch updatedfile -R -i patchfile.patch -o newName
```

For two versions of a large project, the directories can be compared. 

```bash
fool@bar:~$ diff -r dir1 dir2 > patchfile.patch
fool@bar:~$ patch -p0 -i patchfile.patch
fool@bar:~$ patch -p0 -R -i patchfile.patch
```



Reference

[computerhope](https://www.computerhope.com/unix/udiff.htm)
[linuxacademy](https://linuxacademy.com/blog/linux/introduction-using-diff-and-patch/)