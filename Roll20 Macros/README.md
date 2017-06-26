# Roll20 Macros for ADOM Lite

## Installation and Usage
1. Log in to Roll20.
2. Navigate to the game where you wish to use the macro.
3. Click the "Join Game" button.
4. Click the "Collections" icon at the top of the side menu.
5. Click the "+ Add" button next to "Macros".
6. Enter a name for the macro. Ensure that it is short and descriptive. Spaces will be replaced with dashes, so avoid them if possible.
7. Copy the selected macro into the "Actions" field.
8. Click the "Save Changes" button.
9. If you wish to have quick access to the macro, click the "In Bar" checkbox next to the macro.
10. Use the macro in chat by typing the pound sign (#) followed by the macro name. e.g. #listen

## Output
* Most macros output three lines:
* The first line shows the roll formula as it is presented to Roll20; this can be ignored.
* The second line shows the roll. The first number represents the die and the second number represents the modifier that is added when a trait is over twenty. Pass / fail rolls include a third number that represents the target + 1 (One is added due to limitations imposed by Roll20). e.g. "20 + 5 > 15". **The first number will be highlighted in red if the die rolled higher than the trait (roll over failure) or in green on a critical success.**
* The third line shows the result. In most cases, this will be the number of success points (SuP). In the case of a pass / fail roll, this will show the number of successes: 1 or 0. **Roll over failures and critical successes are not taken into account; they must be applied manually according to the "Roll Over Failures and Critical Successes" section of this document.**


## Roll Over Failures and Critical Successes
Due to limitations imposed by Roll20, macros do not automatically consider rolls that fail when the die rolls higher than the trait (roll over failures) or critical successes; the impact of these must be applied manually. Any roll that contains a roll over failure, fails and returns 0 success points (SuP). Depending on the purpose of the roll, critical successes result in doubled SuP or an automatic success; for specifics, please refer to the ADOM Lite manual. In the case of pass / fail rolls that return either a 1 or a 0 as a success count, the results of the roll will have to be tallied by hand in the event of a critical success that doubles SuP.

## Generic Character Sheet Integration
The specifics of how to use generic character sheets with the Roll20 journal are currently beyond the scope of this document, however instructions on how to use the macros with such character sheets are provided here. When you want to pull a character sheet attribute into one of the macros, use the following steps:
1. Within the macro, locate all instances of the "roll query" that calls the attribute. e.g. `?{Perception|0}`
2. Replace the "prompt message" with a reference to the character sheet attribute (e.g. `?{Character Name|Attribute}`). You may also substitute the "target" or "selected" keywords for the character name.
3. Replace "?" with "@". e.g. `@{Character Name|Attribute}`

For more information refer to the following documentation:
* Roll20 Dice Reference: https://wiki.roll20.net/Dice_Reference
* Roll20 Macro Documentation: https://wiki.roll20.net/Macros
* Roll20 Character Sheet Documentation: https://wiki.roll20.net/Character_Sheets
