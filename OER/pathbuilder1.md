<!--
author:  Claude
email: 
version:  0.1.0
language: en
narrator: US English Female
comment: A simple adventure story with single choices and goto statements
-->

# The Ancient Temple Adventure

Once upon a time, you found yourself standing at the entrance of an ancient temple deep in the jungle...

What do you do?

[[enter the temple |Temple Entrance]]
[[return home |Go Home]]

## Go Home
You decide this adventure is too dangerous and head back home. Perhaps another day...

The End.

@goto(Start Over)

## Temple Entrance
You step into the dimly lit temple entrance. The stone walls are covered in mysterious symbols, and you notice two passages ahead.

Which passage do you take?

[[left passage |Left Room]]
[[right passage |Puzzle Room]]

## Left Room
The passage leads you to a room with a golden idol on a pedestal. There's a suspicious pressure plate in front of it.

What's your next move?

[[walk carefully around the plate |Success]]
[[step on the plate to reach the idol |Trap]]

## Puzzle Room
You enter a chamber with an ancient puzzle door. There are three colored levers on the wall.

Which lever will you pull?

[[red lever |Red Lever]]
[[blue lever |Blue Lever]]
[[green lever |Green Lever]]

## Success
Using your archaeological knowledge, you carefully maneuver around the trap and retrieve the idol safely. Congratulations! You've succeeded in your quest!

The End.

@goto(Start Over)

## Trap
As you step on the plate, the entire room begins to shake! The ceiling starts collapsing! You run out just in time, but empty-handed.

The End.

@goto(Start Over)

## Red Lever
The ground beneath you opens up! You fall into a pit of... soft cushions? It seems this was an escape route. You slide through a tunnel and end up outside with an ancient treasure map!

The End.

@goto(Start Over)

## Blue Lever
A burst of ancient dust fills the room. When it clears, nothing seems to have changed... except your hair is now bright blue!

The End.

@goto(Start Over)

## Green Lever
The door slowly creaks open, revealing a magnificent library of ancient scrolls. You've discovered knowledge far more valuable than gold!

The End.

@goto(Start Over)

## Start Over
Would you like to try again?

[[start a new adventure |The Ancient Temple Adventure]]
