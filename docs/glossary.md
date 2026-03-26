# Glossary

**MakeCode Arcade**  
A web-based platform by Microsoft used to create 2D games using blocks or JavaScript. It includes tools for sprites, tilemaps, and testing games.

**JavaScript**  
A programming language used to control game logic, movement, and interactions.  
Example:

```javascript
controller.moveSprite(player, 100, 100)
```

## Blocks

- A visual way of coding where you drag and connect blocks instead of typing code.
![Block code being used in MakeCode Arcade](img/glossary-1.png "Block code being used in MakeCode Arcade")

## Sprite

- A visual object in the game, such as a player, enemy, or item.

## Player Sprite

- The main character controlled by the user.
  
- Example:

```javascript
let player = sprites.create(img`...`, SpriteKind.Player)
```

![The player creation function being used in the code editor](img/glossary-3.png "The player creation function being used in the code editor")

## Enemy Sprite

- A sprite that challenges the player by chasing or interacting with them.
  
Example:

```javascript
let enemy = sprites.create(img`...`, SpriteKind.Enemy)
```

![The enemy creation function being used in the code editor](img/glossary-4.png "The enemy creation function being used in the code editor")

## SpriteKind

- A category used to define types of sprites (Player, Enemy, etc.).

Example:

```javascript
SpriteKind.Player
SpriteKind.Enemy
```

![The SpriteKind variables in the code editor](img/glossary-5.png "The SpriteKind variables in the code editor")

## Tilemap

- A grid-based layout that defines the game level.
  
Example:

```javascript
tiles.setCurrentTilemap(tilemap`level1`)
```

![The setCurrentTilemap function being used in the code editor](img/glossary-6.png "The setCurrentTilemap function being used in the code editor")

## Location

- A position on the tilemap grid where sprites are placed.
  
Example:

```javascript
tiles.placeOnTile(player, tiles.getTileLocation(1, 2))
```

![The placeOnTile function being used in the code editor](img/glossary-7.png "The placeOnTile function being used in the code editor")

## Collision (Overlap)

- When two sprites touch each other and trigger an event.
  
Example:

```javascript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function () {
    info.changeLifeBy(-1)
})
```

![The onOverlap function being used in the code editor](img/glossary-7-1.png "The onOverlap function being used in the code editor")

## Velocity

- The speed and direction of a sprite’s movement using vx and vy.
  
Example:

```javascript
enemy.vx = 30
enemy.vy = -30
```

![The velocity variables being used in the code editor](img/glossary-8.png "The velocity variables being used in the code editor")

## Event

- A trigger that runs code when something happens (like a button press).
  
Example:

```javascript
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {})
```

![The onEvent checker being used in the code editor](img/glossary-9.png "The onEvent checker being used in the code editor")

## Function

- A reusable block of code used to perform a task.
  
Example:

```javascript
function setLevel(level: number) {}
```

![A custom function being used in the code editor](img/glossary-10.png "A custom function being used in the code editor")

## Level

- A stage in the game with its own layout and difficulty.

## Camera

- Controls what part of the game is visible on screen.
  
Example:

```javascript
scene.cameraFollowSprite(player)

```

![The cameraFollowSprite function being used in the code editor](img/glossary-11.png "The cameraFollowSprite function being used in the code editor")

## Score

- Tracks the player’s progress or achievements.
  
Example:

```javascript
info.changeScoreBy(1)

```

![The changeScoreBy function being used in the code editor](img/glossary-12.png "The changeScoreBy function being used in the code editor")

## Life

- Represents how many chances the player has before the game ends.

Example:

```javascript
info.setLife(3)

```

![The setLife function being used in the code editor](img/glossary-13.png "The setLife function being used in the code editor")

## Update Interval

- A loop that runs code repeatedly after a set time.

Example:

```javascript
game.onUpdateInterval(1000, function () {})

```

![The onUpdateInterval function being used in the code editor](img/glossary-14.png "The onUpdateInterval function being used in the code editor")
