# Enemy Sprites

## Overview

The second step to creating a game is to have an enemy for the player to interact with. In this section, we'll cover creating an enemy sprite, and making it so that they follow the player.

## Creating a enemy sprite

MakeCode Arcade offers sprites of a few different types. In the past section, we covered the 'player' type. Here, we'll go over creating an 'enemy' type.

1. First, navigate to the 'sprites' section of the code blocks and select the same 'sprite img of kind kind.' **Click** and **drag** this into your code editor, and make sure it's on a new line. You should see similar code like this. Note that it says mySprite2 instead of mySprite, as it's a different sprite.

```javascript
    let mySprite2 = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
```

2. Right now, this sprite is also a player. To change it to an enemy, we'll need to change the SpriteKind variable. **Delete** where it says 'Player', and type in 'Enemy' instead. You should have code that looks like this.

```javascript
    let mySprite2 = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    . . . . . . . . . . . . . . . .
    `, SpriteKind.Enemy)
```

3. Once again, we'll want to set a custom sprite so our enemy isn't invisible. Similar to the Player section, you can click the floating palette and use the editor to create your own, or **copy** and **paste** the code below and replace your blank enemy code. You should now see a little lemon in your game window.

```javascript
    let mySprite2 = sprites.create(img`
    4 4 4 . . 4 4 4 4 4 . . . . . .
    4 5 5 4 4 5 5 5 5 5 4 4 . . . .
    b 4 5 5 1 5 1 1 1 5 5 5 4 . . .
    . b 5 5 5 5 1 1 5 5 1 1 5 4 . .
    . b d 5 5 5 5 5 5 5 5 1 1 5 4 .
    b 4 5 5 5 5 5 5 5 5 5 5 1 5 4 .
    c d 5 5 5 5 5 5 5 5 5 5 5 5 5 4
    c d 4 5 5 5 5 5 5 5 5 5 5 1 5 4
    c 4 5 5 5 d 5 5 5 5 5 5 5 5 5 4
    c 4 d 5 4 5 d 5 5 5 5 5 5 5 5 4
    . c 4 5 5 5 5 d d d 5 5 5 5 5 b
    . c 4 d 5 4 5 d 4 4 d 5 5 5 4 c
    . . c 4 4 d 4 4 4 4 4 d d 5 d c
    . . . c 4 4 4 4 4 4 4 4 5 5 5 4
    . . . . c c b 4 4 4 b b 4 5 4 4
    . . . . . . c c c c c c b b 4 .
    `, SpriteKind.Enemy)
```

!!! info
    Don't worry if you can't see your apple sprite from the last section anymore! By default, the sprites are placed in the same spot, so they're overlapping. Your apple is still there, just underneath the lemon.

## Setting up speed and following behaviour

Right now, your enemy won't move at all. This isn't ideal for a chasing game, so we'll now go over making this new enemy chase your player sprite around, and reducing their speed so that it's a fair game.

1. Navigate to the 'sprites' section of the code block menu, then the 'physics' subsection. Select the block that says 'Set myenemy follow mysprite.' Click and drag this into your code window. The code should look like this.

```javascript
    myEnemy.follow(mySprite)
```

2. Right now, you'll see a squiggly red line underneath the word 'myEnemy.' This is because that's not the name of our sprites! MakeCode Arcade is looking for a sprite named 'myEnemy', and can't find one. To fix this, **delete** only the word 'myEnemy.' Replace this with the name of your enemy, which is 'mySprite2.' Your code should look like this.

```javascript
    mySprite2.follow(mySprite)
```

3. In the current state of the game, the enemy and player will move at the same speed when controls are implemented. To fix this, lets preemptively reduce the speed of our enemy. We'll edit your follow code again. Right now, it takes in the name of the sprite being followed, and we'll just add another number to signify how fast it should follow. **Type** a comma after the word mySprite, and add a number. Your code should look like the snippet below.

```javascript
    mySprite2.follow(mySprite, 70)
```

!!! info
    It'll still look like nothing is happening. Don't worry! This will be fixed in the next section, where we set up controls for the player.

## Conclusion

After completing this section, you'll have the following:

* An enemy with a unique sprite.
* An enemy that follows your player around.

Nice work! You can move on to further customizing your game in the next section, Customization.
 [Enemy Customization Page](enemy-higher-level.md)
