# Optional for Enemy

In this tutorial, we will learn how to create an **enemy sprite** in MakeCode Arcade using JavaScript.  
The enemy sprite will appear in the game, move toward the player, and reduce the player's life when touched.

Enemy sprites help make games more interactive because they create obstacles and challenges for the player.

---

## Introduction to Enemy Sprites

In many arcade games, enemies are characters that move around the game world and interact with the player.  
In this tutorial, we will create an enemy sprite and program it so that it follows the player and affects the player's lives when they collide.

By the end of this guide, you will understand how to:

- create a player sprite
- create an enemy sprite
- control player movement
- use the camera to follow the player
- add game information such as score and lives
- load multiple levels
- move the enemy toward the player
- detect collisions between sprites
- change levels during gameplay

---

## Prerequisites

Before starting this tutorial, make sure you:

- have access to **MakeCode Arcade**
- understand basic **JavaScript or Blocks**
- know how to create a **new MakeCode Arcade project**

You can open MakeCode Arcade here:

https://arcade.makecode.com/

---

## Step 1: Open MakeCode Arcade

1. Open your web browser.
2. Go to **MakeCode Arcade**.
3. Click **New Project**.
4. Name your project (for example: `Enemy Game`).

Once the editor opens, switch to **JavaScript mode**.

---

## Step 2: Creating the Player Sprite

The first step in the game is creating the **player sprite**.  
In this tutorial, the player is represented by a **yellow duck**.

The following JavaScript code creates the player sprite and assigns it the type `SpriteKind.Player`.

```javascript
let yellowDuck = sprites.create(img`
    . . . . . . . . . . a 5 a . . .
    . . . . . . . . . a 5 a . . . .
    . . . . . . a a a a a a . . . .
    . . . . . a a 5 5 5 5 5 a . . .
    . . . . a a 5 d 1 f 5 d 4 c . .
    . . . . a 5 5 1 f f d d 4 4 4 a
    . . . . a 5 5 d f b 4 4 4 4 a .
    . . . a d 5 5 5 5 4 4 4 4 a . .
    . a a d d d 5 5 5 5 5 5 5 a . .
    a d d d a a a 5 5 5 5 5 5 5 a .
    c d d a 5 5 d c 5 5 5 5 5 5 a .
    c a a d 5 d c d 5 5 5 5 5 5 a .
    c a 5 5 b c d d 5 5 5 5 5 5 a .
    a a c c c d d d 5 5 5 5 5 d a .
    . . . . c c d d d 5 5 5 a a . .
    . . . . . . c c c c c a a . . .
`, SpriteKind.Player)
```

## Step 3: Creating the Enemy Sprite

After creating the player, we create the enemy sprite.
The enemy will chase the player during gameplay.

``` javascript
let enemy = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . 2 2 2 2 2 2 2 . . . . .
    . . . 2 2 2 2 2 2 2 2 2 . . . .
    . . 2 2 2 f 2 2 2 f 2 2 2 . . .
    . . 2 2 2 2 2 2 2 2 2 2 2 . . .
    . . 2 1 2 2 2 2 2 2 2 1 2 . . .
    . . 2 2 2 2 2 2 2 2 2 2 2 . . .
    . . . 2 2 2 2 2 2 2 2 2 . . . .
    . . . . 2 2 2 2 2 2 2 . . . . .
    . . . . . 2 2 . . 2 2 . . . . .
    . . . . 2 2 . . . . 2 2 . . . .
    . . . 2 2 . . . . . . 2 2 . . .
    . . 2 2 . . . . . . . . 2 2 . .
`, SpriteKind.Enemy)
```

- The type SpriteKind.Enemy tells the game that this sprite represents an enemy character.

## Step 4: Enabling Player Movement

- Next, we allow the player to move around the game map.
  
``` javascript
controller.moveSprite(yellowDuck, 100, 100)
```

This command allows the player to move in all directions using the arrow keys.

## Step 5: Making the Camera Follow the Player

- To keep the player centered on the screen while moving through the level, the camera follows the player sprite.
  
``` javascript
scene.cameraFollowSprite(yellowDuck)
```

This ensures the player stays centered on the screen.

## Step 6: Adding Game Information

- Add score and life counters.
  
``` javascript
info.setLife(3)
info.setScore(0)
```
- The player starts with three lives.

## Step 7: Starting the First Level
- Track the current level and load the first level.
``` javascript
let currentLevel = 1
setLevel(currentLevel)
```
## Step 8: Creating the Level System
- The setLevel() function loads different tilemaps and positions the sprites.
``` javascript
function setLevel(level: number) {
    if (level == 1) {
        tiles.setCurrentTilemap(tilemap`level1`)
        tiles.placeOnTile(yellowDuck, tiles.getTileLocation(1, 2))
        tiles.placeOnTile(enemy, tiles.getTileLocation(8, 2))
    } else if (level == 2) {
        tiles.setCurrentTilemap(tilemap`level2`)
        tiles.placeOnTile(yellowDuck, tiles.getTileLocation(1, 1))
        tiles.placeOnTile(enemy, tiles.getTileLocation(7, 5))
    } else {
        tiles.setCurrentTilemap(tilemap`level3`)
        tiles.placeOnTile(yellowDuck, tiles.getTileLocation(2, 2))
        tiles.placeOnTile(enemy, tiles.getTileLocation(10, 6))
    }
}
```
- Each level loads a different map and places the enemy in a new location.

## Step 9: Programming the Enemy to Follow the Player
- The enemy moves toward the player every second.
``` javascript
game.onUpdateInterval(1000, function () {
    if (enemy.x < yellowDuck.x) {
        enemy.vx = 30
    } else {
        enemy.vx = -30
    }

    if (enemy.y < yellowDuck.y) {
        enemy.vy = 30
    } else {
        enemy.vy = -30
    }
})
```
- This creates a simple enemy chasing behavior.

## Step 10: Detecting Collisions Between Player and Enemy
When the enemy touches the player, the player loses one life.
``` javascript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (player, badGuy) {
    info.changeLifeBy(-1)
    tiles.placeOnTile(yellowDuck, tiles.getTileLocation(1, 2))
    pause(500)

    if (info.life() <= 0) {
        game.over(false)
    }
})
```
- If the player loses all lives, the game ends.

## Step 11: Changing Levels
- Press the A button to move to the next level.

``` javascript
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    currentLevel += 1

    if (currentLevel > 3) {
        game.over(true)
    } else {
        setLevel(currentLevel)
        info.changeScoreBy(1)
    }
})
```

When all levels are completed, the player wins the game.

## Summary
In this tutorial, you learned how to:

- create a player sprite

- create an enemy sprite

- enable player movement

- add camera tracking

- display score and lives

- build multiple levels

- program enemy movement

- detect sprite collisions

- change levels during gameplay

Enemy sprites make games more exciting because they introduce challenge and interaction.