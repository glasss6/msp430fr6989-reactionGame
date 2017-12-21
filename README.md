# Reaction Game
## Stephen Glass

## main.c
### Compatibility
* MSP4306989

### Description
The reaction game is designed for the MSP430FR6989 and utilizes the LCD display. The goal of the 2-player game is to be the first player to press your buttom 10 times. The first player to press the button 10 times wins. Each time you press the button it updates your score on the LCD display and blinks an LED to indicate that you successfully pushed the button. When you win, it will display it on the screen! After winning, the game will automatically reset after a few seconds and you can start another round with your friend!

This code utilizes the driverlib LCD display library. The code has software debouncing for the buttons to make sure that each button press is fair and accurate.

## YouTube Video Demonstration
![YouTube Video](https://img.youtube.com/vi/Fg25mOs-a4c/0.jpg)](https://www.youtube.com/watch?v=Fg25mOs-a4c)

## Functions
### init_GPIO(void)
This function will initialize the GPIO for the LCD display, buttons, and LEDs. Additionally, this will disable any unused GPIO ports.

### Init_Clock(void)
This function will initialize the clock 1 for updating the LCD display.

### initializeTimer(int capture)
This function will initialize the timer used for software debouncing of the buttons.
* int capture = the frequency of the timer to set in hertz

Example:
initializeTimer(100); // Set the timer module to 100Hz

### updateScore(unsigned int player, unsigned int score)
This function will update the scoreboard for the specified player and score.

Example:
updateScore(9, 5); // Set the score of player 1 to 5
updateScore(7, 2); // Set the score of player 2 to 2
// 9 = player 1, 7 is player 2



## hal_LCD.c
This is part of the driverlib library by Texas Instruments. This file creates some basic functions for displaying characters on the LCD screen. This code is used to show the score on the LCD display and showing the winner of the LCD.

## Functions
### Init_LCD(void)
Initializes the LCD variables and GPIO.

### displayScrollText(char)
Displays a string across the LCD display like a marquee.

Example:
displayScrollText("P1 WINS"); // Will display "P1 WINS" across the LCD display

### showChar(char, int)
Displays a character at specified spot in the LCD.

Example:
showChar(9, 0x01); // Displays the character associated with 0x01 in the player 1 spot (9)

### clearLCD(void)
Clears the LCD display of everything.