---
title: Synchonization Experience
...

The purpose of this lab is to provide you with some experiencing seeing how various synchronization primitives play out in practice. It will take the form of playing four versions of a simple competitive online game.

# Getting with a group

Lab will open with you signing into zoom <https://virginia.zoom.us/j/138570502>.
The TAs will then split you into zoom breakout rooms of 3--5 people each.
Zoom's toolchain appears to limit us to making these assignments randomly.

Expecting that many of your are feeling somewhat isolated and in need of conversation, we encourage you to spend several minutes in small-talk with the other members of your group before other activities begin.

You will then go through the four game variants together.

# The Game

You'll be presented with 

- a dollar amount you are trying to reach. Each player has a different target amount, all within $20 of one another.
- a dollar amount that is "on the table"
- a set of buttons for adding or removing money in increments of $1, $5, $10, and $20

Your goal is to reach your target dollar amount before anyone else you are playing with does so.

# The Variants

1.  Variant 1 (<https://kytos.cs.virginia.edu/coa2/cashgame1.php>) 
    has atomic money moves and no other synchronization.
    It is possible (even likely) that other players' plays will occur between you looking at the table and your play being acted on.

1.  Variant 2 (<https://kytos.cs.virginia.edu/coa2/cashgame2.php>)
    uses locks to prevent plays if someone else has made a play between your looking and acting.

1.  Variant 3 (<https://kytos.cs.virginia.edu/coa2/cashgame3.php>)
    places arriving players in a queue and only lets them play in order.
    It is otherwise like Variant 1.

1.  Variant 4 (<https://kytos.cs.virginia.edu/coa2/cashgame4.php>)
    uses voting to make plays; only if a majority of players agree to an action does it occur.

Each variant allows arbitrary game names.
Your group should

1. for each variant
    a. repeat until you agree on how the variant feels in play
        i. pick a name
        i. all enter that game (make sure no one plays before all are in the game)
        i. play until someone wins (we encourage conversation during play)
1. agree on how to describe how the different synchronization models changed how the game feels; you'll need to share this with a TA for check-off.
1. call a TA to come join your room and share what you found

# Passing Off

Explain to a TA how the different games felt different. They will be looking for evidence that you understood how the synchronization model impacted the game.
