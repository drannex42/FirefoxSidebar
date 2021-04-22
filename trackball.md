# Trackballs 
A selection of scripts to enhance trackball configs

## All Tracksballs 

On Linux (X Servers) you can easily change the sensitivty with the follow script, the first number is sensitivity and the second is the accceleration, the acceleration is how fast it will speed up to be.

By default, the pointer (the on-screen representation of the pointing device) goes "acceleration" times as fast when the device travels more than "threshold" "mickeys" (i.e., would-be pixels) in 10 ms, including a small transition range. This way, the pointing device can be used for precise alignment when it is moved slowly, yet it can be set to travel across the screen in a flick of the wrist when desired. One or both parameters for the m option can be omitted, but if only one is given, it will be interpreted as the acceleration. If no parameters or the flag 'default' is used, the system defaults will be set.

If the "threshold" parameter is provided and is 0, the "acceleration" parameter will be used in the exponent of a more natural and continuous formula, giving precise control for slow motion but big reach for fast motion, and a progressive transition for motions between. Recommended "acceleration" value in this case is 3/2 to 3, but not limited to that range.

```xset m 5 10```
