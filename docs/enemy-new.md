# Enemy Sprites

## Overview

The second step to creating a game is to have an enemy for the player to interact with. In this section, we'll cover creating an enemy sprite, and making it so that they follow and attack the player, causing them to lose health. This section will not be in depth in the basics of how to set sprites or drag code blocks, as this was introduced in the previous section, Player Sprites and Movement.

## Creating a enemy sprite

MakeCode Arcade offers sprites of a few different types. In the past section, we covered the 'player' type. Here, we'll go over creating an 'enemy' type.

1. First, navigate to the 'sprites' section of the code blocks and select the same 'set mysprite2 to sprite of type player' that you used to create your player sprite. Click and drag this into your 'on start' button, with the order here not mattering.
2. To change this sprite to be an enemy, you'll need to click on the 'player' text at the end of the block, which will open up a dropdown menu. Select the type 'enemy' by clicking on it.
[comment]: # (img/enemy_1.png)
3. As covered more in depth in the Player Sprites and Movement section, you'll want to set a custom sprite so this enemy is visible. Click the gray square, then navigate to the gallery and select a premade sprite and hit done.

## Setting up speed and following behaviour

Right now, your enemy won't move at all. This isn't ideal for a chasing game, so we'll now go over making this new enemy chase your player sprite around, and reducing their speed so that it's a fair game.

1. Navigate to the 'sprites' section of the code block menu, then the 'physics' subsection. Select the block that says 'Set myenemy follow mysprite.' Click and drag this into your 'on start' block.
[comment]: # (img/enemy_2.png)
!!! Info
    All the sprites have their own names. Make sure the follower and following sprites match your player and enemy sprites, by clicking on the sprite names and selecting the right one from the dropdown.
[comment]: # (img/enemy_3.png)
1. Our enemy currently moves too quickly, overlapping with the player most of the time. In an actual game, this would be unfair as it would cause constant damage. To fix this, navigate back to your follow code block. There will be a plus symbol at the end. Click this, and your code block will change to now say 'with speed 100.'
[comment]: # (img/enemy_4.png)
1. Change the 100 to a lower number of your choice by clicking on the number, and typing in another.

## Setting up player health

1. To make your player character have lives, navigate to the 'info' section of the code block menu. Under the 'life' subsection, select the 'set life to 3' code block, and click and drag it into your 'on start' block. When your game runs again, you'll now see three hearts in the top left corner.
[comment]: # (img/enemy_5.png)

## Setting up enemy damage

After setting up our enemy to follow and player health, nothing will happen when the player and enemy touch. Don't worry! This isn't a bug either. We'll go over setting up a health and damage system in this section.

1. Navigate to the 'sprites' section of the code block menu. Scroll down to the 'overlaps' section and select the code block that says 'on sprite of kind player overlaps othersprite of kind player.' Unlike the other code blocks we've worked with so far, you don't want to drag this one into your 'on start' block, as it won't work. You can drag this one our into the open space in your editor and let it sit by itself.
[comment]: # (img/enemy_6.png)
!!! Info
    Make sure you click on one instance of 'player' and change it in the dropdown to say 'enemy.' This makes sure the two types interact properly, and not just overlap without anything happening.
1. Navigate to the 'info' section of the code block menu. Under the 'life' subsection, select the block that says 'change life by -1.' Click and drag this code block into your overlap code block, not your 'on start.'
[comment]: # (img/enemy_7.png)
!!! Warning
    Make sure your change life code block is underneath your overlap code block, and not your 'on start' code block. If you place it under 'on start', the player will start with 2 lives and nothing will happen when the enemy touches them.
1. Uh oh! Right now, your enemy spawns on top of your player and instantly kills them. This doesn't work, as it's completely unfair. This can be fixed by making the enemy spawn in a different location. Navigate to the 'sprites' section of the code, then the 'physics' subsection. Select the code block that says 'set mysprite position to x 0 and y 0.' Click and drag this into your 'on start' block.
2. Click the mysprite name and select the name of your enemy sprite from the dropdown. Then, change the x and y values by clicking and typing a new number. There will be a popup showing you where on the map your position will put the enemy.
3. Hmm, this still lets the enemy instantly kill the player when they touch. We can reset the enemy's position when they deal damage to prevent this. Navigate back to the 'sprites' section, and pick another 'set mysprite position to x 0 and y 0.' However, this time, click and drag it into your overlap block, not the 'on start' one. Change the position values and sprite name here as well, so that the enemy can't one shot our player.
[comment]: # (img/enemy_8.png)

## Conclusion

After completing this section, you'll have the following:

* An enemy that follows your player around.
* A player sprite with 3 lives.
* An enemy that damages your player.
* A game that ends when you've run out of lives.

Nice work! You can move on to further customizing your game in the next section, Customization.
[comment]: # (Customization links to the customization page)
