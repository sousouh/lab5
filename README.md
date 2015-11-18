# lab5
### Lab class 5, Structs &amp; Stringstreams 


Today's problem is to calculate statistics for 2D diffusion of colloids which perform random-walk motion. Consider *N* colloids which start at *x=0* and *y=0*. Now we want to push them in total *Nsteps* randomly in *+/-* direction for both *x* and *y*. The three options "moving in negative direction", "moving in positive direction" and "resting" should be drafted with equal probability.

The structure of the preexisting code is the following: We dynamically allocate a pointer to *N* colloids and two integer pointers *rx* and *ry* with respective size, in which the moving events get stored. We split the iteration over *Nsteps* into two for-loops since after every *Nsubsteps* iterations we want all colloid positions to be printed out. Furthermore we write the mean positions in *x* and *y* and the variance after every step into an extra file called ***statistics.dat***. In the end we close all open files and delete the dynamically allocated memory.

The **init** and **print** function as well as the **stringstream** structure are pre-written in ***randomwalk.cxx***. You have four tasks

 * Get familiar with the structure of the code

 * Write a **conditions** function which sets the movement direction for ***ALL*** colloids at once into *rx* and *ry*, respectively

 * Write a **pusher** function which pushes all colloids at once by the value of *step* into the direction stored in the respective *rx* and *ry* array

 * Write a **statistics** function which calculates (and overwrites) *meanx*, *meany* and *var*, thus mean positions and variance

Note that we expect the variance *var* to increase **linearly** in time as we investigate diffusion. You can plot all your output files at once by writing ***plot for [i=0:10] 'rwalk_'.i.'.dat' w p*** in gnuplot. Try to use **const** as often as possible in order to prevent variables from changing unintentionally.
