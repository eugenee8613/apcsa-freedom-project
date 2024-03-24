# Entry 3
##### 2/12/24
Content:
So moving foward with the freedom project, I have been adding different parts to the game. I added the default sprites so far. I basically added already all the fundamentals and basicis for it to be a functional game. I added the spritees. I have added the terrain(assestTs), the positions. I added coins so that the player can have a score.
he code I used was:
```
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

    const cam = camPos(player.pos);

    function update() {
    camPos(cam);
    }
```
    Something interesting that I used was adding the WASD controls. Basically these controls control the playser movement so left is the key D, right is the key A, S is to slow down the player, and W is to make the player move faster. I also added object or so called `assests` so its like the terrain and stuff.

EDP:
On the Engineering Design Procces I am up to the Test part because since I created it already, I am currently testing it out so that I can see what I need to add. Maybe I might add another level, I could also add different terrains (assests). I could add enemies that can try to eleminate the player. So far up to the Test section of the EDP and hoping to be soon at the improve section.

Skills: Some skills that I am develpoing so far is debugging and how to google. I am developing debugging because I am breaking apart the code and making sure that it makes sense, and if I make any mistakes I can google it and see what I did wrong so next time I won't make the same mistake again and I learn from the mistake. I asked google some very minor details about to use a specific function such as `function update` because I didn't know what it was updating at first, then I debugged it through my code and tried to use the `function update` function work, so as the sprite moves in the direction that the user wants it to move, the camera updates the postion everytime the user moves using the WASD keys.





[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)