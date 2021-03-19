---
title: Drone Backend Development
date: 2021-03-19
---

# Drone Backend Development

### Visual Studio Code
Visual Studio Code (VSC) is a program we use to write code in java and following gitflow, we can commit and push to github without even having to open github. VSC helps us understand our code more thoroughly and helps us format and prepare it to send to our drone. We can use VSC to set up a command line and various functions for operating our drone for our race.

### Tello Drone
Our Tello Drone is what we will be operating with VSC and can be very complex to write and execute code. Tello Drone has a set of very specific commands and indicators to tell you the state of the drone, the direction it is going, and even the speed. 

The Drone has been having problems connecting sometimes and will refuse to receive commands but we have successfully debugged most of our issues. We wrote a very simple sequence just to start since we are currently defining functions for our controls. 

Our drone in its current state once the code is executed will send "command", then "takeoff", check battery level with "battery?" to make sure it is sufficient for flight, then "up 30", followed by "flip b" which will make the drone flip backwards, and finally we send the command "land" which is pretty self explanitory.

### Problems With Drone Development
So far we have had quite a few issues with getting the drone to read and respond to our code. We have currently been working through defining the directional movement and trying to get the drone to act upon sending such code. It seems like everytime we add something new we also add a new problem but we usually think through and rationalize it enough to see what the issues are. 

Currently we are attempting to have the program prompt the user and ask for a command to run and then run the command that is tied to that input. Directional movements like left, right, up, and down are seeming to be difficult since they also have a numerical value to enter which we cant neccessarily define.

### Ours Success So Far
So far we have gotten the user prompt to work with commands such as takeoff, emergency, and land. We attempted to try the directional movements mentioned above but we still are working through how to also prompt the user for a number that follows the desired direction. 

The following code is a switch function which is used to basically run a different command based on different inputs. For example, if we were to type in "takeoff' into the prompt, it would go to case "takeoff" and run the code that is listed within. This is very useful for what we are doing since we can run any command we want based on our input. The "it worked!" part of the switch is just there so that we know it has receive the correct code.

![Our Current Successful Code]({{site.url}}/assets/Switch-function.png)

At the start of our code we have this which upon execution will send "command" for the drone to enter SDK mode and then immediately check the battery level to make sure it is sufficient. The 'server got:' function will console log whatever we send to the drone so that we know it has received its command correctly.

Here is an example of what that would look like:

```javascript
server.on("message", (msg, rinfo) =>
    console.log(
        `server got: ${msg.toString()} from ${rinfo.address}:${rinfo.port}`
    )
);

server.send(   
    Buffer.from("command"),
    port, 
    address
);

server.send(
    Buffer.from("battery?"),
    port,
    address
);
```
