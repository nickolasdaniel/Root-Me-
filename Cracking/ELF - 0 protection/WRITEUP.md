# ELF - 0 protection
## 5 Points
This is a very easy challenge, especially if you have the right tool, such as IDA Pro.
So we have this binary file ```ch1.bin``` which appears to look like this if we open it in IDA:
![1](https://github.com/nickolasdaniel/Root-Me-/blob/master/Cracking/ELF%20-%200%20protection/photos/1.PNG)
The password is literally right there but we can see it in the decompilated C code since I use the PRO versison of IDA:
![2](https://github.com/nickolasdaniel/Root-Me-/blob/master/Cracking/ELF%20-%200%20protection/photos/2.PNG)

So as I said this was a easy challenge, with the password just being showed at first sight.
Password: __123456789__
