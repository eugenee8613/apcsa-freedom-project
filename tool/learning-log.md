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


3/11/24
I addede sprites and objects to make it into an actual game using the code:
kaboom();

    const MOVE_SPEED = 120;

    loadSprite("player", "sprites/player.png");
    loadSprite("coin", "sprites/coin.png");

    const player = add([
    sprite("player"),
    pos(80, 80),
    origin("center"),
    ]);

    const coin = add([
    sprite("coin"),
    pos(120, 120),
    origin("center"),
    ]);

    // Player movement
    keyDown("d", () => {
    player.move(MOVE_SPEED, 0);
    });

    keyDown("a", () => {
    player.move(-MOVE_SPEED, 0);
    });

    keyDown("s", () => {
    player.move(0, MOVE_SPEED);
    });

    keyDown("w", () => {
    player.move(0, -MOVE_SPEED);
    });

    // Collision detection
    player.collides("coin", (c) => {
    destroy(c);
    });

    // Camera follow player
    const cam = camPos(player.pos);

    // Update function
    function update() {
    camPos(cam);
    }
.


3/19/24
I have now basically created most of the game, I added the score, the sprites cam jump over objects, if the sprite hits the objects, the game is over. Also if the sprite hits the objects it makes a funny burp sound.
```
    import kaboom from "kaboom"
    import "kaboom/global"

    const FLOOR_HEIGHT = 48;
    const JUMP_FORCE = 800;
    const SPEED = 480;

    kaboom();

    loadSprite("bean", "sprites/bean.png");

    scene("game", () => {

    setGravity(1600);

    const player = add([
        sprite("bean"),
        pos(80, 40),
        area(),
        body(),
    ]);

    // floor
    add([
        rect(width(), FLOOR_HEIGHT),
        outline(4),
        pos(0, height()),
        anchor("botleft"),
        area(),
        body({ isStatic: true }),
        color(127, 200, 255),
    ]);

    function jump() {
        if (player.isGrounded()) {
            player.jump(JUMP_FORCE);
        }
    }

    onKeyPress("space", jump);
    onClick(jump);

    function spawnTree() {

        add([
            rect(48, rand(32, 96)),
            area(),
            outline(4),
            pos(width(), height() - FLOOR_HEIGHT),
            anchor("botleft"),
            color(255, 180, 255),
            move(LEFT, SPEED),
            "tree",
        ]);

        wait(rand(0.5, 1.5), spawnTree);

    }

    spawnTree();

    player.onCollide("tree", () => {
        go("lose", score);
        burp();
        addKaboom(player.pos);
    });

    let score = 0;

    const scoreLabel = add([
        text(score),
        pos(24, 24),
    ]);

    onUpdate(() => {
        score++;
        scoreLabel.text = score;
    });

});

    scene("lose", (score) => {

    add([
        sprite("bean"),
        pos(width() / 2, height() / 2 - 80),
        scale(2),
        anchor("center"),
    ]);

    add([
        text(score),
        pos(width() / 2, height() / 2 + 80),
        scale(2),
        anchor("center"),
    ]);

    onKeyPress("space", () => go("game"));
    onClick(() => go("game"));

});

go("game");
```
This is my code so far for the game I am creating.