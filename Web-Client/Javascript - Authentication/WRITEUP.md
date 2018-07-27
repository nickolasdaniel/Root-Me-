# Javascript - Authentication
## 5 Points

We have another form and we have to find the account in order to bypass it and get the password. If we inspect the page we have see this:

![1](https://github.com/nickolasdaniel/Root-Me-/blob/master/Web-Client/Javascript%20-%20Authentication/photos/1.png)

So now we know we have a script file called ```login.js```. If we access that javascript file through url like so:

![2](https://github.com/nickolasdaniel/Root-Me-/blob/master/Web-Client/Javascript%20-%20Authentication/photos/2.png)

We are given the following output:

![3](https://github.com/nickolasdaniel/Root-Me-/blob/master/Web-Client/Javascript%20-%20Authentication/photos/3.png)

It's simple now as it's comparing the username with ```4dm1n``` and the password with ```sh.org```. So as it can be seen in the script, we can validate the challenge using the password ```sh.org```.
