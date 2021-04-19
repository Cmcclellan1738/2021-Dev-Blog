---
title: Battlesnake Dev Blog
date: 2021-04-19
---

# Battlesnake Development

## Understanding the Problem
I ran into a lot of issues while coding our battlesnake to be the best it can. Understanding the problem comes with a lot of patience and common sense. I learned a lot about how to isolate and figure out what really went wrong. Commenting and console logging certain parts of your algorithm will help tremendously to isolate the issue to figure out why its not working. It can take a decent chunk of your time to figure out the issue if you dont know off the top of your head and it requires a lot of patience. Isolating the problem by individually console logging and making sure everything gives the right inputs and data. 

## Team Role
In our team I layed out the structure for what we wanted our snake to be able to do eventually and then we filled in that skeleton one by one until we had a fully functioning snake. I wrote a lot of the starter code and functions and evolved it to work better with what we wanted to do. We still werent completely finished with our snake because it still makes dumb decisions but we got what we needed done and ended up coming out on top. Our snake is actually very smart for what it is, we had a lot of issues getting it to the point its at now but our snake turned out to be very successful. 

#### This is currently what our snake looks like:

![DaBattleSnakeGif](https://exporter.battlesnake.com/games/c6543c35-e206-4246-9832-70732ff95b18/gif.gif)

## Thinking Algorithmically
A lot of the times while writing and programming code you have to think differently than you would solving problems outside of coding. You have to think from the computers perspective and think about what it is asking and what you are sending it. A lot of the times while coding you try to fix the problem but you have no idea what it wants from you so you have to put yourself into a different mindset. You have to try to put yourself in the computers shoes and try to think how it is thinking, like if it is asking for a move from the server, you have to send it exactly what it wants in the correct syntax or it will have no idea what youre wanting it to do. Our check neck function for example is very complex and what is basically does is it check to see if the head of the snake is about to run into itself at any part of the body and if it is, whatever the move is that will cause that outcome is filtered out so the move cant be selected. 

#### Heres what our check neck function looks like:

````Javascript
checkNeck: (body, possibleMoves) => {
    var filteredPossibleMoves = possibleMoves
    console.log(possibleMoves)
    var move = ""
    body.forEach(segment => {
      if (body[0].y + 1 == segment.y && body[0].x == segment.x) {
        filteredPossibleMoves = filteredPossibleMoves.filter(move => move != "up")
      } else if (body[0].y - 1 == segment.y && body[0].x == segment.x) {
        filteredPossibleMoves = filteredPossibleMoves.filter(move => move != "down")
      } else if (body[0].x + 1 == segment.x && body[0].y == segment.y) {
        filteredPossibleMoves = filteredPossibleMoves.filter(move => move != "right")
      } else if (body[0].x - 1 == segment.x && body[0].y == segment.y) {
        filteredPossibleMoves = filteredPossibleMoves.filter(move => move != "left")
      } else if (body[0].y + 2 == segment.y && body[0].x == segment.x) {
        filteredPossibleMoves = filteredPossibleMoves.filter(move => move != "up")
      } else if (body[0].y - 2 == segment.y && body[0].x == segment.x) {
        filteredPossibleMoves = filteredPossibleMoves.filter(move => move != "down")
      } else if (body[0].x + 2 == segment.x && body[0].y == segment.y) {
        filteredPossibleMoves = filteredPossibleMoves.filter(move => move != "right")
      } else if (body[0].x - 2 == segment.x && body[0].y == segment.y) {
        filteredPossibleMoves = filteredPossibleMoves.filter(move => move != "left")
      }
    });
    return filteredPossibleMoves
}
````

## Problem Solving
A lot of problem solving ties into the previous topic, thinking algorithmically. When youre solving problems with code you have to understand what it wants and why it is not making the correct decisions based on what youre sending it. If the computer is asking for a specific set of moves you have to send it exactly what it wants and in the correct way it wants you to send it or you will have an error and will just cause more problems. 
