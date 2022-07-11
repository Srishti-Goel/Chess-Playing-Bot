# Chess-Playing Bot
## What is this?
![alt text](https://github.com/Srishti-Goel/Chess-Playing-Bot/blob/main/Chess_bot/Chess-Player.jpg)  
This is the Chess-Playing bots part of the project.  
The Front-End interface can be found in a separate repository listed here: https://github.com/Srishti-Goel/ChessInterface.  
Due to the current lack of connection to the Front-End, a separate, Command-Line based interface has also been created to test our algorithms.  

## How to Play
The official game playes by running the file "util.ipynb".  

**Step 1**:  
Run the first 2 cells as they are, without making any changes.  
  
**Step 2**:  
Create an empty chess board as:  
```python
my_board = chess.Board()
```
  
  
**Step 3**:  
Decide the player you want to play as (White / Black).  
This decides the order of your game-playing function arguments.  
To play, call the play_game function as:
```python
play_game(my_board, (White player), (Black player))
```

You play as the ```ConsolePlayer()```   
  
**Step 4**:  
Decide the engine you want to play against and place the respective function in the other player.  
  
**Step 5**:  
Play well, and try to beat the computer engine! :)  
  
NOTE: Some of the engines return statistical data in the 
   
 ## Currently Available Players
 The engines currently available are:
 1. ```DummyEngine()```  
     This player is a random-move player. It doesn't evaluate the positions, just if the move made is legal or not.
     
2. ```ScoreEngine('basic')```  
   This player maximizes its reward in the next move. However, this may miss check-mate patterns, etc.  
  
3. ```ScoreEngine('improved_space')```  
    This player maximizes its reward in the next move, while maximizing the space it occupies on the board.  
    
 4. ```ScoreEngine('minimax')```  
    This player implements the same algorithm as is implemented in the benchmarked Stockfish engines.  
    It looks at the possible future lines of the moves to a depth defined in the function.  
    The depth of the tree defines how many moves into the future this engine searches. The deeper the tree, the more moves ahead it searches (assuming perfect play from both players), which usually results in better move patterns, but it also takes that much longer to find the next best move.  
    Through a trial and error method, we have found the optimal depth of 6-8 moves.

## Comparing the Algorithms
- As a general rule, all the ScoreEngine() bots almost always beat the DummyEngine() [as it would be concerning if they don't].  
- The minimax algorithm takes much longer computationally to find moves that generally lead to a success in most of the games played against DummyEngine, and about 80% if the games played against the basic ScoreEngine().  
- Between the basic and the improved_space engines, there isn't a big computation-time gap, but there is no clear winner between them.  
