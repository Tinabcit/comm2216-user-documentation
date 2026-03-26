# Enemy Sprites

## Overview

The second step to creating a game is to have an enemy for the player to interact with. In this section, we'll cover creating an enemy sprite, and making it so that they follow the player.

## Step 1: Creating a enemy sprite

MakeCode Arcade offers sprites of a few different types. In the past section, we covered the 'player' type. Here, we'll go over creating an 'enemy' type.

1. **Navigate** to the 'sprites' section of the code blocks and select the same 'sprite img of kind kind.'

2. **Click** and **drag** this into your code editor, and make sure it's on a new line. You should see similar code like this. Note that it says mySprite2 instead of mySprite, as it's a different sprite.

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

3. **Delete** where it says 'Player', and type in 'Enemy' instead. You should have code that looks like this. This is to ensure the new sprite is an enemy, and not another player.

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

4. **Copy** and **paste** the code below and replace your blank enemy code. You should now see a little lemon in your game window. Optionally, you can **click** the floating palette and create your own sprite.

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

## Step 2: Setting up speed and following behaviour

Right now, your enemy won't move at all. This isn't ideal for a chasing game, so we'll now go over making this new enemy chase your player sprite around, and reducing their speed so that it's a fair game.

1. **Navigate** to the 'sprites' section of the code block menu, then the 'physics' subsection. Select the block that says 'Set myenemy follow mysprite.' Click and drag this into your code window. The code should look like this.

    ```javascript
        myEnemy.follow(mySprite)
    ```

2. **Delete** only the word 'myEnemy.' Replace this with the name of your enemy, which is 'mySprite2.' Your code should look like this. This is to ensure MakeCode Arcade makes your enemy sprite follows your player, and not a random one.

    ```javascript
        mySprite2.follow(mySprite)
    ```

3. **Type** a comma after the word mySprite, and add a number. Your code should look like the snippet below. This makes the enemy slightly slower than the player.

    ```javascript
        mySprite2.follow(mySprite, 70)
    ```

    !!! info
        It'll still look like nothing is happening. Don't worry! This will be fixed in the next section, where we set up controls for the player.

## Conclusion

After completing this section, you'll have the following:

* An enemy with a unique sprite.
* An enemy that follows your player around.

Nice work! You can move on to further customizing your game in the next section, [Game Controller](game-controls.md).
