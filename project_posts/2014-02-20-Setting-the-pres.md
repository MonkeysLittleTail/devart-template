The idea to synchronize the cameras is to use LED lights that flash in a constant rhythm, stroboscopes.

![Flash](project_images/flash.gif?raw=true "Flash")

As a example, let's say we have a 4/4 compass in which we have 4 lights. 
So when the cameras are processing the images, if one of them, let's say camera 2 is in compass 2 (2/4), 
but camera 1 is in compass 1 (1/4) with a delayed frame, what is going to happen is that the code 
is going to make the camera 2 ignore the immediate next beat (3) and hold its position, i.e. compass 2/4. 



The code would then be:

 onUpdate( ){
	if(camera1.position == camera2.position){
		camera1.position++;
		camera2.position++;
	}else if(camera1.position > camera2.position ) {
		camera2.position++;
	} else {
		camera1.position++;
	}
}

This example is not going to be useful if the delay happens in a whole cycle. 
However we don't believe that the cameras are going to be so desynchronized. 
To prevent that, the cycles have to be bigger, i.e., more strobes.


![Sketch](project_images/10.jpg?raw=true "Sketch")