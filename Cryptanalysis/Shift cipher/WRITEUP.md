# Shift cipher
## 10 Points

So this one was a bit harder than the previous ones, but still quite easy. So we're given a binary file which contains a weird encoded strings with weird looking characters: ```L|k.y+*^.*zo..*.kvsno|*k.om*vo*zk}}*cyvksr.``` We've been told that we need to rotate the characters in order to get the sentence that contains the flag. If we look with ```hexdump -C ch7.bin```:
![1](https://github.com/nickolasdaniel/Root-Me-/blob/master/Cryptanalysis/Shift%20cipher/photos/1.PNG)

we can see those ```*``` which look like spaces between words, so if we check ascii table:

![2](https://github.com/nickolasdaniel/Root-Me-/blob/master/Cryptanalysis/Shift%20cipher/photos/2.PNG)

So, if we shift the string to -10 ascii values maybe we can get the password right? So I've came up with this script in python:
![3](https://github.com/nickolasdaniel/Root-Me-/blob/master/Cryptanalysis/Shift%20cipher/photos/3.PNG)

I was right, check the output! The password is: __Yolaihu__

![4](https://github.com/nickolasdaniel/Root-Me-/blob/master/Cryptanalysis/Shift%20cipher/photos/4.PNG)

