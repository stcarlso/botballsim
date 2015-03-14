# Frequently asked questions #

Questions commonly asked by new users of JBSim can be found here. Suggestions for items to add to the list should be added as an [issue](http://code.google.com/p/botballsim/issues/list).

  * **How do I load my code into the program through KISS-C?**

> KISS-C currently does not support direct code loading -- JBSim will not replace the "Simulate" button with one of its own. To run code on the simulated robot, launch JBSim and use the "Load Code" button.

  * **How do I rotate my robot using the Hand of God?**

> Right click and drag to indicate the direction that the robot should be pointing towards. Alternatively, Control-Click and drag.

  * **Clicking the Play button does not start code.**

> Make sure that code was loaded in the first place. Check the LCD screen for compile errors. If the button still shows the same icon, try clicking it again.

  * **Clicking the Play button freezes the simulator.**

> This is a known issue that is hard to consistently replicate. Try restarting the program. If the issue persists, please file it in the related [issue](http://code.google.com/p/botballsim/issues/list).

  * **Sensors are not working properly.**

> Digital sensors actuate when the center of the dot intercepts an obstacle. If the sensor is placed inside your robot's frame, the robot will collide before the sensor can ever fire. Try moving the sensor slightly outside the robot.
> Likewise, Distance (ET) sensors measure to the nearest obstacle, so try moving them outside of the robot. Color sensors do not suffer from this problem.

  * **The robot to be simulated looks very different from the available robots.**

> If the collision model is not drastically different, substituting a built-in design will still provide a good idea of how this robot might behave. See Creating a New Robot Design.

  * **Not all of the simulator is visible on the screen.**

> The program currently requires a high resolution (at least 1152x768) to be viewed in its entirety. Increase resolution if possible. Re-laying out the screen or moving some outputs around should fix this issue in the near future.

If your problem is not listed on this page, check the KnownIssues section as well.