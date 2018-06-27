# Hash - SHA-2
## 5 Points

Another hash: ```96719db60d8e3f498c98d94155e1296aac105ck4923290c89eeeb3ba26d3eef92```

This one is a SHA-2....or is it really SHA-2? Let's take a look with python.
![1](https://github.com/nickolasdaniel/Root-Me-/blob/master/Cryptanalysis/Hash%20-%20SHA-2/photos/1.PNG)
As you can see, this hash is 65 characters long. A SHA-2 hash should only have 64 characters since it has 256 bits and each digit is 4 bits. But why is it 65? It is very well known that hashes are made up of hexadecimal values which only contains numbers from ```0-9``` and characters from ```a-f``` and our hash contains a ```k```. So we'll have a SHA-2 hash only after removing the ```k``` from the hash.
Now we have this hash ```96719db60d8e3f498c98d94155e1296aac105c4923290c89eeeb3ba26d3eef92``` and we can crack it using ```https://crackstation.net/``` again.
The result as it can be seen below is: ```4dM1n```
![2](https://github.com/nickolasdaniel/Root-Me-/blob/master/Cryptanalysis/Hash%20-%20SHA-2/photos/2.PNG)
Now, the challenge asks for SHA-1 hash out of the given SHA-2, so all we have to do now, is to convert the result ```4dM1n``` to SHA-1.
We can do that using python:
![3](https://github.com/nickolasdaniel/Root-Me-/blob/master/Cryptanalysis/Hash%20-%20SHA-2/photos/3.PNG)
So the SHA1 (also the password of this for this challenge) of that SHA-2 result is: __a7c9d5a37201c08c5b7b156173bea5ec2063edf9__

