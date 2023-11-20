# Entry 1
##### 11/6/X23

Content:
The tool that I chose right now currently is kaboom.js I chose this tool becasue I wanted to create some type of 3rd person fighting game relating to Mortal Combat and UFC 5. I also chose this because I am starting to have a passion for fighting. I want to create a 3rd person fighting game related to Mortal Combat or UFC. Some cool game that maybe others will enjoy playing.It doesn't have to be remotely close to a fighting game but it the concept can be a way easier version to replicate.

I am up to the starting point with just making the characters(`sprites`)

```
kaboom()

// define gravity
setGravity(2400)

// load a default sprite
loadBean()

// add character to screen, from a list of components
const player = add([
    sprite("bean"),  // renders as a sprite
    pos(120, 80),    // position in world
    area(),          // has a collider
    body(),          // responds to physics and gravity
])

// jump when player presses "space" key
onKeyPress("space", () => {
    // .jump() is provided by the body() component
    player.jump()
})
```




Sources:

kaboom.js - to get started and transfer the data into my ide
Youtube - helped me with any questions/concerns I had during the setup, etc.
Google- searhed how to put the position and load the sprite



EDP:
FOr the EDP I am up to the research part becuase I am still at the beginning area of Kaboom.
I imported all the requirements from Kaboom.js and moved them into my IDE.




Skills:
One skill that I am determined to grow is Debugging because no one is perfect, and no one can get the code right at the first try so Debugging is a skill that I will try my best to master. By rereading the code and making sure it runs.
The second skill is How to google,  because by googling, it is the best tool to use especially if your stuck on some code, you can use the internet to help you out. I used the internet to help me out because I didn't how to  load the sprite and place its position I searched it up and got this code
 ```
 loadBean()
// add character to screen, from a list of components
const player = add([
    sprite("bean"),  // renders as a sprite
    pos(120, 80),    // position in world
    area(),          // has a collider
    body(),          // responds to physics and gravity
])

```




[Next](entry02.md)

[Home](../README.md)