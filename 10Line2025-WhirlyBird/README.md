
BASIC Tenliners Contest 2025

Whirlybird 10Liner

email: peterc@bizzwerx.com.au

Whirlybird 10Liner is a variation of the classic flappy bird game

Task and Goal
=============
Fly the helicopter through the gap in the wall


Control:
========
Any key will increase the height of the helicopter



Game Requirements:
==================
- Standard C64 original hardware or emulator
- 1 Player


Starting in VICE: C64 emulator (http://vice-emu.sourceforge.net/):
==================================================================
Start the emulator and then drag and drop the "whirlybird.prg" into the VICE window.
-or-
Load the program with the command: load "whirlybird.prg",8
Then start the program with:       run


Whirlybird BASIC program code:
==============================
0s$="aaahpphppacaacaipiloepocpobpoblobjobappapoaieaieaifhpphpoaaaaaa":?"{clear}{white}wait"
1v=53248:pOv+39,7:pOv+32,14:pOv+33,14:pOv+21,1:fOc=1to63:d=aS(mI(s$,c,1))-65:r=0
2fOi=3to0step-1:b=(dand2^i)<>0:r=r*4+2*b:nE:pOc+12287,r*-1:nE:i$=" "+cH(20)+"{down}"
3fOt=1to23:j$=j$+i$:nE:p$="{down}{left*3}{reverse on}{space*2}{down}{left*2}--{down}{left*2}{space*2}{right}":g$="{down*8}":q$=p$+g$+p$
4p$(0)=q$+p$+p$+p$:p$(1)=p$+q$+p$+p$:p$(2)=p$+p$+q$+p$:p$(3)=p$+p$+p$+q$:h=30
5pO53276,1:pO53286,7:x=150:y=130:pOv+1,y:pOv+31,0:s=0:e=0:a=0:f=20:ifu>htHh=u-1
6pO2040,192:print"{home}{white}hi score"h"  score"s"{black}":?p$(int(rnd(1)*4));:s=s+1:f=f-0.1
7a=a+2-aB(sG(pE(197)-64))*5:y=y+a:ify>230tHforz=1to74:pOv+32,z/5:nE:?"{clear}":u=s:gO5
8pOv,x:pOv+1,y:ifpE(v+31)=1thenforz=1to74:pO53280,z/5:nE:?"{clear}":u=s:goto5
9print"{home}{down}"j$"{home}":e=e+1:onint(s-e/f)*-1+1goto7,6

This code is from CBM prg Studio (http://www.ajordison.co.uk/).


Whirlybird explained 
========================================================
0s$="aaahpphppacaacaipiloepocpobpoblobjobappapoaieaieaifhpphpoaaaaaa":?"{clear}{white}wait"
' Initializes a string with encoded sprite data and prints a clear screen + "wait"
' The sprite is multicolor but only 1 colour is used.  

1v=53248:pOv+39,7:pOv+32,14:pOv+33,14:pOv+21,1:fOc=1to63:d=aS(mI(s$,c,1))-65:r=0
' Sets VIC base address and initializes screen color and border registers; begins loop to decode data

2fOi=3to0step-1:b=(dand2^i)<>0:r=r*4+2*b:nE:pOc+12287,r*-1:nE:i$=" "+cH(20)+"{down}"
' Converts each character to a series of bits and builds graphical data; 4 bit data is converted to 8 bit data.

3fOt=1to23:j$=j$+i$:nE:p$="{down}{left*3}{reverse on}{space*2}{down}{left*2}--{down}{left*2}{space*2}{right}":g$="{down*8}":q$=p$+g$+p$
' Constructs j$ which shifts the display to the left and sets up the wall with the gap

4p$(0)=q$+p$+p$+p$:p$(1)=p$+q$+p$+p$:p$(2)=p$+p$+q$+p$:p$(3)=p$+p$+p$+q$:h=35
' Defines variations of the wall with the gap in different positions stored in p$() array; sets current high score set by my son Jake

5pO53276,1:pO53286,7:x=150:y=130:pOv+1,y:pOv+31,0:s=0:e=0:a=0:f=20:ifu>htHh=u-1
' Initializes sprite settings, sprite coordinates, set/reset game variables score, acceleration and gap between walls, updates high score

6pO2040,192:print"{home}{white}hi score"h"  score"s"{black}":?p$(int(rnd(1)*4));:s=s+1:f=f-0.1
' Assigns sprite graphic, prints scores and game layout, updates score and decreases gap between walls

7a=a+2-aB(sG(pE(197)-64))*5:y=y+a:ify>230tHforz=1to74:pOv+32,z/5:nE:?"{clear}":u=s:gO5
' Adjusts vertical position based on joystick input; if hit the ground, end game and restart

8pOv,x:pOv+1,y:ifpE(v+31)=1thenforz=1to74:pO53280,z/5:nE:?"{clear}":u=s:goto5
' Draws sprite at current position; checks for collision and ends game if collision detected

9print"{home}{down}"j$"{home}":e=e+1:onint(s-e/f)*-1+1goto7,6
' Scrolls the screen and controls game loop based on if another wall is to be rendered
