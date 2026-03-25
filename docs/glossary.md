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
![Alt text for the image](img/glossary-1.png)

## Sprite

- A visual object in the game, such as a player, enemy, or item.

## Player Sprite

- The main character controlled by the user.
  
- Example:

```javascript
let player = sprites.create(img`...`, SpriteKind.Player)
```

![Alt text for the image](img/glossary-3.png)

## Enemy Sprite

- A sprite that challenges the player by chasing or interacting with them.
  
Example:

```javascript
let enemy = sprites.create(img`...`, SpriteKind.Enemy)
```

![Alt text for the image](img/glossary-4.png)

## SpriteKind

- A category used to define types of sprites (Player, Enemy, etc.).

Example:

```javascript
SpriteKind.Player
SpriteKind.Enemy
```

![Alt text for the image](img/glossary-5.png)

## Tilemap

- A grid-based layout that defines the game level.
  
Example:

```javascript
tiles.setCurrentTilemap(tilemap`level1`)
```

![Alt text for the image](img/glossary-6.png)

## Location

- A position on the tilemap grid where sprites are placed.
  
Example:

```javascript
tiles.placeOnTile(player, tiles.getTileLocation(1, 2))
```

![Alt text for the image](img/glossary-7.png)

## Collision (Overlap)

- When two sprites touch each other and trigger an event.
  
Example:

```javascript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function () {
    info.changeLifeBy(-1)
})
```

![Alt text for the image](img/glossary-7-1.png)

## Velocity

- The speed and direction of a sprite’s movement using vx and vy.
  
Example:

```javascript
enemy.vx = 30
enemy.vy = -30
```

![Alt text for the image](img/glossary-8.png)

## Event

- A trigger that runs code when something happens (like a button press).
  
Example:

```javascript
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {})
```

![Alt text for the image](img/glossary-9.png)

## Function

- A reusable block of code used to perform a task.
  
Example:

```javascript
function setLevel(level: number) {}
```

![Alt text for the image](img/glossary-10.png)

## Level

- A stage in the game with its own layout and difficulty.

## Camera

- Controls what part of the game is visible on screen.
  
Example:

```javascript
scene.cameraFollowSprite(player)

```

![Alt text for the image](img/glossary-11.png)

## Score

- Tracks the player’s progress or achievements.
  
Example:

```javascript
info.changeScoreBy(1)

```

![Alt text for the image](img/glossary-12.png)

## Life

- Represents how many chances the player has before the game ends.

Example:

```javascript
info.setLife(3)

```

![Alt text for the image](img/glossary-13.png)

## Update Interval

- A loop that runs code repeatedly after a set time.

Example:

```javascript
game.onUpdateInterval(1000, function () {})

```

![Alt text for the image](img/glossary-14.png)
