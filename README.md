# HoggyProject
Developing a simulator and multiple strategies for the dice game Hog.

# Rules of the Game
In Hoggy two players alternate turns trying to be the first to end a turn with at least GOAL total points, where GOAL defaults to 100. On each turn, the current player chooses some number of dice to roll, up to 10. That player's score for the turn is the sum of the dice outcomes. However, a player who rolls too many dice risks:

Sow Sad:
If any of the dice outcomes is a 1, the current player's score for the turn is 1.

  Example 1: The current player rolls 7 dice, 5 of which are 1's. They score 1 point for the turn.
  Example 2: The current player rolls 4 dice, all of which are 3's. Since Sow Sad did not occur, they score 12 points for the turn.

In a normal game of Hog, those are all the rules. To spice up the game, we'll include some special rules:

Pig Tail:  

A player who chooses to roll zero dice scores 2 * abs(tens - ones) + 1 points; where tens, ones are the tens and ones digits of the opponent's score. The ones digit refers to the rightmost digit and the tens digit refers to the second-rightmost digit.

Example 1: 
The opponent has 46 points, and the current player chooses to roll zero dice. 2 * abs(4 - 6) + 1 = 5, so the player gains 5 points.

Example 2: 
The opponent has 73 points, and the current player chooses to roll zero dice. 2 * abs(7 - 3) + 1 = 9.

Square Swine:
After a player gains points for their turn, if the resulting score is a perfect square, then increase their score to the next higher perfect square. A perfect square is any integer n where n = d * d for some integer d.

Example 1: 
A player has 12 points and rolls 3 dice that total 13 points. Their new score would be 25, but since 25 is 5 squared, their score is increased to 6 squared: 36.

Example 2:  
A player has 12 points and rolls 3 dice that total 12 point. Their new score would be 24, which is not a perfect square.

Example 3:  
A player has 0 points and rolls 5 dice, but one is a 1, so their new score would be 1. 1 is a perfect square, and so their score is increased to 4.

Example 4:

A player has 80 points and rolls 10 dice, but three are 1's, so their new score would be 1. 81 is 9 squared, so their new score is 10 squared: 100. They win the game.
