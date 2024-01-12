# Stick Hero

## Overview
Stick Hero is a JavaFX application where players navigate a stick figure through various levels by controlling the length of the stick used to cross gaps between platforms.
## Features of Game
- Dynamic gameplay with interactive stick control.
- Score and gem count display with custom fonts and borders.
- Pause functionality to temporarily halt the game.
- Animation transitions for smooth gameplay experience.
# Usage OverView
### Usage of Home Menu
- Click the "Play" button to start the game.
- Click the "Exit" button to close the application.
- Navigate your stick figure across the platforms and aim for a high score!

### Gameplay
- Click and hold to grow the stick.
- Release to drop the stick and rotate it into a bridge.
- Cross the gap safely to score points and collect gems.
- Press the pause button to pause the game at any time.
- ---------------------------------------------------------------------------------------
## Pause Functionality
The Stick Hero game includes a pause feature that allows players to temporarily halt the gameplay. This feature is particularly useful if players need to take a break or attend to something else without closing the game.

### How It Works
- The pause button is represented by a custom image and is positioned at the top-left corner of the game window.
- When the pause button is clicked, the game enters a paused state, and all game actions are suspended.
- A "Paused" label is displayed along with options to "Resume" the game or return to the "Home" screen.
- The current score is displayed, and the high score is retrieved and shown for comparison.
- Clicking the "Resume" button will remove the pause overlay and restore the game's interactive state, allowing players to continue from where they left off.

### Implementation Details
- The pause button is created as a `Button` with an `ImageView` containing the pause icon.
- Event handlers for mouse pressed and released actions are temporarily disabled to prevent any game interaction during the pause state.
- A VBox layout is used to organize the pause label and buttons vertically, and an HBox layout is used to display the scores horizontally.
- The game's main pane is cleared and then populated with the pause interface elements.
- Once the "Resume" button is clicked, the pause interface is removed, and the original event handlers are restored to resume gameplay.

- This pause feature ensures that players have control over their game session and can pause and resume the game at their convenience.
---------------------------------------------------------------------------------------
## End Game Functionality
The Stick Hero game features an end game scenario that is triggered when the player's character meets an untimely end. This functionality provides players with options to either retry the level, return to the home screen, or use in-game currency to revive the character.

### How It Works
- When the player dies, the game displays a message "You Died!!" along with buttons for different actions.
- The "Retry" button resets the score to zero and restarts the game from the beginning of the level.
- The "Revive" button allows players to continue from where they left off by spending in-game currency (gems).
- If the player does not have enough gems, a message "Not enough gems" is displayed, and the score is reset.
- The end game screen also shows the player's current score and the high score for comparison.

### Implementation Details
- The end game screen is implemented using a `VBox` layout to organize the message and buttons vertically.
- A `BorderStroke` and `CornerRadii` are used to style the "Revive" button, giving it a distinct look.
- The `revive` button's background is set with a transparent image for a consistent design with other buttons.
- Event handlers for mouse actions are disabled to prevent any unintended game interactions during the end game state.
- Clicking the "Retry" button invokes the `start_main_game` handler to reset the game.
- The `getEndPage` method manages the display and functionality of the end game screen.

This end game feature ensures that players have multiple options after their character dies, enhancing the overall gameplay experience.
## Resources used
- JavaFX SDK: The primary framework used for creating the graphical user interface of the game.
- Java Development Kit (JDK): The essential toolkit for developing Java applications, including the Stick Hero game.
- Image Assets: Custom images for backgrounds, buttons, and icons, which are loaded using the Image class in JavaFX.
- Custom Fonts: Fonts like “DM Sans” and “Times New Roman” are used to style text elements such as labels and buttons.
- Event Handling Classes: Classes like EventHandler, MouseEvent, and AnimationTimer are used to handle user interactions and animate the game.
- Layout Managers: JavaFX layout managers such as Pane, VBox, HBox, and Scene are used to structure the game’s UI components.
- Shapes and Transitions: The Rectangle class and TranslateTransition are used to represent the stick and animate the stick figure, respectively.
- Styling Classes: Classes like CornerRadii, BorderStroke, Border, and Background are used to style UI components with borders and backgrounds.
---------------------------------------------------------------------------------------
# Design Patterns Used

### Singleton
The Singleton pattern is implemented in the `path_stick` class, which ensures that only one instance of the main path (a `Rectangle` object) is created and shared across the application.

### Factory
The Factory pattern is implemented in the `Factory` class, which provides a method `get_shape` to create shapes based on the provided type. It supports creating `Rectangle` and `Square` shapes and adds them to a given `Pane`.

## Classes and Methods

### Factory Class
- `get_shape(String asd, Pane ma_p)`: Returns a `Shape` object based on the type specified.
- `getRectangle(Pane main_pane)`: Private method to create a `Rectangle` object.
- `getSquare(Pane main_pane)`: Private method to create a `Square` object.
- `get_Cherry(Rectangle rectangle, Pane main_pane)`: Private method to create an `ImageView` object representing a cherry.

### path_stick Class
- `getPathRectangle()`: Static method to get the instance of the main path `Rectangle`.
---------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------
## Requirements
- Java 8 or higher
- JavaFX SDK

## Installation
To run Stick Hero, you will need to have Java and JavaFX installed on your system.

1. Install Java JDK from Oracle's website or use OpenJDK.
2. Download JavaFX SDK from OpenJFX.
3. Configure your IDE to include the JavaFX library and add VM options to include the JavaFX modules.

## Assumptions
- When the Player is in moving state, user is advised **`not to click`** at the time as it may cause buggy behaviour sometimes. Although this bug comes rarely.
- Consider a Scenario where a player is dying but can touch/is touching a diamond then it can collect that.
- The hitbox ( the space around an objest, that's considered a part of it ) of the diamond is intentionally left big for the ease of the player to play it.
- The paths of all the images are absolute, so to run it, the paths have to refactor.  

## Running the Application
1. Compile the source code using your preferred IDE or command line.
2. Run the `HelloApplication` class to start the application.

# Authors
- Amartya Singh
- Adarsh Jha
