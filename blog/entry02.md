# Entry 2
##### 12/11/23

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)

Content:
Given my interest in health and fitness, I decided to incorporate fitness elements into the game. I added "health boosts" that the player collects for points. Here's an example of the addition of health boosts:

```
const healthBoost = game.add([
  sprite("healthBoost"),
  pos(200, 200),
  layer("obj"),
]);

player.collides(healthBoost, function () {
  destroy(healthBoost);
});
```


I also added interactivity. This included keyboard controls for the player character. Here's an example of the code

 ```
 keyDown("left", function () {
  player.move(-100, 0);
});

keyDown("right", function () {
  player.move(100, 0);
});
```


Sources:

kaboom.js - to get started and transfer the data into my ide
Youtube - helped me with any questions/concerns I had during the setup, etc.
Google- searhed how to put the position and load the sprite



EDP:
FOr the EDP I am up to the plan part becuase I am  at the middle area of Kaboom.
I imported all the requirements from Kaboom.js and moved them into my IDE.
I am planning with my partner on what to make next.




Skills:
I noticed that I am determined to grow is Debugging because no one is perfect, and no one can get the code right at the first try so debugging is a skill that I will try my best to master. By rereading the code and making sure it runs.
I learned How to google,  because by googling, it is the best tool to use especially if your stuck on some code, you can use the internet to help you out. I used the internet to help me out because I didn't how to  load the sprite and place its position I searched it up and got this code
