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
`file ./-*` displays the file type of all files.
Password for next level is `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`.

## Level 5 -> 6
The password for the next level is stored in a file somewhere under the *inhere* directory and has all of the following properties:
-human-readable
-1033 bytes in size
-not executable
```
$ ssh bandit5@bandit.labs.overthewire.org -p 2220
$ cd inhere
$ find -type f -size 1033c
    ./maybehere07/.file2
$ cat ./maybehere07/.file2
```
`find -type f -size 1033c` this finds the files with size 1033 bytes.
Password for next level is `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`.

## Level 6 -> 7
The password for the next level is stored *somewhere on the server* and has all of the following properties:
-owned by user bandit7
-owned by group bandit6
-33 bytes in size
```
$ ssh bandit6@bandit.labs.overthewire.org -p 2220
$ find / -user bandit7 -group bandit6 -size 33c 2>&1 | grep -F -v Permission | grep -F -v directory
    /var/lib/dpkg/info/bandit7.password
$ cat /var/lib/dpkg/info/bandit7.password
```
Password for the next level is `z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S`.

## Level 7 -> 8
The password for the next level is stored in the file data.txt next to the word millionth.
```
$ ssh bandit7@bandit.labs.overthewire.org -p 2220
$ cat data.txt | grep millionth
    millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
Password for the next level is `TESKZC0XvTetK0S9xNwm25STk5iWrBvP`.

## Level 8 -> 9
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.
```
$ ssh bandit8@bandit.labs.overthewire.org -p 2220
$ cat data.txt | sort | uniq -u
```
Password for the next level is `EN632PlfYiZbn3PhVK3XOGSlNInNE00t`.

## Level 9 -> 10
The password for the next level is stored in the file *data.txt* in one of the few human-readable strings, preceded by several *=* characters.
```
$ ssh bandit9@bandit.labs.overthewire.org -p 2220
$ strings data.txt | grep "="
    dS=5
    f========== theM
    =XeOh
    =vb`
    O=Nq
    =I6a
    ========== password
    ========== is
    2\:=
    u=]T
    %AM_9=
    1~=y
    Q=9(
    j=GD
    b=fF
    0?F=(
    .DX_/=
    ========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
Password for the next level is `G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s`.

## Level 10 -> 11
The password for the next level is stored in the file *data.txt*, which contains base64 encoded data.
```
$ ssh bandit10@bandit.labs.overthewire.org -p 2220
$ cat data.txt | base64 --decode
    The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```
Password for the next level is `6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM`.

## Level 11 -> 12
The password for the next level is stored in the file *data.txt*, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.
```
$ ssh bandit11@bandit.labs.overthewire.org -p 2220
$ cat data.txt | tr 'a-zA-Z' 'n-za-mN-ZA-N'
    The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```
The password is `JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv`.

## Level 12 -> 13
The password for the next level is stored in the file *data.txt*, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under `/tmp` in which you can work using `mkdir`. For example: `mkdir /tmp/myname123`. Then copy the datafile using `cp`, and rename it using `mv` (read the manpages!)
```
$ ssh bandit11@bandit.labs.overthewire.org -p 2220

```