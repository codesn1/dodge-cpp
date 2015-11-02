# DODGE.cpp

Want to annoy people? Me too. That's why I wrote `DODGE.cpp`. Put this code snippet literally anywhere and it will run a console dodge game upon program start!

![alt tag](https://raw.githubusercontent.com/codesn1/dodge-cpp/master/kitten.jpg)

Oh, sorry. Wrong screenshot....

![alt tag](https://raw.githubusercontent.com/codesn1/dodge-cpp/master/screenshot.png)

And here's the snippet:

	#include <time.h>    /* DODGE.cpp                                             */
	#include <termios.h> /*           -- Oliver Katz @olivettikatz                */
	int _______________________dodge(){srand(time((time_t*)0x0000000));char b[7][9]=
	{"        ",  //
	 "        ",  //               _____      ___   ___ 
	 "        ",  //             / __\ \    / /_\ / __|
	 "*      ^",  //             \__ \\ \/\/ / _ \ (_ |
	 "        ",  //             |___/ \_/\_/_/ \_\___|
	 "        ",  //
	 "        "}; //
	termios o, n;tcgetattr(0, &o);n = o;n.c_lflag&=0xfffffeff;tcsetattr(0,0,&n);int
	a=0;while(1){printf("\033[2J\033[H"

	                              "DODGE THE ROCKS!\n"
	                           "PRESS A AND D TO MOVE!\n==="

	"===========\n");if(rand()%100>85)b[rand()%7][0]='*';int f=0;for(int j=0;j<8;j++
	){for(int i=0;i<7;i++){if(b[i][j]=='^'){printf("^");f=1;if(a=='d'&&i+1<7){b[i][j
	]=' ';b[i+1][j]='b';}else if(a=='a'&&i-1>=0){b[i][j]=' ';b[i-1][j]='b';}}else if
	(b[i][j]=='*'){printf("* ");b[i][j]=' ';if(j+1<8){b[i][j+1]='a';}}else if(b[i][j
	]=='a'){b[i][j]='*';printf("  ");}else if(b[i][j]=='b'){b[i][j]='^';printf("  ")
	;f=1;}else{printf("  ");}}printf("\n");}printf("==============\n");if(!f){printf
	("GAME OVER!\n");break;}timeval t;fd_set s;t.tv_sec=0;t.tv_usec=100000;FD_ZERO(&
	s);FD_SET(0,&s);select(1,&s,NULL,NULL,&t);if(FD_ISSET(0,&s))a=getchar();else a=0
	;}tcsetattr(0,0,&o);return 0;}const int __dodgee=_______________________dodge();

See? Swag!

# Dependencies

`#include <iostream>`

# Support

Basically untested on anything but my Mac.

# Special Thanks

...