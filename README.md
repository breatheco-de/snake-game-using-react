<!-- hide -->
# Create Your Own Snake Game in React!
<!-- endhide -->

<how-to-start>

## 🌱 How to start this project

Don't clone this repository because we will use a different template.

We recommend opening the `React template` using a provisioning tool like [Codespaces](https://4geeks.com/lesson/what-is-github-codespaces) (recommended) or [Gitpod](https://4geeks.com/lesson/how-to-use-gitpod). Alternatively, you can [clone the GitHub repository](https://4geeks.com/how-to/github-clone-repository) on your local computer using the `git clone` command.

This is the repository you need to open or clone:

```
https://github.com/4GeeksAcademy/react-hello
```

> ⚠ You will need to have Node.js installed if you do it locally, but all of that is already installed on Codespaces or Gitpod!

</how-to-start>

## 📝 Instructions

### Step 1: Set Up the Project

- [ ] Set up the boilerplate project from the provided React template.
  
- [ ] Follow the instructions in the README of the repository to set up your development environment.

### Step 2: Plan the Game Structure

- [ ] Create a sketch or diagram of how your Snake game will look.

  - How will you represent the game board?
  - How will you manage the state of the snake and the food?
  - What components will you need?

### Step 3: Implement the Game Board

- [ ] Create a `Board` component that will represent the area where the snake moves.

- [ ] Define the size of the board (e.g., a 20x20 grid).

- [ ] Use CSS to style the board and the cells.

### Step 4: Manage State with useState

- [ ] Use the `useState` hook to manage:

  - The position of the snake (an array of coordinates).
  - The current direction of movement.
  - The position of the food.
  - The game state (running, game over).

```jsx
const [snake, setSnake] = useState([[10, 10]]);
const [direction, setDirection] = useState('RIGHT');
const [food, setFood] = useState([15, 15]);
const [gameOver, setGameOver] = useState(false);
```

### Step 5: Handle Snake Movement

- [ ] Use the `useEffect` hook to create a game loop that updates the snake's position at regular intervals.

- [ ] Calculate the new head of the snake based on the current direction.

- [ ] Check for collisions with walls or with the snake itself.

```jsx
useEffect(() => {
  const moveSnake = () => {
    // Logic to move the snake
  };

  if (!gameOver) {
    const interval = setInterval(moveSnake, 200);
    return () => clearInterval(interval);
  }
}, [snake, direction, gameOver]);
```

### Step 6: Key Controls to Change Direction

- [ ] Add an event listener for arrow keys and update the snake's direction accordingly.

```jsx
useEffect(() => {
  const handleKeyDown = (event) => {
    switch(event.key) {
      case 'ArrowUp':
        setDirection('UP');
        break;
      case 'ArrowDown':
        setDirection('DOWN');
        break;
      case 'ArrowLeft':
        setDirection('LEFT');
        break;
      case 'ArrowRight':
        setDirection('RIGHT');
        break;
      default:
        break;
    }
  };

  window.addEventListener('keydown', handleKeyDown);
  return () => window.removeEventListener('keydown', handleKeyDown);
}, []);
```

### Step 7: Implement Food Logic

- [ ] When the snake eats the food:

  - Increase the length of the snake.
  - Generate a new random position for the food.

- [ ] Ensure that the food does not appear on a position occupied by the snake.

### Step 8: Handle Game Over

- [ ] Determine when the game is over (collision with walls or itself).

- [ ] Display a "Game Over!" message and offer an option to restart the game.

```jsx
if (checkCollision(newHead)) {
  setGameOver(true);
}
```

### Step 9: Improve the User Interface

- [ ] Add visual elements such as:

  - Current score (based on the snake's length or number of food items consumed).
  - Button to restart the game.
  - Visual indicators for the food and the snake.

- [ ] Ensure the game is responsive and looks good on different devices.

## Bonus Section

### Additional Features to Practice and Improve the Project

1. **Speed Adjustment:** Increase the snake's speed as the player progresses.

2. **Difficulty Levels:** Offer different difficulty levels with varying speeds or board sizes.

3. **Obstacles:** Add obstacles to the board that the snake must avoid.

4. **Sounds and Effects:** Add sound effects when eating food or when the game ends!

5. **High Scores:** Implement a system to save and display high scores using local storage.

6. **Customizable Themes:** Allow the player to choose between different visual themes for the game.

7. **Multiplayer Game:** Implement a mode where two snakes compete on the same board.

Explore different enhancements to make your Snake game more interesting and challenging!
