# 🎮 Tic Tac Toe Game (HTML + CSS + JavaScript)

A simple web-based Tic Tac Toe game built using basic **HTML**, **CSS**, and **JavaScript**. Two players can play turn-by-turn as "O" and "X". The game announces the winner and provides options to reset or start a new game.

---

## 📁 Project Structure
tic-tac-toe/
│
├── index.html # Game UI structure
├── style.css # Styling and layout
└── app.js # Game logic and interactions


---

## 🧠 Features

- 3x3 Grid Tic Tac Toe board.
- Two-player gameplay (O and X).
- Win detection logic based on all 8 possible winning patterns.
- "New Game" and "Reset Game" functionality.
- Winner message display.
- Disable board after game ends.
- Simple, clean responsive design.

---

## 🚀 How to Use

1. **Click on any box** to make a move.
2. The game alternates between **Player O** and **Player X**.
3. The first player to form a winning pattern is declared the winner.
4. Click **"New Game"** or **"Reset Game"** to restart.

---

## 📋 Core JavaScript Logic (Quick Summary)

### 🔄 Turn Handling

```javascript
let turnO = true; // O starts first
box.innerText = turnO ? "O" : "X";
turnO = !turnO;
// Winning Patterns
const winPatterns = [
  [0,1,2], [3,4,5], [6,7,8], // rows
  [0,3,6], [1,4,7], [2,5,8], // columns
  [0,4,8], [2,4,6]           // diagonals
];
//🏆 Check Winner
const checkWinner = () => {
  for (let pattern of winPatterns) {
    let val1 = boxes[pattern[0]].innerText;
    let val2 = boxes[pattern[1]].innerText;
    let val3 = boxes[pattern[2]].innerText;

    if (val1 && val1 === val2 && val2 === val3) {
      showWinner(val1);
    }
  }
};
//🔒 Disable & Enable Boxes
const disableBoxes = () => {
  boxes.forEach(box => box.disabled = true);
};

const enableBoxes = () => {
  boxes.forEach(box => {
    box.disabled = false;
    box.innerText = "";
  });
};
//🎉 Show Winner
const showWinner = (winner) => {
  msg.innerText = `Congratulation, Winner is ${winner}`;
  msgContainer.classList.remove("hide");
  disableBoxes();
};

