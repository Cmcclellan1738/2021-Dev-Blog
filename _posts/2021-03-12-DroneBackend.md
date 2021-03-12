---
title: Drone Backend
date: 2021-03-12
---

# Drone Backend Development
### Visual Studio Code
Visual Studio Code is a program we use to write code in java and follwoing gitflow, we can commit and push to github without even having to open github. VSC helps us understand our code more thoroughly and helps us format and prepare it to send to our drone. We can use VSC to set up a command line and various functions for operating our drone for our race.

### Tello Drone
Our Tello Drone is what we will be operating with VSC and can be very complex to write and execute code. Tello Drone has a set of very specific commands and indicators to tell you the state of the drone, the direction it is going, and even the speed. The Drone has been having problems connecting sometimes and will refuse to receive commands but we have successfully debugged most of our issues. We wrote a very simple sequence just to start since we are currently defining functions for our controls. Our drone in its current state once the code is executed will send "command", then takeoff, check battery level to make sure it is sufficient for flight, then go up 30, followed by a flip backwards, and finally it will land.
