# Troubleshooting Guide

This guide helps you fix common problems when creating an enemy sprite in MakeCode Arcade.

If your game is not working correctly, check the issues below and follow the suggested solutions.

---

## Enemy Sprite Issues

### Enemy does not appear

**Cause:**

- Enemy sprite not created or not placed on the map

**Solution:**

```javascript
let enemy = sprites.create(img`...`, SpriteKind.Enemy)
tiles.placeOnTile(enemy, tiles.getTileLocation(8, 2))
```

- Enemy is not moving

**Cause:**

- Missing movement logic

- Velocity not set
  
```javascript
Solution:

game.onUpdateInterval(1000, function () {
    enemy.vx = 30
    enemy.vy = 30
})
```

- Enemy is not following the player

**Cause:**

- No position comparison logic

Solution:

```javascript
if (enemy.x < yellowDuck.x) {
    enemy.vx = 30
} else {
    enemy.vx = -30
}
Player Issues
Player cannot move
```

**Cause:**

- Movement not enabled

Solution:

```javascript
controller.moveSprite(yellowDuck, 100, 100)
```

- Camera does not follow player

**Cause:**

- Camera function missing

Solution:

```javascript
scene.cameraFollowSprite(yellowDuck)
```

- Collision Issues
- Player does not lose life

**Cause:**

- Overlap event missing or incorrect

Solution:

```javascript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function () {
    info.changeLifeBy(-1)
})
```

- Game does not end

**Cause:**

- Missing game over condition

Solution:

```javascript
if (info.life() <= 0) {
    game.over(false)
}
```

- Level Issues
- Levels do not change

**Cause:**

- Button event missing

- Level variable not updated

Solution:

```javascript
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    currentLevel += 1
    setLevel(currentLevel)
})
```

- Sprites appear in wrong position

**Cause:**

- Incorrect tile coordinates

Solution:

```javascript
tiles.placeOnTile(enemy, tiles.getTileLocation(8, 2))
```

- General Errors
Code not running or showing errors

**Cause:**

- Syntax errors (missing brackets, wrong names)

Solution:

Check:

- variable names (yellowDuck, enemy)

- brackets { }

- parentheses ( )

- spelling mistakes

## Debugging Tips

- Test your game after each change

- Start with simple values

- Keep code organized

- Add comments to understand your code

- Fix one problem at a time.
