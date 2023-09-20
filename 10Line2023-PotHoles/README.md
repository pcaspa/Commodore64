POTHOLES
=======

Written by Peter Caspari for the BASIC 10Liner Contest 2023.

Language: Commodore 64 Basic v2

Category: PUR-80


The game
----
Race the 60 second timer to see how far you can get.  Hitting potholes or the side of the track will slow you down.

With the compiled version I got 4.64KM 

The Compiled version uses the same BASIC Code with the following exception.
line 7:  D=D+0.75 rather than D=D+1.3
This adjusts the distance covered to accommodate the faster execution of the compiled version


Controls and play
--------

Use left and right on the joystick in port 2 to drive the car.  Fire to accelerate


Loading
-------

You can use any Commodore 64 emulator that works with *.d64 files, commonly used is VICE.

- In VICE:
	- Click: File -> Attach disk image -> Unit #8
	- Select: potholes.d64
	- Click: Open 

	LOAD"PH-BASIC",8 - for the BASIC version
	LOAD"PH-COMPILED",8 - for the COMPILED version
	
	RUN
	
	RUN Again to restart the game
 
On the real hardware, just load with:

	LOAD"PH-BASIC",8 - for the BASIC version
	LOAD"PH-COMPILED",8 - for the COMPILED version

	RUN
	
	RUN Again to restart the game
