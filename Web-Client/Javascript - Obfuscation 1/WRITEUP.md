# Javascript - Obfuscation 1
## 10 Points

We have another alert box, but it is pointless as we have the script in the ```Inspect Element``` section:

![1](https://github.com/nickolasdaniel/Root-Me-/blob/master/Web-Client/Javascript%20-%20Obfuscation%201/photos/1.png)

As the challenge says, the password is obfuscated, but the solution is right under our nose because it compares with the output of the ```unescape('%63%70%61%73%62%69%65%6e%64%75%72%70%61%73%73%77%6f%72%64');``` function.

Now if we use the console, we can see the password: ```cpasbiendurpassword```.

![2](https://github.com/nickolasdaniel/Root-Me-/blob/master/Web-Client/Javascript%20-%20Obfuscation%201/photos/2.png)
