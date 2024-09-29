Documentation for Flutter Calculator App:


This documentation explains the structure, logic, and features of the provided Flutter Calculator App code. The app performs basic arithmetic operations and provides a simple user interface using Flutter. The app consists of a primary screen where buttons are dynamically generated and displayed. Let's break it down:
Project Structure
1.	main.dart: Entry point of the Flutter app.
2.	calculator_screen.dart: The main screen where the calculator functionality is implemented.
3.	button_values.dart: A separate file that contains button values, such as numbers, operators, and actions (clear, delete, etc.).
Widgets and Layout
CalculatorScreen Widget
•	Type: Stateful Widget
•	Purpose: Displays the calculator interface and handles the interaction and state changes.
Key UI Components:
1.	App Bar:
Displays a centered title "Calculator App".
2.	Display Area:
Shows the current input and calculation result.
Utilizes the SingleChildScrollView to scroll if the input is too long.
Aligns text to the right for a clean calculator feel.
3.	Button Grid (Wrap Widget):
Dynamically generates the calculator buttons from the values defined in button_values.dart.
Uses SizedBox to adjust the size of each button, and buttons are evenly spaced.
Buttons are laid out using the Wrap widget to create a grid-like structure for numbers and operations.

Core Functions
1.	Button Creation (buildButton):
This method generates each button using Flutter's Material widget, styled with InkWell for clickable behavior. The color, shape, and text are set based on the button value.
The onTap event triggers the action associated with each button.
2.	Button Action Handler (onBtnTap):
This function processes what happens when a button is pressed.
It checks for different button types:
	Numbers: Appends the pressed number to number1 or number2 based on the state.
	Operators: Stores the operator for calculation.
	Clear (C): Resets the entire display.
	Delete: Deletes the last character from the input.
	Percentage (%): Converts the input number into a percentage.
	Equals (=): Executes the calculation.
3.	Calculation Logic (calculate):
When the = button is pressed, the calculator checks if all necessary values (number1, operand, number2) are present.
Performs the selected operation (addition, subtraction, multiplication, division).
Converts the result into a readable string using toStringAsPrecision(3), which limits the result to three significant digits.
Resets operand and number2 after showing the result.
4.	Percentage Conversion (convertToPercentage):
Converts the current value of number1 into a percentage (divides by 100).
If a calculation is in progress (i.e., number1, operand, and number2 are present), it first calculates the result before converting to percentage.
5.	Clear and Delete (clearAll, delete):
clearAll: Resets the calculator, clearing all values (number1, operand, number2).
delete: Deletes the last character entered, whether it’s part of number1, number2, or the operator.

Design Decisions
1.	Color Scheme:
Operator Buttons: Colored orange to distinguish from number buttons.
Action Buttons (DEL, C): Colored blue-grey for a subtle highlight.
Number Buttons: Colored black for a clean, minimalist look.
2.	Button Size:
The "0" button takes up two columns in width, providing more emphasis, similar to many physical calculators.
Other buttons maintain a uniform size to keep the layout neat and consistent.
3.	Screen Responsiveness:
The button sizes and layouts adapt to the screen size using MediaQuery. This ensures the buttons are well spaced and look consistent across different devices.

button_values.dart
Button Values
The buttons are categorized based on their functionality, including number buttons, operator buttons, and special action buttons. Here’s a breakdown:
1.	Special Action Buttons:
del ("D"): This button is used to delete the last digit or operator in the current input.
clr ("C"): Clears the entire input, resetting the calculator.
per ("%"): Converts the current number to its percentage value.
calculate ("="): Triggers the calculation of the equation and displays the result.
2.	Operator Buttons:
multiply ("×"): Multiplies the two input numbers.
divide ("÷"): Divides the first number by the second number.
add ("+"): Adds the two input numbers.
subtract ("-"): Subtracts the second number from the first number.
3.	Number Buttons:
n0 ("0") to n9 ("9"): The digits 0 through 9 used to input numbers.
dot ("."): Used for decimal numbers to input floating point values.

buttonValues List
The buttonValues list is an ordered collection of all the buttons that appear in the calculator. It specifies the sequence in which buttons are displayed on the UI.
The buttons in the list are ordered in a grid-like fashion (4 columns by 5 rows) with:
•	The first row containing DEL, C, %, and ×.
•	The second to fourth rows contain the number buttons and basic arithmetic operations.
•	The final row contains 0, ., and = for calculating the result.
Usage of the Btn Class
•	In the Flutter app, the buttonValues list from the Btn class is mapped to UI components (e.g., buttons) in the calculator screen. Each value in the list represents a button on the calculator and is rendered accordingly.
Button Values Summary
•	The Btn class provides a clean, organized way to manage button labels for the calculator app.
•	It includes constants for numbers, operators, and special actions like clear and delete.
•	The buttonValues list holds all button labels in a specific order, ensuring they are displayed in the correct sequence in the calculator UI.

App Usage
1.	Input Numbers:
Tap the number buttons to input the first number (number1).
2.	Select Operation:
Tap any operator (+, -, *, /) to choose the operation.
3.	Input Second Number:
After choosing the operation, tap the number buttons to input the second number (number2).
4.	Calculate Result:
Press = to perform the operation and display the result.
5.	Clear:
Press C to reset the calculator to its initial state.
6.	Delete:
Press DEL to delete the last character from the current input.
7.	Percentage:
Press % to convert the current number to a percentage.

Conclusion
This Flutter Calculator App provides a simple yet functional calculator interface. The app uses basic Flutter components like Scaffold, Wrap, and Material widgets to create an interactive and responsive layout. The core of the app lies in the logic for handling number input, operators, and performing arithmetic calculations. This app can be further extended to handle more complex operations or scientific functions based on the user's needs.


