# Calculator

A simple calculator built with HTML, CSS, and JavaScript. It runs in the browser and needs no libraries.

## Features

- Addition, subtraction, multiplication, and division
- `AC` to clear everything
- `+/-` to change a number between positive and negative
- `%` to turn a number into a percentage (divides by 100)
- Decimal numbers (only one `.` per number)
- Chain calculations, for example `5 + 3 + 2 = 10`
- Division by zero shows `Error`
- Rounds results to avoid errors like `0.1 + 0.2 = 0.30000000000000004`

## How it works

The project has three parts:

1. **HTML**: the structure (display, buttons)
2. **CSS**: the look (colors, layout, spacing)
3. **JavaScript**: the logic (what happens when you click)

## 1. HTML (Structure)

- A main box (`.containor`) holds the whole calculator.
- The top shows the title "Standard".
- Below it is the display, a read-only `<input>`, so the user can only type using the buttons.
- Under the display are the buttons, arranged in rows:
  - **Utility buttons:** AC, +/-, %
  - **Number buttons:** 0 to 9 and the decimal point
  - **Operator buttons:** `/`, `x`, `-`, `+`
  - **Equal button:** `=`
- Each button uses `onclick` to call a JavaScript function.

## 2. CSS (Design)

- `*` removes the default margin and padding from everything.
- `.containor` sets the calculator width (350px), centers it, and gives it a gray background, rounded corners, and a shadow.
- `.main` uses **CSS Grid** with 4 equal columns, so every row of buttons lines up.
- `.button` gives every button the same size, no border, and a pointer cursor.
- Each button type has its own color:
  - `.utility` is purple
  - `.operator` is black
  - `.number` is dark gray
  - `.equal` is green

## 3. JavaScript (Logic)

### Variables

| Variable | Purpose |
|----------|---------|
| `display` | The display input on the page |
| `current` | The number the user is typing now |
| `previous` | The first number, saved when an operator is pressed |
| `operator` | The chosen operation (`+`, `-`, `*`, `/`) |
| `justCalculated` | Remembers that `=` was just pressed, so a new number starts a fresh calculation |

### Functions

| Function | What it does |
|----------|--------------|
| `updateDisplay()` | Rebuilds the display text from `previous`, `operator`, and `current` (for example `5 + 3`) |
| `appendNum(num)` | Adds a digit or `.` to `current`. Blocks a second `.` and removes extra leading zeros |
| `selectOperator(op)` | Saves `current` into `previous` and stores the operator. If a calculation is already waiting, it calculates it first (chain calculation) |
| `compute(a, b, op)` | Does the math with a `switch` statement. Returns `Error` for division by zero and rounds the result |
| `calculate()` | Runs when `=` is clicked. Uses `compute()` and shows the result |
| `toggleSign()` | Changes the current number between positive and negative |
| `percentage()` | Divides the current number by 100 |
| `clearDisplay()` | Resets the display and all variables |
| `showError()` | Clears everything and shows `Error` |

### Example

To calculate `5 + 3`:
1. Click `5`, so `current = "5"`
2. Click `+`, so `previous = "5"`, `operator = "+"`
3. Click `3`, so `current = "3"`
4. Click `=`, so the display shows `8`

## How to run

1. Save the code as `calculator.html`.
2. Open the file in any web browser.
3. <img width="202" height="200" alt="image" src="https://github.com/user-attachments/assets/da3c8aaa-f13e-4fa2-bd97-24f91767e3d3" />

