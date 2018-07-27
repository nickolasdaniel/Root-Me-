# Javascript - Obfuscation 2
## 10 Points

We are given a blank html page which if we inspect the source with ```Ctrl + U``` we can see:

![1](https://github.com/nickolasdaniel/Root-Me-/blob/master/Web-Client/Javascript%20-%20Obfuscation%202/photos/1.png)

Wwe only have a variable which looks pretty awful: ```unescape("unescape%28%22String.fromCharCode%2528104%252C68%252C117%252C102%252C106%252C100%252C107%252C105%252C49%252C53%252C54%2529%22%29");```

But it isn't as bad as it seems because basically what this does, is it is unescaping and unescaped string as follows:

![2](https://github.com/nickolasdaniel/Root-Me-/blob/master/Web-Client/Javascript%20-%20Obfuscation%202/photos/2.png)

But be careful, because you have to modify those ```%28%22``` into ```("``` because those are the corresponding characters to those codes, and besides, it even makes more sense. 

Now the only thing left do to is to put this ```String.fromCharCode(104,68,117,102,106,100,107,105,49,53,54)``` in console: 

![3](https://github.com/nickolasdaniel/Root-Me-/blob/master/Web-Client/Javascript%20-%20Obfuscation%202/photos/3.png)

So the password is: **hDufjdki156**.

