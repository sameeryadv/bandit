# OverTheWire Bandit

The Bandit wargame is aimed at absolute beginners. It will teach the basics needed to be able to play other wargames. Read more at [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)

## Level 0
In this level we have to connect to server using `bandit0` as user and `bandit0` as password.
```
$ ssh bandit0@bandit.labs.overthewire.org -p 2220
```

## Level 0 -> 1
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into `bandit1` using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
```
$ cat readme
```
Password we get is `NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL`. Now type `exit` to exit this level.

## Level 1 -> 2
The password for the next level is stored in a file called *-* located in the home directory.
```
$ ssh bandit1@bandit.labs.overthewire.org -p 2220
$ cat ./-
```
Password for next level is `rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`.

## Level 2 -> 3
The password for the next level is stored in a file called *spaces in this filename* located in the home directory.
```
$ ssh bandit2@bandit.labs.overthewire.org -p 2220
$ cat spaces\ in\ this\ filename
```
Password for next level is `aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG`.

## Level 3 -> 4
The password for the next level is stored in a hidden file in the *inhere* directory.
```
$ ssh bandit3@bandit.labs.overthewire.org -p 2220
$ ls
$cd inhere
$cat .hidden
```
Password for next level is `2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe`.

## Level 4 -> 5
The password for the next level is stored in the only human-readable file in the *inhere* directory. Tip: if your terminal is messed up, try the `reset` command.

```
$ ssh bandit4@bandit.labs.overthewire.org -p 2220
$ cd inhere/
$ ls
    -file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
$ file ./-*
    ./-file00: data
    ./-file01: data
    ./-file02: data
    ./-file03: data
    ./-file04: data
    ./-file05: Non-ISO extended-ASCII text, with NEL line terminators
    ./-file06: Non-ISO extended-ASCII text, with no line terminators, with escape sequences
    ./-file07: ASCII text
    ./-file08: data
    ./-file09: data
$ cat ./-file07
```
Password for next level is `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`.