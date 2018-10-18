# Adding-scissor-lift-Kinematics-to-Marlin
Author Bartolobot 
10/18/2018 
 
 looking to add a new type of Kinematics to marlin for a 3D printer(The Bartolobot 1300X) with a Scissor lift-like mechanism as the Z axis. Where the actual stepper motor moving the Hot end up & down (in my case the bed is fixed), Is set at 90' deg. from the actual Z-axis direction (it lay flat under the bed with an ACME lead screw) And moves a single stage scissor lift mechanism (Essentially it's an "X" frame on each side liked together and they pivot in the center point of the "X" Two tip ends of each "X" are fixed and the other two are free to move within a slot Connected to the Acme screw through a nut and linkage) Heres Where the issue lies the Z motor travel does not translate into an equal amount of lift at the hot end. At the bottom of my Z axis (Start Position) the actual displacement inferred from the motor is at its greatest. And progressively continues to decrease with every step. So at the start, the move is bigger than the motor move, At the middle, it's about equal, and towards the top max, it's much smaller than the motor move.
 
 Thus my Z steps need to be Proportional to the Z position. The calculation can be done with Pythagorean theorem a² + b² = c'² 
 As far as position goes I don't think A feedback sensor is necessary. Just like any other printer once homing is done the position is known, if the math is right and no steps are lost then the position should be understood.
 
 some suggestions from thinkyhead, Anhardt, & Palatis have been made. I have been slow to learn but I am new to Github as a contributor 
 I can't say I'm new to coding or python but I have much to learn.
 
 Anhardt: Suggested I use a preprocessor or a python script

  "Instead of modifying Marlin, think about a preprocessor.
A, for example, python script, reading in your g-code, searching the z-values, modifying them with your formula and writing them back to another file.
Usually, this is much more time efficient (for you) than a proper integration of a new cinematic into Marlin.
DELTA, SCARA, COREXY all begun that way."

Palatis: agrees with my idea of a new kinematics

Thinkyhead: points out possible similarities to Kurt Russell, in Kappa
    
    " …like a scissor lift…

Is it similar at all to the Scott Russell Linkage as used in the Kappa?"
