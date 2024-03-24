# Entry 4
##### 3/18/24


Content: So far I have created the MVP which is the minimum product of the game. I have added
I have now more than the minimun for the game, I added the score, the sprites cam jump over objects, if the sprite hits the objects, the game is over. Also if the sprite hits the objects it makes a funny burp sound. I am getting closer and closer to my finished game.
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
This is my code so far for the game I am creating. Something more I want to add is to create more enemies for the player to encounter. Also different objects and terrain for the player to jump over




## EDP:
On the Engineering Design Procces I am up to the Improve part because since I created it already, I am currently improving it out so that I can see what I need to add and make better. Another level is what I am currently trying to do, I could also add different terrains (assests). Enemeis would sound like something I would add/improve as well.

## Skills:
 I'm starting to get better at debugging and using Google effectively. When I'm coding, I break down the code to understand it better and fix any mistakes. If I get stuck, I search on Google to figure out what went wrong. This helps me learn from my errors and avoid making the same ones again. For example, I recently looked up how to use the function `OnKeyPress` because I wasn't sure how to use it in code. After some research and experimenting with my code, I got it to work. So everytime the user presses `space` the sprite will jump over the objects.

## Sources:
* https://jefferson-cuartas.medium.com/intro-to-kaboom-a-javascript-library-for-game-development-e2b252ee8439
* https://kaboomjs.com/play?example=loader






[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)