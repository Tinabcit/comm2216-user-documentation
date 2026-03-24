# Player Sprites

## Overview

The first step to creating a game is to have a player character. In this section, we will go over a few topics. By the end of this section, you will be able to create a player sprite, give it movement controls, and create a tilemap for your sprite to move around.

As mentioned in the Installation section, MakeCode Arcade organizes it's code blocks into a few main sections visible to the left of the code block area, seen here.

## Creating a player sprite

Sprites are what MakeCode Arcade uses to refer to entities, or characters in the engine. We'll start with creating a sprite of the player type.

1. First, **click** on the 'Sprites' section of the code block menu. The tutorial should have showed you where this is, when you made an account.
2. Once you've clicked on 'Sprites', you'll see a few subsections. The 'Create' one should be at the top, alongside the code block that says 'set mysprite to sprite of kind player.'
[comment]: # (img/player_1.png)
1. **Click** and **drag** that out of the menu, and you'll have the block. **Drag** the block into the 'on start' block that was there when the project was created. You'll know it's in the right spot when 'on start' opens up and the shadow of your block appears. You can **let go** of the block, and it'll click into place. If it lands outside of the 'on start' block, you can move it again by clicking and dragging.
[comment]: # (img/player_2.png)
!!! Info
    If you drag the wrong block, you can drag it back into the block menu, and a trash can will appear. This is where you can delete code blocks.
1. Right now, your player sprite is blank. To fix that, **click** on the empty gray square next to the word 'sprite.' This will open up a small pixel art interface. For the purposes of this documentation, custom sprites will be covered later on.
2. Navigate to the top bar that has menus for 'Editor', 'Gallery', and 'My Assets', and **click** on the 'Gallery' option. This will show you a gallery of many pixel art sprites, and you can **click** on one you like to select it. After selecting it, it'll pop up in the editor. Navigate to the bottom right of the screen and **click** the 'done' button to set the sprite.
[comment]: # (img/player_3.png)

## Setting up movement and camera

Now that we have our player sprite, you'll find that it doesn't move. This is due to there being no controls set up, which we'll fix in this section.

1. Navigate to the controller section, then the single player section inside it. **Select** the 'move mysprite with buttons' block, which should be the top most block.
[comment]: # (img/player_4.png)
1. **Drag** it into the 'on start' block underneath the camera from step 2. Similar to the last section, **click** and **drag** this block out of the menu into your 'on start' block.
!!! Info
    It's important you place the movement block underneath your sprite block, so that the blocks run in order.
1. Navigate to the 'scene' section of the code blocks, then find the 'camera' subsection. **Select** the block that says 'camera follows mysprite.'
[comment]: # (img/player_5.png)
1. Once again, **click** and **drag** this into your 'on start' block, ensuring it's underneath your previous logic.

!!! Info
    After adding the movement camera, it will look like the sprite is no longer moving. This isn't a bug, so don't worry! This is due to the background being black, so there's no visual feedback. We'll fix this in the next steps.

## Creating a tilemap background

To fix the problem of the sprite appearing not to move, and to add some unique charm to your game, you can set a tilemap. A tilemap is basically a background map for your sprite to move around in.

1. Navigate to the 'scene' section of the code blocks, then scroll down to the 'tilemap' section. **Select** the block that says 'set tilemap to tilemap', with a gray square, similar to the player sprite block.
[comment]: # (img/player_6.png)
1. **Click** and **drag** the code block out of the menu and into your 'on start' block. The placement of this block isn't strict, and will still work whether it's before or after your core logic.
2. To design your tilemap, **click** the gray square next to the word 'tilemap.' This will open up the sprite editor, similar to the player sprite menu.
3. Navigate to the top bar that has menus for 'Editor', 'Gallery', and 'My Assets', and **click** on the 'Gallery' option. The gallery will show you a handful of pre-made tilemaps, and you can select whichever one you'd like. After selecting it, it'll pop up in the editor. Navigate to the bottom right, and **click** the 'done' button to set this as your tilemap.
[comment]: # (img/player_7.png)

!!! Info
    These premade tilemaps already have collision set up. This can be done with custom tilemaps as well, but is not the default, and will not be covered in this documentation.

## Conclusion

After completing this section, you'll have the following:

* A player sprite with working movement.
* A camera that follows your player sprite around.
* A tilemap for your player sprite to move around in.

You can now move on to the next section, Enemy Sprites and Interaction. Nice work!
[comment]: # (Enemy Sprites and Interaction links to the enemy page)
