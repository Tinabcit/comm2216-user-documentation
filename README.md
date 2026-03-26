# 🎮 MakeCode Arcade Game Project

## 👥 Team Members
- Tina Shabestari  
- Ria Bhullar

---

## 📌 Project Overview
This project is a 2D game created using MakeCode Arcade.  
The player controls a character (yellow duck 🦆) and must avoid enemies while progressing through different levels.

The purpose of this project was to practice using sprites, tilemaps, and event-based programming to build an interactive game.

---

## 🕹️ Features
- Player movement using keyboard controls  
- Enemy that follows the player  
- Life system (lose life when touching enemy)  
- Game over condition when lives reach 0  
- Level system (press A to move to next level)  
- Tilemap-based level design  
- Camera follows the player  

---

## 🎮 Controls

| Key | Action |
|-----|--------|
| Arrow Keys | Move player |
| A Button | Go to next level |

---

## 🧠 How the Game Works

- The enemy follows the player by comparing positions  
- When the player overlaps with an enemy, they lose 1 life  
- The game ends when the player’s life reaches 0  
- Pressing the A button increases the level  
- The camera follows the player to create a scrolling effect  

---

## 🗂️ Technologies Used
- JavaScript (MakeCode Arcade)  
- Tilemaps  
- Sprites  
- Event-driven programming  

---

## 🚀 How to Run the Game

1. Go to https://arcade.makecode.com/  
2. Click **New Project**  
3. Switch to JavaScript view  
4. Copy and paste the game code  
5. Click **Run** to play  

---

## ⚠️ Troubleshooting

**Player cannot move**
```javascript
controller.moveSprite(yellowDuck)

Losing life too fast

pause(500)

Enemy not moving correctly

Check enemy.vx and position logic
✨ Future Improvements
Add score system
Add sound effects
Add more levels
Add win screen
👩‍💻 Contribution

Tina

Game logic (tilemaps, life system, level system)
README and documentation

Ria

Player, Enemy setup and controls
Instructions and markdown files
Screenshots and visuals
