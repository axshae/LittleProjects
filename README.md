# Little Projects



[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

# P1: Piano using C++!
#### Copy the below code and run it in DOS BOX Turbo C++
```c++
/*
Author	  :	 Akshay
Created on:	 21-10-2018
Software  :  MS-DOS Turbo C++, windows 10 64bit
*/

#include<dos.h>
//note-1: above header file(dos.h) contains sound(),nosound() & delay() functions
#include<conio.h>
//note-2: conio.h contains getch() and clrscr() function
#include<stdio.h>
//note-3 stdio.h contains printf() function
void main(){
clrscr();		//clears the screen comes under conio.h header file
/*
getch() waits for user input and does not print anything on the screen
while getche() function also waits for user input but print whatever key user pressed
*/
printf("Start Playing piano (press esc to exit)");
int keyInput=getch();	//waits for first key input
while(keyInput!=27)	//ascii value of ESC is 27(How did i find it?ans:by printing keyInput)
{
		/*
				1. loop run until user does not press esc key
				2. whenever user press any other key a different sound is played as
				we know every key has its own ascii value
		*/

	sound(keyInput+50);	// this functions accepts a frequeny and plays it
	delay(100);// this function accepts the number of milliseconds it needs to play the sound
					// 1 sec =1000 ms
	nosound(); 	//this function turnsoff the speaker, it must be called everytime we dont need to play the sound
	keyInput=getch();				//everytime waits for new key input from user
}
}


```
  
### How its working?

1. Just imagine how a piano is played? 
	- You press any key and it plays some sound..simplee
	- and sound plays until you dont move your fingers up (maybe this is not the case in some pianos :p )
	
2. 	Now think what happens inside the paino when you press a key?
	- Well i don't know either :p
	- Nvm Just joking...
	- Each key have its own frequency so when you press it that frequency is played and pressing multiple keys one after other creates a melody

3. But how paino plays that frequency assigned to keys?
	- There must be some computer program having a function (like ours sound()) which accepts a frequency and plays the sound
	- In our case we have sound() function which accepts a frequency value and plays the sound like sound(7) means play a sound of 7Hz

4. Okay now tell me your logic to build a piano?
	- hmmm
	- well its pretty easy peasy...
	- Steps:
	1. wait for a input from the user i.e. wait for user to press any key
	2. the moment user press any key start an infinte loop that will only end if esc is pressed
	3. from pressed key you will get a unique ascii value
	4. pass that ascii value to sound() function 
	5. now tell the program how long to play the sound by using delay() function
	6. then turnoff the speaker y nosound() function
	7. again goto step 1
	8. easy right

5. Nothing more. Just start coding and enjoy. ;) 	

