# Tool Learning Log

Tool: **Kaboom**

Project: **Game**

---

10/26/23:

https://kaboomjs.com/kaboomware
Introduction to Kaboom Js, what is and how does it work
Sprites and Animation: Kaboom.js allows you to create and manipulate sprites, which are 2D images used in games. Animate these sprites to create movement and actions within the game.
Physics: The library includes physics functions that handle collisions, gravity, and other interactions between game objects.
Input Handling: Kaboom.js simplifies input handling, making it easy to respond to keyboard and mouse events. This is crucial for controlling game characters and responding to player actions.
Sound: Incorporate sound effects and background music into my games using Kaboom.js.
Scenes and Layers: Games often have multiple screens or scenes. Kaboom.js allows you to create different scenes and manage layers within those scenes, enabling smooth transitions and complex game structures.
These are somethings I learned today.


Intro Code
Progress:
```
 kaboom()
            // load a sprite "bean" from an image
            loadSprite("bean", "sprites/bean.png")

            // add something to screen
            add([
                sprite("bean"),
                pos(80, 40),
            ])
            add([
            sprite("bean"),
            pos(80, 40),
            scale(3),
            rotate(30),
            color(0, 0, 255),
        ])

```
Basic Intro for Kaboom just created a bean character with a certain position and size.
Some challenges I had was just going to the site and actually finding the correct code to start off.
Something that I'm going to try next is add more utilities to the code like adding blocks, grass and obstsacles.
<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
