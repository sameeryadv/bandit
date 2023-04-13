# OverTheWire Bandit

The Bandit wargame is aimed at absolute beginners. It will teach the basics needed to be able to play other wargames. Read more at [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)

## Level 0
In this level we have to connect to server using `bandit0` as user and `bandit0` as password.
```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

Password for next level is written in `readme` file. Password we get is `NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL`.

## Level 1

We will login to `bandit1`. The password for the next level is stored in a file called *-* located in the home directory.
```
cat ./-
```
Password for next level is `rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`.

## Level 2
We will login to `bandit2` using above password. The password for the next level is stored in a file called *spaces in this filename* located in the home directory.
