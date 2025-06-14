<h1>ExpNo 7 : Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game</h1> 
<h3>Name: Harini S      </h3>
<h3>Register Number:212223040058           </h3>
<H3>Aim:</H3>
<p>
Implement Alpha-beta pruning of Minimax Search Algorithm for a Simple TIC-TAC-TOE game
</p>
<h1>GOALS of Alpha-Beta Pruning in MiniMax Search Algorithm</h1>

<h3>Improve the decision-making efficiency of the computer player by reducing the number of evaluated nodes in the game tree.</h3>
<h3>Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning and the Minimax algorithm with Python Code.</h3>
<h1>IMPLEMENTATION</h1>

The project involves developing a Tic-Tac-Toe game implementation incorporating the Alpha-Beta pruning with the Minimax algorithm. Using this algorithm, the computer player analyzes the game state, evaluates possible moves, and selects the optimal action based on the anticipated outcomes.

<h1>The Minimax algorithm</h1>

recursively evaluates all possible moves and their potential outcomes, creating a game tree.

<h1>Alpha-Beta pruning</h1>

Alpha–Beta (𝛼−𝛽) algorithm is actually an improved minimax using a heuristic. It stops evaluating a move when it makes sure that it’s worse than a previously examined move. Such moves need not to be evaluated further.

When added to a simple minimax algorithm, it gives the same output but cuts off certain branches that can’t possibly affect the final decision — dramatically improving the performance
<hr>

## PROGRAM

```
import math

def minimax(curDepth, nodeIndex, maxTurn, scores, targetDepth, alpha, beta):
    # Base case: targetDepth reached
    if curDepth == targetDepth:
        return scores[nodeIndex]

    if maxTurn:
        maxEval = -math.inf  # Initialize maximum evaluation
        # Maximizing player's turn
        for i in range(2):  # There are two children for each node
            eval = minimax(curDepth + 1, nodeIndex * 2 + i, False, scores, targetDepth, alpha, beta)
            maxEval = max(maxEval, eval)
            alpha = max(alpha, eval)  # Update alpha
            if beta <= alpha:  # Beta pruning
                break
        return maxEval
    else:
        minEval = math.inf  # Initialize minimum evaluation
        # Minimizing player's turn
        for i in range(2):  # There are two children for each node
            eval = minimax(curDepth + 1, nodeIndex * 2 + i, True, scores, targetDepth, alpha, beta)
            minEval = min(minEval, eval)
            beta = min(beta, eval)  # Update beta
            if beta <= alpha:  # Alpha pruning
                break
        return minEval

 scores = [3, 5, 6, 9, 1, 2, 0, -1]
    targetDepth = 3  # Example target depth

    # Start Minimax from the root with initial alpha and beta values
    best_value = minimax(0, 0, True, scores, targetDepth, -math.inf, math.inf)
    print("The optimal value is:", best_value)
```
<h2>Sample Input and Output:</h2>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8d5e329a-9aff-41a6-bcf0-46efa10e1b92)
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/438b242d-54ba-443e-b040-a936e6ae3b55)
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/99a33390-fa11-4ade-a19f-e93bcd7aaec9)
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/440797bd-53cb-49c1-b18d-89776864c3e7)
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/81575a16-26b2-46f1-a8ac-27c9ed0a0fe5)

## RESULT:
Thus,Implementation of Minimax Search Algorithm for a Simple TIC-TAC-TOE game wasa done successfully.
