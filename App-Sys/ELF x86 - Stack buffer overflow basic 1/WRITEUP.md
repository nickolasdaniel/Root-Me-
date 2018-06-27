# ELF x86 - Stack buffer overflow basic 1
## 5 Points

Source code:
```c
#include <stdlib.h>
#include <stdio.h>
 
/*
gcc -m32 -o ch13 ch13.c -fno-stack-protector
*/
 
 
int main()
{
 
  int var;
  int check = 0x04030201;
  char buf[40];
 
  fgets(buf,45,stdin);
 
  printf("\n[buf]: %s\n", buf);
  printf("[check] %p\n", check);
 
  if ((check != 0x04030201) && (check != 0xdeadbeef))
    printf ("\nYou are on the right way!\n");
 
  if (check == 0xdeadbeef)
   {
     printf("Yeah dude! You win!\nOpening your shell...\n");
     system("/bin/dash");
     printf("Shell closed! Bye.\n");
   }
   return 0;
}
```
Alright, so knowing the source code is already an important step on solving this challenge since we know which address is expected when we overflow the buffer, and also the size of the buffer is given. Okay so, we have to connect to the challenge through ssh which is given in the info ```ssh -p 2222 app-systeme-ch13@challenge02.root-me.org```
Once we are connected, we can use ```ls -a``` too see files and hidden files.
![1](https://github.com/nickolasdaniel/Root-Me-/blob/master/App-Sys/ELF%20x86%20-%20Stack%20buffer%20overflow%20basic%201/photos/1.PNG)
Okay, so we can see there is a ```.passwd``` file which contains our password besides the source code and the actual executable.
Now, if we try to display the password, it would say this:
![2](https://github.com/nickolasdaniel/Root-Me-/blob/master/App-Sys/ELF%20x86%20-%20Stack%20buffer%20overflow%20basic%201/photos/2.PNG)
It is expected tho, because we are not in a shell, so the task is to activate the shell.
We can do that by exploiting a mini command through python, to overflow the buffer and to write in the expected memory address. Alright, so we know the size of the buffer is 40 bytes, we write this first ```python -c 'print "A" * 40'```. Then we add the memory address, but careful because it's litle endian, that means we need to write te address like this ```\xef\xbe\xad\xde```. We now have the necessary information to exploit the payload.
![3](https://github.com/nickolasdaniel/Root-Me-/blob/master/App-Sys/ELF%20x86%20-%20Stack%20buffer%20overflow%20basic%201/photos/3.PNG)
Well, all good, but the shell is closing right after it had been opened. But no problem adding a simple ```;cat``` will solve our problem, so we now write the following:
![4](https://github.com/nickolasdaniel/Root-Me-/blob/master/App-Sys/ELF%20x86%20-%20Stack%20buffer%20overflow%20basic%201/photos/4.PNG)
So the challenge is solved. The only thing we have do to now is to display the password.
![5](https://github.com/nickolasdaniel/Root-Me-/blob/master/App-Sys/ELF%20x86%20-%20Stack%20buffer%20overflow%20basic%201/photos/5.PNG)
Great so the password is: __1w4ntm0r3pr0np1s__
