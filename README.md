<h1 align="center">Calculator</h1>

## Project Description
This project implements a simple **Calculator** using HTML, CSS, and JavaScript. The application allows users to perform basic arithmetic operations such as addition, subtraction, multiplication, and division through an intuitive user interface.

## Features

1. **Basic Operations**:
   - **Addition**: Users can add numbers using the `+` button.
   - **Subtraction**: Users can subtract numbers using the `-` button.
   - **Multiplication**: Users can multiply numbers using the `*` button.
   - **Division**: Users can divide numbers using the `/` button.

2. **User Interaction**:
   - **Input Display**: The current calculation is displayed in a dedicated input field.
   - **Clear Display**: Users can clear the input using the `AC` button.
   - **Delete Last Character**: Users can remove the last entered character using the `DE` button.

## Project Structure

The project contains the following files:

- `index.html`: The main HTML file containing the calculator structure and user interface.
- `style.css`: The CSS file for styling the calculator interface.
- `script.js`: The JavaScript file that contains the logic for the calculator operations.

## Code Explanation

### HTML (`index.html`)

The HTML file defines the structure of the calculator. Key components include:

- **Form and Display**:
    ```html
    <div class="display">
        <input type="text" name="display">
    </div>
    ```
    This input field displays the current value or result of the calculations.

- **Calculator Buttons**:
    ```html
    <input type="button" value="1" onclick="appendChar('1')">
    ```
    Each button calls the `appendChar` function with its value when clicked, allowing users to input numbers and operations.

### CSS (`style.css`)

The CSS styles the calculator, including the layout and appearance of buttons and the display. Key styles include:

- Setting a background color for the calculator.
- Styling the buttons with shadows and rounded corners for a modern look.
- Adjusting the input display to align text to the right for better readability.

### JavaScript (`script.js`)

The JavaScript code contains the logic for the calculator operations:

- **Append to Display**:
    ```javascript
    function appendChar(char) {
        document.forms[0].display.value += char;
    }
    ```
    This function adds the character clicked on the button to the display input field.

- **Clear Display**:
    ```javascript
    function clearDisplay() {
        document.forms[0].display.value = '';
    }
    ```
    This function resets the display to an empty string when the "AC" button is clicked.

- **Delete Last Character**:
    ```javascript
    function deleteLast() {
        var displayValue = document.forms[0].display.value;
        document.forms[0].display.value = displayValue.slice(0, -1);
    }
    ```
    This function removes the last character from the display, allowing for corrections.

- **Calculate Result**:
    ```javascript
    function calculate() {
        var displayValue = document.forms[0].display.value;
        try {
            var result = eval(displayValue);
            if (!isFinite(result)) {
                throw "Error, can't divide by zero";
            }
            document.forms[0].display.value = result;
        } catch (error) {
            alert(error);
        }
    }
    ```
    This function evaluates the expression in the display using the `eval` function, checks for division by zero, and displays the result or an error message.

## How to Run

1. Clone the repository or download the files.
2. Open the `index.html` file in a web browser.
3. Use the buttons to perform calculations.

## Future Improvements

- Implement a graphical user interface (GUI) for enhanced user interaction.
- Add advanced mathematical functions such as square root and exponentiation.
- Improve error handling for more robust calculations.

## License

This project is open-source and available for use and modification.
