---
title: Drone Communication
date: 2021-02-11
---

# How Drones and a Computer Communicate
### IP Adresses and Port Numbers

We use IP adresses and port numbers to connect directly from our computer to the drone. Every IP address is unique and every port number is unique to the device you are using. The first 3 group of number or octets in an IP adress describes the network your device is currently connected to. The last octet in an IP address is the host number or the specific number your network temporarily assigns to your device.  

### TCP and UDP 
TCP and UDP are 2 different protocols for transfering files or data across the internet. One is reliable but slow and the other is fast but usually very unreliable. TCP or Transmissin Control Protocol is a from of data transfer that is very slow due to the fact that when you send a file or command it responds back with either the phrase ok meaning that it received it or nothing which means it was not received. UDP on the other hand is a very fast form of data transfer usually used for voice calls and other things. When you send a command using UDP it sends them back to back without replies and it doesnt care if it gets received or not. Some of the files may drop off and be corrupted and some will go through.

We use TCP when flying drones to make sure that the drone has received the command and whether it will act upon that command or if there is debugging required. If we were to use UDP we would have a lot of those commands be dropped off in the process of transfer and the drone would not receive it so it is best that we use TCP to make sure the commands are received correctly.
